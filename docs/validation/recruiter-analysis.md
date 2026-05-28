# Recruiter Validation Analysis

**Validation date:** 2026-05-28  
**Operators tested:** 5  
**Scope:** Recruiter dashboard readability, role readiness accuracy, proof page quality, portfolio differentiation  

---

## Summary

The recruiter dashboard (Phase 14) successfully differentiates between all five operator archetypes. The role readiness scoring is accurate — each operator's primary role alignment matches their real-world background. The verified proof pages are self-contained and readable without DiamOps context. The achievement language is professional and recruiter-appropriate.

**Recruiter Validation Score: 88/100**

---

## Recruiter Dashboard — Cross-Operator Comparison

| Operator | Readiness % | Label | Primary role | Role score | Achievements |
|---|---|---|---|---|---|
| 01 — Helpdesk | 61% | Developing | IT Support L1/L2 | 68/100 | 3 |
| 02 — SOC | 84% | Strong | SOC Analyst | 91/100 | 7 |
| 03 — MSP | 68% | Developing | IT Support L1/L2 | 74/100 | 4 |
| 04 — Cloud | 88% | Strong | Cloud/DevOps | 94/100 | 9 |
| 05 — Struggling | 34% | Early | IT Support L1/L2 | 28/100 | 1 |

**Finding:** The 5-operator spread from 34% to 88% demonstrates that the recruiter profile is genuinely sensitive to operator quality — it's not a participation trophy system.

---

## Role Readiness Accuracy

### Does the primary role match the operator's real-world background?

| Operator | Expected primary role | Actual primary role | Match |
|---|---|---|---|
| 01 | IT Support L1/L2 | IT Support L1/L2 | ✓ |
| 02 | SOC Analyst | SOC Analyst | ✓ |
| 03 | IT Support / NOC | IT Support L1/L2 (NOC close second) | ✓ |
| 04 | Cloud/DevOps | Cloud/DevOps | ✓ |
| 05 | IT Support L1 | IT Support L1/L2 | ✓ |

**Role accuracy: 5/5 correct primary alignments.**

### Does the secondary role make sense?

| Operator | Primary | Secondary | Makes sense? |
|---|---|---|---|
| 01 | IT Support | NOC | Yes — helpdesk → NOC is a natural progression |
| 02 | SOC | Cloud/DevOps | Yes — infrastructure-aware SOC analysts |
| 03 | IT Support | NOC | Yes — MSP generalist maps to both |
| 04 | Cloud/DevOps | SOC | Yes — security-aware cloud engineers |
| 05 | IT Support | (insufficient data) | N/A — only 3 cases |

**Secondary role accuracy: 4/4 meaningful secondaries (Operator 05 excluded).**

---

## Verified Proof Pages — Readability Assessment

All proof pages were assessed for standalone readability: "Could a recruiter understand this page without knowing what DiamOps is?"

### Operator 02 — Ransomware Precursor Case (96/100)

A recruiter landing on this proof page sees:
- Case title: "Ransomware Precursor Detection — Stage 2 Payload C2 Beacon"
- Investigation notes: "Conflicting evidence identified: AV success entry at 08:12 treated as artefact. Network logs confirm C2 beacon pattern at 08:31. Full IOC chain documented..."
- Scorecard: 96/100 | Root cause correct: Yes | Hints: None | Verified: Yes
- Technical context: "Stage-2 payload bypassed initial AV scan. Network egress monitoring confirmed C2 beacon."

**Assessment:** A recruiter reading this can answer: "Can this person investigate a security incident? Yes. Are their notes structured? Yes. Did they work independently? Yes (no hints). Was the investigation confirmed correct? Yes."

**Score: 9/10** — Very strong standalone value.

### Operator 04 — Kubernetes Pod Eviction Chain (98/100)

