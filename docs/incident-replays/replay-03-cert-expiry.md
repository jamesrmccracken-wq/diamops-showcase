# Incident Replay 03 — Certificate Expiry Chain

**Operator:** Operator 04 — Cloud/DevOps  
**Ticket ID:** TKT-0089 / TKT-0090 / TKT-0091 (simulated incident chain)  
**Priority:** P2 — Advanced  
**Category:** Infrastructure / Certificate Management  
**Investigation score:** 93/100 (primary ticket — TKT-0089)  
**Session:** Session 4, Ticket 10 (Certificate Expiry on Load Balancer)  

---

## Incident Chain Overview

This replay documents a 3-ticket incident chain. The operator investigated the primary ticket (TKT-0089) and discovered the chain via the related incidents panel.

```
TKT-0088 (upstream)        TKT-0089 (primary)         TKT-0091 (downstream)
CI/CD deploy skipped       Load balancer cert          HTTPS failures for
cert rotation step    →    expired — ALB returning  →  dependent microservices
                           SSL_ERROR_RX_RECORD_TOO_LONG    (api-gateway, checkout)
```

---

## Incident Record — TKT-0089 (Primary)

### Symptoms
Production ALB (app-prod-lb-01) returning SSL errors for all HTTPS traffic. CloudWatch ALB metrics showing 100% 5xx error rate on HTTPS listener since 09:47. HTTP traffic on port 80 unaffected. Users reporting "This site can't be reached" for all HTTPS endpoints. Incident started approximately 09:47 — coincides with certificate renewal check schedule.

### Evidence Available
1. AWS Certificate Manager console: Certificate `*.corp-app.com` — Status: EXPIRED — Expiry: 2026-05-28 09:45
2. ALB listener configuration: HTTPS:443 listener — Certificate: `*.corp-app.com` — Certificate status: Expired
3. CloudWatch ALB metrics: 5xx error rate jumped from 0% to 100% at 09:47:02
4. CloudWatch ALB access logs: `"SSL_ERROR_RX_RECORD_TOO_LONG"` errors in all HTTPS requests since 09:47
5. Certificate renewal automation: Route53/ACM auto-renewal job last ran 2026-05-21 — LOG: "Certificate renewal skipped — validation DNS record not found"
6. Route53 DNS records: CNAME `_acme-challenge.corp-app.com` — DELETED. Last change: 2026-05-22 14:31 (Terraform apply, commit a4f2b1c)
7. Terraform state: `aws_route53_record._acme_challenge_corp_app` — destroy in commit a4f2b1c — applied 2026-05-22
8. Related incidents panel: TKT-0088 (upstream — deploy step) · TKT-0091 (downstream — microservice failures)

---

## Operator Investigation

### What the operator did
1. Read full ticket — symptoms, environment badge ("Production — High escalation risk")
2. Read ALL 8 evidence items before writing notes
3. Checked related incidents panel — discovered TKT-0088 (upstream) and TKT-0091 (downstream)
4. Used `p9_explain_issue` — Advanced tier output with chain context
5. Used `p9_generate_rca` — evidence confidence: "7/8 supporting indicators for certificate expiry due to Terraform DNS record deletion"
6. Wrote structured notes (160 words):

> "Certificate `*.corp-app.com` expired at 09:45, immediately causing ALB HTTPS listener to serve SSL errors. Root cause: ACM auto-renewal failed on 2026-05-21 because the validation DNS CNAME `_acme-challenge.corp-app.com` was missing — this record was deleted by Terraform commit a4f2b1c on 2026-05-22 as part of an infrastructure cleanup. The Terraform change inadvertently removed the ACM validation record, preventing certificate renewal. This ticket is downstream of TKT-0088 (CI/CD deploy skipped cert rotation check) and upstream of TKT-0091 (HTTPS failures in api-gateway and checkout microservices). Full chain affects all production HTTPS traffic."

7. Actions (numbered runbook):

