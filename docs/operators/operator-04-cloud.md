# Operator 04-cloud — Full Showcase

# Operator 04 — Systematic Cloud/DevOps

**Archetype:** Cloud Infrastructure / DevOps engineer  
**Real-world analogue:** 3 years in cloud infrastructure. Manages AWS environments, writes Terraform, owns CI/CD pipelines. Rarely does "tickets" in their day job — incidents are handled via runbooks and post-mortems. Looking to build a structured evidence portfolio for a Senior Cloud Engineer or SRE role.  
**Goal on DiamOps:** Demonstrate structured incident investigation, root cause precision, and post-incident review quality. Wants the recruiter dashboard to show "SRE-ready" signals.

---

## Profile

| Field | Value |
|---|---|
| Experience level | 3–5 years |
| Current role | Cloud Infrastructure Engineer (AWS) |
| DiamOps tier | Advanced |
| Primary concern | "I want to show I can do structured RCA, not just fix things and move on" |
| Secondary concern | "Is the cloud/DevOps content realistic? I'll know if it's wrong." |
| Device | MacBook Pro, 1440p, Arc browser |
| Session length | 60–90 minutes |
| Session frequency | 2x per week (deliberate, methodical) |

---

## Behavioural Characteristics

- **Methodical:** Reads every evidence item before forming any hypothesis. Does not start writing notes until evidence review is complete.
- **Root-cause precise:** Notes explicitly name the root cause with evidence mapping. Writes like they're producing a post-mortem.
- **Runbook-oriented:** Actions are written as numbered steps ("1. Identified affected ECS tasks. 2. Rolled back task definition to v14. 3. Confirmed health check passing on 3/3 instances.")
- **Chain-aware:** Always checks related incidents before proceeding
- **Hint-never:** Never uses hints. Considers it a personal benchmark.
- **Demands infrastructure realism:** Will reject the platform if infrastructure tickets are generic or inaccurate

---

## Career Path Target

- **Primary path:** Cloud/DevOps Engineer → SRE
- **Milestone target:** Advanced (10+ cases, avg score ≥ 85)
- **Role affinity expected:** Cloud/DevOps → Strong; SOC → Moderate; NOC → Moderate; IT Support → Low

---

## Expected Achievements (after 12 cases)

- All standard achievements (first_case through verification_discipline)
- `root_cause_champion` — Yes (very precise root causes)
- `advanced_handler` — Yes (all Advanced/Critical tier)
- `chain_investigator` — Yes (always checks chains)
- `queue_recovery` — Possible (if queue surge fires during session)
- `documentation_excellence` — Yes (notes are always deep)
- `escalation_specialist` — Unlikely (never escalates)

---

## Sentinel Alignment

This operator tests:
- Cloud/DevOps ticket realism (AWS, Kubernetes, Terraform, CI/CD contexts)
- Advanced AI action quality (RCA confidence rows)
- Perfect scores possible? Can this archetype hit 90+ consistently?
- Role affinity Cloud/DevOps scoring ceiling
- Recruiter dashboard with 9+ achievements
- Progression timeline with many events

---

# Operator 04 — Cloud/DevOps — Full Journey

**Session date:** 2026-05-28  
**Total session time:** ~5h across 4 sessions  
**Cases completed:** 12  
**Final score average:** 89/100  

---

## Session 1 — Infrastructure Realism Assessment (90 min)

### Registration and Setup
Registers as Advanced tier. Reads wizard in ~60 seconds. Notes the "operational consequence" framing: "that's basically a post-mortem approach, I know how to do this."

### Ticket 1 — ECS Service Deployment Failure (P2 Advanced)

Opens ticket. Environment badge: "Production — High escalation risk." 

Reads ALL 8 evidence items before writing a single word. Starts writing after 4 minutes.

Notes (excerpt): "Root cause: ECS task definition v18 introduced memory limit reduction from 2048 to 512 MiB for the api-service container, causing OOMKilled failures on all 3 task instances. Evidence: CloudWatch Container Insights logs show OOMKilled at 14:32 on all 3 instances (evidence items 2, 5, 7). Task definition history confirms limit change in v18 commit f3a1b2c."

Actions: "1. Identified affected ECS service: api-service (3/3 tasks failing). 2. Rolled back task definition to v17. 3. Forced new deployment. 4. Confirmed 3/3 tasks healthy via ECS console. 5. Created Jira ticket for memory limit review before next deployment."

Verify: Yes. Root cause: Correct.

Score: 97/100. Highest first-case score of all operators.

**Reaction:** "The ECS context is accurate. OOMKilled, task definitions, Container Insights — whoever wrote this knows AWS. This platform is legitimate."

**Finding:** Infrastructure ticket realism earns immediate credibility with the Cloud/DevOps operator. This is the equivalent trust gate to AI action accuracy for the SOC operator.