A recruiter sees:
- Case title: "Kubernetes Pod Eviction Loop — Upstream Node Disk Pressure Chain"
- Investigation notes (excerpt): "Root cause: Log volume accumulation on node-02 caused disk pressure, triggering eviction of dependent pods. Chain documented: TKT-0089 upstream (node disk pressure) → this ticket (pod eviction) → TKT-0091 downstream (service unavailable)."
- Scorecard: 98/100 | All flags: Yes | Hints: None

**Assessment:** An SRE hiring manager reading this sees runbook methodology, chain awareness, and a structured post-mortem approach. This is the strongest individual proof page in the validation.

**Score: 10/10** — Ceiling-level standalone value.

### Operator 01 — Outlook Profile Corruption (74/100)

A recruiter sees:
- Case title: "Outlook Profile Corruption — Authentication Failure Post-Update"
- Investigation notes: "Outlook profile appears corrupted based on error 0x80040154 in application logs. User reports started after Windows update KB5004237."
- Scorecard: 74/100 | Root cause correct: Yes | Hints: None | Verified: Yes

**Assessment:** For an IT Support L2 role, this demonstrates: correct error identification, change correlation (Windows update), and verification discipline. Adequate for the target role.

**Score: 7/10** — Appropriate for the application level.

---

## Achievement Language Assessment

All 12 achievement labels and descriptions reviewed for recruiter-appropriateness:

| Achievement | Label | Recruiter signal |
|---|---|---|
| first_case | First Operational Investigation | Participation — low signal |
| evidence_first | Evidence Review Completed | Investigation methodology — medium |
| root_cause_champion | Root Cause Champion | Diagnostic accuracy — high |
| verification_discipline | Verification Discipline | Process discipline — high |
| documentation_excellence | Documentation Excellence | Report quality — high |
| sla_guardian | SLA Guardian | Time management — high |
| incident_stabiliser | Incident Stabiliser | Pressure handling — high |
| escalation_specialist | Escalation Specialist | Judgment — medium |
| advanced_handler | Advanced Incident Handler | Complexity handling — high |
| cross_domain | Cross-Domain Practitioner | Breadth — medium |
| chain_investigator | Incident Chain Investigator | Systems thinking — high |
| queue_recovery | Queue Recovery Under Pressure | Prioritisation — high |

**Finding:** 8 of 12 achievements carry high recruiter signal. None use gamification language (no XP, points, levels, or coins). All are operationally grounded.

---

## Recruiter Dashboard UX

### Strengths
- Readiness strip is immediately scannable (one number, one label, one role, one trend)
- Role readiness grid shows all 4 roles with relative comparison — a recruiter can see breadth as well as depth
- "What this demonstrates" section in skills evidence is direct and recruiter-readable
- Progression timeline shows career growth trajectory — valuable for growth-hiring

### Issues

**Issue 1 — Readiness % Derivation Not Explained (MEDIUM)**  
Recruiters may wonder what the 88% is calculated from. No tooltip or footnote explains the inputs.  
Recommendation: Add "Based on X cases, Y achievements, investigation scores" micro-text below the readiness %.

**Issue 2 — Verified Case Evidence Grid — Score Context Missing (LOW)**  
The case grid shows title and score but not the case difficulty tier. An 84/100 on an Advanced/Critical ticket is very different from 84/100 on a Beginner ticket.  
Recommendation: Add a difficulty badge (Beginner / Intermediate / Advanced / Critical) to each verified case card.

**Issue 3 — No Share/Export Mechanism (OUT OF SCOPE for Phase 14)**  
Recruiters cannot visit the dashboard directly — it requires platform authentication. A read-only shareable link or PDF export is needed for real recruiter use.  
Recommendation: Phase 17+ feature. Add `/recruiter/public/<token>` read-only view.

---

## Recruiter Readiness Scorecard

| Dimension | Score |
|---|---|
| Role alignment accuracy | 96/100 |
| Readiness % differentiation | 90/100 |
| Proof page standalone readability | 88/100 |
| Achievement language professionalism | 94/100 |
| Dashboard UX | 82/100 |
| Cross-operator differentiation | 92/100 |
| **Overall recruiter validation** | **90/100** |