> "1. Provisioned new ACM certificate for *.corp-app.com via Console (DNS validation method). 2. Re-created `_acme-challenge.corp-app.com` CNAME in Route53 — issued manually, Terraform to be updated. 3. Waited for ACM validation (approximately 4 minutes). 4. Updated ALB HTTPS listener to use new certificate ARN. 5. Confirmed HTTPS traffic restoring — CloudWatch 5xx rate dropping. 6. Created Jira ticket INFRA-4421: Add cert validation record to Terraform state to prevent future deletion. 7. Updated TKT-0091 status — root cause confirmed upstream. Downstream services recovering."

8. Verified: Yes — confirmed with CloudWatch metrics
9. Closed: Resolved

**Time taken:** 22 minutes (complex chain case — appropriate duration)

---

## Scoring Record

| Metric | Value | Notes |
|---|---|---|
| Overall score | 93/100 | Strong chain documentation |
| Root cause correct | Yes | Terraform DNS record deletion |
| Evidence reviewed | Yes | All 8 items |
| Verified before close | Yes | CloudWatch confirmed |
| Hints used | None | — |
| Notes depth | Deep | Chain-aware, all root causes mapped |
| Chain documented | Yes | Upstream + downstream referenced |

### Consequence flags
None fired.

---

## Chain Investigation Analysis

### The Terraform → ACM → ALB → Microservices chain
This is a 4-system causal chain:

```
Terraform apply (infrastructure cleanup)
    ↓ Deletes _acme-challenge DNS CNAME (inadvertent)
ACM auto-renewal job
    ↓ Fails — validation DNS record not found
Certificate expiry
    ↓ ACM certificate expires at 09:45
ALB HTTPS listener
    ↓ Certificate expired — all HTTPS returns SSL error
Downstream microservices (api-gateway, checkout)
    ↓ Service-to-service HTTPS calls failing
    → TKT-0091: "HTTPS failures for dependent microservices"
```

### What the operator understood
The operator correctly traced the chain from the presenting symptom (ALB SSL error) to the root cause (Terraform deleting the DNS validation record) to the systemic fix (update Terraform state to protect the record).

This is post-mortem level reasoning applied to a ticket investigation — exactly what the SRE/Cloud archetype demonstrates.

### What a shallow investigation would miss
- **Certificate renewal skip log (item 5):** This is the smoking gun. Without reading this, the investigator would see "certificate expired" and reissue without understanding why it expired. The renewal skip reason ("validation DNS record not found") points directly to the root cause.
- **Terraform commit (items 6, 7):** The Git history evidence links the certificate failure to an infrastructure change — the kind of cross-system root cause that requires infrastructure-aware thinking.
- **Chain context (item 8):** Without checking related incidents, the systemic impact on downstream services might be missed or reported as a separate unrelated incident.

---

## Recruiter Value

This case demonstrates:
- Multi-system infrastructure root cause identification (Terraform → ACM → ALB chain)
- Post-mortem quality investigation documentation
- Systemic fix thinking (not just "reissue certificate" — includes Terraform state remediation)
- Chain-aware documentation (upstream + downstream impact mapped)
- Evidence-informed root cause (renewal skip log correctly identified as key evidence)

**Assessment for Cloud/DevOps Engineer / SRE role:** This is a senior-level incident investigation. The Terraform root cause identification, ACM/ALB chain understanding, and systemic fix (protecting the DNS record in Terraform state) demonstrate infrastructure-aware thinking at a senior level.

A hiring manager for an SRE or Cloud Infrastructure role reading this proof page would see:
1. Complex multi-system chain handled correctly
2. Structured runbook-style remediation
3. Root cause prevention included (Jira ticket for Terraform fix)
4. No hints used — independent investigation

**This is the strongest case in the DiamOps validation showcase.**

---

## Platform Behaviour Notes

- Related incidents panel showed TKT-0088 (upstream) and TKT-0091 (downstream) correctly
- `p9_generate_rca` Advanced evidence confidence output: 7/8 — accurate (item 4, the ALB access logs, are the 8th item — supporting but redundant given CloudWatch metrics)
- Chain documentation scored correctly — notes explicitly naming upstream/downstream tickets
- No red herrings in this case (by design — the evidence chain is clean for this Advanced case type)
- Score 93/100 is appropriate: near-perfect investigation with full chain documentation, all evidence read, and correct systemic fix identified