### Tickets 2–4

All Cloud/Infrastructure domain. Scores: 93, 91, 94. Notes consistently structured as numbered runbook steps.

**Achievement progression:**  
- `first_case` — case 1  
- `evidence_first` — case 1  
- `verification_discipline` — case 3 (3 consecutive with verify)  
- `documentation_excellence` — case 4 (notes depth consistently high)  
- `root_cause_champion` — case 4 (5 correct root causes)

---

## Session 2 — Chain Investigation and Cross-Domain (75 min)

### Tickets 5–8

**Ticket 5 — Kubernetes Pod Eviction Loop (P1 Critical)**  
Environment badge: "DR Site — regulatory SOC 2 context."  

Related incidents panel: 2 linked tickets — upstream "Node disk pressure" and downstream "Service unavailable for dependent API."

Operator documents full chain in notes: "This eviction loop is downstream of TKT-0089 (node disk pressure). The upstream cause is log volume accumulation on node-02. Resolution requires both: clearing disk pressure upstream and restarting evicted pods."

Score: 98/100. Closest to perfect of all operators.

**Achievement fired:** `chain_investigator`

**Finding:** Perfect chain documentation is rewardable. The scoring rubric correctly gives maximum points for evidence + chain awareness + correct root cause + verification.

**Ticket 6 — Terraform State Lock Conflict (P2 Advanced)**  
Cross-domain: Infrastructure + Developer tooling. Handles confidently.

Score: 92/100. `cross_domain` achievement fires.

**Ticket 7 — CI/CD Pipeline Failure — Secrets Rotation (P2 Advanced)**  
Red herring: one evidence item shows "pipeline succeeded at 10:48" — but a different run failure occurred at 11:02. Operator reads both items, identifies the discrepancy.

Completion reveal: "The 10:48 success was a different pipeline stage. The 11:02 failure was the deployment stage."

Score: 94/100.

**Ticket 8 — AWS S3 Bucket Policy Misconfiguration (P2 Advanced)**  
Security/Cloud overlap ticket.

Score: 91/100. `advanced_handler` achievement fires (5 Advanced/Critical).

---

## Session 3 — Queue Surge + SRE Methodology (70 min)

**Queue enters surge state between sessions:** "HIGH — 18 unresolved, 5 SLA at risk."

**Operator reaction:** Reads the surge banner. Notes: "In a real SRE incident, this would mean the on-call rotation just got paged. I'll triage by blast radius."

Skips over P3 tickets in queue, starts with P1. This is correct SRE triage behaviour.

**Finding:** The platform doesn't expose ticket priority ordering in the queue — the operator has to make the judgment call themselves. This is realistic (real queues aren't always sorted by priority). However, a "SRE triage mode" that surfaces P1s first could be valuable.

### Tickets 9–11

**Ticket 9 — Database Connection Pool Exhaustion (P1 Critical)**  
RDS/PostgreSQL context. Operator finds the evidence trail systematically. Notes 5 structured steps. 

Score: 96/100. `queue_recovery` achievement fires (resolved a Critical ticket during queue surge).

**Ticket 10 — Load Balancer Health Check Misconfiguration (P2 Advanced)**  
Chain: upstream deployment change caused ALB health check path change.

Score: 93/100.

**Ticket 11 — Kubernetes ConfigMap Out of Sync — GitOps Drift (P2 Advanced)**  
GitOps/ArgoCD context. Authentic cloud-native incident type.

Score: 90/100.

---

## Session 4 — Final Case + Recruiter Review (65 min)

### Ticket 12 — Multi-Region Failover Misconfiguration (P1 Critical)

Complex case. 10 evidence items. Related to 3 other tickets. Cross-region Route 53 DNS failover failure.

Notes: 280 words. Full chain documented. All evidence mapped. 

Score: 95/100.

**Achievement fired:** `documentation_excellence` (confirmed over 8 consecutive deep-note cases)

---

## Recruiter Dashboard

**Readiness strip:** "88% — Strong" | Role alignment: "Cloud/DevOps Engineer" | Trend: "Stable at high performance"

Role readiness:
- Cloud/DevOps Engineer: 94/100 — Strong fit
- SOC Analyst: 58/100 — Developing
- NOC Analyst: 51/100 — Developing
- IT Support L1/L2: 24/100 — Early stage

**Achievements section:** 9 achievements displayed.

**Operator reads through achievements carefully.** "queue_recovery — resolved a Critical ticket during high-pressure queue surge. Yeah, that's exactly what I'd want a recruiter to see."

**Verified case evidence:** 11 of 12 cases shown (only case 1 at 97 — all qualify). 

**Operator opens proof for the Kubernetes pod eviction chain case (98/100):**

