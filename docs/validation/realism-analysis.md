# Operational Realism Analysis

**Validation date:** 2026-05-28  
**Operators tested:** 5  
**Scope:** Incident content accuracy, evidence quality, consequence accuracy, environmental context  

---

## Summary

Operational realism is the platform's strongest dimension. All five operators accepted the incident content as credible — with the Cloud/DevOps operator (the most technically demanding) explicitly validating the AWS/Kubernetes ticket accuracy. The conflicting evidence and red herring systems work as intended. Environmental context badges are read and acted on. Consequence flags are accurate.

**Operational Realism Score: 94/100**

---

## Incident Content Realism

### Ticket Content Assessment by Category

| Category | Archetype tested | Operator verdict | Score |
|---|---|---|---|
| Security / SOC | Operator 02 | "Accurate — pattern matches real MSSP alerts" | 9/10 |
| Cloud / AWS / Kubernetes | Operator 04 | "ECS, OOMKilled, Container Insights all accurate" | 9/10 |
| Infrastructure / Network | Operators 01, 03 | "Standard enterprise infrastructure — correct" | 8/10 |
| IT Support / Helpdesk | Operators 01, 05 | "Realistic password resets, printer issues" | 8/10 |
| GitOps / DevOps tooling | Operator 04 | "Plausible but missing ArgoCD-specific terminology" | 7/10 |

### Overall ticket content realism: 8.2/10

---

## Evidence System

### Red Herring Detection
- Operator 02 detected red herring on case 2 unprompted. Correct identification confirmed at completion reveal.
- Operator 04 detected misleading evidence item on case 7 (CI/CD pipeline).
- Operators 01, 03, 05 did not encounter red herrings (Beginner-tier tickets use standard evidence only).

**Red herring system: 10/10** — Works exactly as designed. Detection confirmation loop reinforces trust.

### Conflicting Evidence (Advanced Tier)
- Operators 02 and 04 both encountered conflicting evidence items on P1/Critical tickets
- Both identified and documented the conflict in their investigation notes
- Post-close reveal was accurate and credible in both cases

**Conflicting evidence system: 10/10**

### Evidence Depth by Tier
- Beginner tickets: 4–6 evidence items, clearly labelled, no adversarial content
- Intermediate tickets: 6–8 items, mixed signal quality, mild red herrings possible
- Advanced/Critical tickets: 8–10 items, deliberate conflicting signals, red herrings seeded

**Tier calibration: 9/10** — Appropriate escalation in evidence complexity.

---

## Environmental Context

### Environment Badge Assessment
All environment archetypes encountered across 5 operators:

| Environment | Encountered by | Badge shown | Tone note shown | Operator responded |
|---|---|---|---|---|
| Production — High escalation | Operators 02, 04 | Yes | Yes | Yes |
| DR Site — SOC 2 context | Operators 02, 04 | Yes | Yes | Yes |
| Dev/Test — Low risk | Operator 03 | Yes | No (beginner) | N/A |
| Corporate network | Operators 01, 03 | Yes | No (beginner) | N/A |

**Environment badge system: 9/10** — Colour coding, escalation tone notes, and SLA labels all function correctly.

---

## Incident Chain Realism

### Chain Discovery and Usage
- Operator 02: Discovered chains on case 4 (service account → SMTP downstream). Documented.
- Operator 04: Discovered chains on case 5 (node disk pressure → pod eviction → API downstream). Full chain documented.
- Operator 03: Noticed chains panel on case 6 but didn't document chain context.
- Operators 01, 05: Beginner-tier — chains not surfaced.

**Chain system: 9/10** — Chains are discovered naturally by operators who are looking for depth. Not intrusive for operators who don't.

---

## Consequence System

### Consequence Flag Accuracy

All 5 operators tested across multiple consequence scenarios:

| Consequence | Fired correctly | Over-fired | Under-fired |
|---|---|---|---|
| Notes lack specificity | 11/11 cases where applicable | 0 | 0 |
| Insufficient evidence review | 9/9 cases | 0 | 0 |
| Verification skipped | 14/14 cases | 0 | 0 |
| No actions on high-priority | 2/2 cases | 0 | 0 |

**Consequence accuracy: 10/10** — Zero false positives or false negatives in test population.

### Consequence Flag Usability
- Flags are readable and visible
- Operators 01, 02, 03 all changed behaviour after reading flags
- Operator 05 read flags but found them insufficiently actionable (confirmed as UX issue, not accuracy issue)

---

## Operational Pressure Realism

### Queue Surge State
- Surge state fired for Operators 02, 03, and 04 during their sessions
- All three operators responded to the surge banner in ways consistent with their real-world behaviour
- Surge state correctly elevated presence strip to "High operational pressure"

### SLA Risk Indicators
- SLA at risk indicators fired on 3 tickets across 5 operators
- Operator 03 (MSP archetype) responded most strongly to SLA risk — consistent with archetype
- Operator 04 prioritised P1s during surge — correct SRE triage behaviour

**Operational pressure system: 9/10**

---

## Shift Digest

Not triggered during this validation session (requires ≥3h absence between sessions). Confirmed present in code; activation is session-timing dependent.

---

## Realism Gaps Identified

### Gap 1 — GitOps Terminology Depth (LOW)
Kubernetes/ArgoCD tickets are plausible but don't include App-level health status, sync status, or Application CRD terminology. Noted by Operator 04.

### Gap 2 — False Positive Investigation Rubric (MEDIUM)
The scoring rubric doesn't distinguish between confirmed-incident investigations and false-positive investigations. SOC analysts closing FP tickets may be under-scored against criteria designed for confirmed incidents.

### Gap 3 — Time-to-Resolution Not Captured (LOW)
Investigation duration is not a platform signal. SRE and NOC operators who value speed would benefit from seeing investigation time as a soft metric in their operational profile.

---

## Realism Scorecard

| Dimension | Score |
|---|---|
| Ticket content accuracy | 82/100 |
| Evidence system (red herrings, conflicting) | 96/100 |
| Environmental context badges | 90/100 |
| Incident chain depth | 88/100 |
| Consequence accuracy | 98/100 |
| Queue pressure realism | 90/100 |
| **Overall realism** | **91/100** |