Reads investigation notes — exact text preserved. Reads scorecard: "Root cause correct: Yes, Evidence reviewed: Yes, Verified: Yes, Hints: None, Score: 98/100."

**Reaction:** "If a recruiter sees this — they see structured thinking, SRE methodology, full chain awareness, and no hints. This is actually a strong portfolio piece."

**Finding:** At 9 achievements and 88% Strong with Cloud/DevOps alignment, this operator's recruiter dashboard represents the ceiling of what DiamOps can demonstrate. The portfolio is credible for a Senior Cloud Engineer or SRE application.

---

## End State

| Metric | Value |
|---|---|
| Cases closed | 12 |
| Average score | 89/100 |
| Achievements | 9 |
| Role affinity | Cloud/DevOps: Strong (94/100) |
| Recruiter readiness | 88% — Strong |
| Career path progress | Cloud/DevOps → Advanced milestone |
| Progression timeline events | 18 |

---

# Operator 04 — Cloud/DevOps — Findings

---

## What Worked Well

### 1. Infrastructure Ticket Realism — Platform Trust Gate
The ECS/CloudWatch/Kubernetes ticket content was accurate enough to pass a 3-year AWS engineer's scrutiny on the first case. This is the most critical trust gate for the Cloud/DevOps archetype. Without this, the operator would disengage.

### 2. Near-Perfect Score Is Achievable
Case 5 scored 98/100. This demonstrates the scoring rubric isn't arbitrarily capped. A perfect investigation (full evidence, chain-aware notes, correct root cause, no hints, verified) gets very close to maximum — which is the correct behaviour for a realistic scoring system.

### 3. Chain Documentation Rewards Properly
The `chain_investigator` achievement requires documented chain awareness in notes (not just opening the related incidents panel). The operator wrote full chain context and the achievement correctly fired.

### 4. Recruiter Portfolio at 9 Achievements
The 9-achievement recruiter profile is the showcase ceiling state. The `queue_recovery` achievement label is directly usable in a recruiter narrative: "Resolved a Critical ticket during high-pressure queue surge." This is an example of achievement language that is professional and evidence-linked.

### 5. Progression Timeline at 18 Events
At 18 timeline events, the progression timeline is visually rich and tells a coherent career narrative. The variety of event types (score jumps, new domains, achievements, milestones) creates a convincing operational history.

---

## Issues Found

### Issue 1 — No Triage Priority Ordering in Queue (MEDIUM)
**Description:** The SRE operator correctly identified that P1 tickets should be triaged first during surge, but the queue doesn't surface them at the top. The operator had to manually scan for P1s.

**Impact:** Under surge conditions, the queue layout doesn't support professional triage behaviour.

**Recommendation:** During surge state, add a "Priority sort" indicator to the queue: automatically surface P1/Critical tickets at the top of the queue during surge banner states.

### Issue 2 — Score Ceiling Ambiguity (LOW)
**Description:** After scoring 97 and 98, the operator asked "can I hit 100?" The platform doesn't communicate what the maximum represents or whether 100/100 is achievable.

**Impact:** Operators optimising for score may not know if they're at ceiling or if there's still room to improve.

**Recommendation:** Add a micro-tooltip on the scorecard: "100/100 reflects a complete investigation with all evidence reviewed, verified root cause, full documentation, and no hints used." This makes the ceiling legible without being a target to game.

### Issue 3 — GitOps/ArgoCD Ticket Realism (MINOR)
**Description:** The ConfigMap out-of-sync ticket was plausible but the evidence items didn't include ArgoCD-specific terminology (sync status, App health, Application CRD state). The operator noted: "This is right but feels slightly generic — real ArgoCD incidents have specific terminology."

**Impact:** Minor realism gap for GitOps-native operators. Most users won't notice.

**Recommendation:** Review Cloud/DevOps ticket evidence items for GitOps, SRE, and container-native terminology accuracy. Low priority but adds realism depth for senior operators.

---

## Validation Outcomes

| Test | Pass/Fail | Notes |
|---|---|---|
| Cloud/infrastructure ticket realism | PASS | ECS, K8s, Terraform, CI/CD all accurate |
| Near-perfect score achievable | PASS | 98/100 case 5 |
| chain_investigator fires on documented chains | PASS | Case 5, chain context in notes |
| queue_recovery fires during surge | PASS | Case 9, HIGH surge state active |
| documentation_excellence fires | PASS | After consistent deep-note cases |
| 9 achievements displayable in recruiter | PASS | All 9 shown correctly |
| Role affinity Cloud/DevOps at ceiling | PASS | 94/100 Strong |
| Recruiter readiness maximum state | PASS | 88% — Strong |
| Progression timeline 18 events | PASS | All event types represented |
| Advanced AI RCA output accurate | PASS | Evidence confidence rows trusted |
