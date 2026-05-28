# Operator 02-soc — Full Showcase

# Operator 02 — SOC Analyst

**Archetype:** Security Operations Centre analyst  
**Real-world analogue:** 2 years as a SOC Tier 1 analyst at an MSSP. Reviews alerts, triages events, escalates confirmed incidents. Familiar with evidence chains and log analysis. Looking to validate operational capability to apply for SOC L2 or IR roles.  
**Goal on DiamOps:** Build a portfolio that demonstrates structured investigation methodology and confidence with adversarial evidence.

---

## Profile

| Field | Value |
|---|---|
| Experience level | 2–3 years |
| Current role | SOC Analyst Tier 1 (MSSP) |
| DiamOps tier | Intermediate |
| Primary concern | "I need to show I can work high-pressure, adversarial incidents — not just helpdesk stuff" |
| Secondary concern | "I want to see if this platform is actually realistic or just a toy" |
| Device | Windows 11 workstation, dual monitor, Firefox |
| Session length | 45–60 minutes |
| Session frequency | 5x per week |

---

## Behavioural Characteristics

- **Evidence-obsessed:** Reviews every evidence item before forming a hypothesis. Sometimes gets stuck in analysis paralysis.
- **Over-documents root cause:** RCA notes are thorough but verbose — sometimes 300+ word notes for a P3 ticket.
- **Escalation discipline:** Rarely escalates without documented justification. When escalating, writes clear handover notes.
- **AI sceptic:** Doesn't use AI actions by default. Tests them to see if they're accurate before trusting them.
- **Looks for red herrings:** Specifically tests the conflicting evidence system — tries to identify which evidence items are misleading.
- **High-pressure comfortable:** Performs well during queue surge states. Doesn't panic at SLA warnings.
- **Demands accuracy:** If the platform's AI explanation is wrong or vague, notices immediately and loses trust.

---

## Career Path Target

- **Primary path:** SOC Analyst → Incident Responder
- **Milestone target:** Advanced (10 cases, avg score ≥ 82)
- **Role affinity expected:** SOC Analyst → Strong; Cloud/DevOps → Moderate; IT Support → Low

---

## Expected Achievements (after 11 cases)

- `first_case` — Yes
- `evidence_first` — Yes (evidence review is default behaviour)
- `root_cause_champion` — Yes (5+ correct root causes)
- `verification_discipline` — Yes (always verifies)
- `documentation_excellence` — Yes (notes depth always high)
- `advanced_handler` — Yes (handles Advanced/Critical tier tickets)
- `chain_investigator` — Likely (will investigate incident chains)
- `escalation_specialist` — Unlikely (rarely escalates)

---

## Sentinel Alignment

This operator tests:
- Intermediate/Advanced tier ticket variety (Security, Infrastructure, Critical incidents)
- Conflicting evidence system (chain_investigator, red herring reveal)
- AI action accuracy at Intermediate/Advanced tier (RCA with evidence confidence rows)
- Role affinity SOC scoring accuracy
- Recruiter dashboard differentiation from helpdesk operator

---

# Operator 02 — SOC Analyst — Full Journey

**Session date:** 2026-05-28  
**Total session time:** ~4h 30min across 5 simulated sessions  
**Cases completed:** 11  
**Final score average:** 84/100  

---

## Session 1 — Platform Evaluation (60 min)

### First Login — Direct to Intermediate
Registers with "2-3 years experience" and "SOC Analyst" goal. Lands on wizard. Reads quickly (~90 seconds). Notes the mention of "adversarial evidence and conflicting signals" — explicitly says "okay so there's red herrings, let me find one."

**Finding:** Intermediate-tier framing in the wizard correctly sets up the right operator mindset. The "adversarial evidence" language is appropriate and credible.

### Dashboard Assessment
Reads all queue metrics. Sees presence strip: "Moderate operational pressure — 7 active cases, 2 claimed." Immediately asks: "who claimed the 2? is that me or someone else?" — understands presence simulation within seconds.

**Finding:** Presence strip framing is correct but ambiguous for this operator. They understand it's simulated but want to know if "claimed" includes their own. This is a legitimate confusion point.

### Tickets 1–3 — Platform trust calibration

**Ticket 1 — Suspicious Authentication Activity (P2 Intermediate)**  
Spends 8 minutes reviewing evidence. Reads all 7 evidence items. Uses `p9_explain_issue` and reads the output critically: "that's accurate actually, it's not dumbed down." Runs RCA action: reads the "evidence confidence" output (X/Y supporting). Writes 180-word structured RCA note. Verifies. Closes.

Score: 91/100. Root cause correct: Yes.

**Reaction:** "Okay, the AI output is actually useful. It's not just generic advice."

**Finding:** The Advanced-tier AI action output (evidence confidence rows, chain context) earns credibility with the analytical operator. This is a trust gate that this operator passes at ticket 1.

**Ticket 2 — Network Scan Detection (P3 Intermediate)**  
Finds a conflicting evidence item: one log says "scan terminated at 14:32" and another says "outbound connection at 14:35." Tests whether the platform will flag this.

Writes in notes: "Conflicting evidence: scan termination log contradicts outbound connection at 14:35. Treating the 14:35 entry as potentially injected or artefactual. Proceeding on confirmed scan pattern."

Score: 88/100. Red herring reveal on completion: "Evidence item 'Scan terminated 14:32' was a misleading artefact seeded to test investigation discipline."

**Reaction:** "Right. That's exactly what a real SOC alert looks like. Good."

**Finding:** Red herring reveal at completion is well-received by SOC archetype. The confirmation that they correctly identified it reinforces trust in the platform's realism.

**Ticket 3 — Malware Execution Indicator (P1 Critical)**  
First Critical-tier ticket. Notices the environment badge: "Production — High escalation risk." Reads escalation tone note: "This system hosts payment processing. Escalation should include compliance context."

Adjusts escalation approach accordingly: escalates with compliance note.

Score: 82/100. Score slightly lower because operator escalated when resolution was possible within scope.

**Reaction:** "Fair — I over-escalated. I should have contained first. That's accurate feedback."

**Finding:** Critical-tier tickets correctly signal higher stakes. The escalation tone note is read and acted on. The lower score for an escalation that was possible to self-resolve is accurate and credible.

---

## Session 2 — Incident Chains (55 min)

### Tickets 4–6

**Ticket 4 — Service Account Password Expiry (P2 Intermediate)**  
Notices "Related incidents" panel in sidebar. One linked ticket: "Downstream: SMTP relay auth failure." Operator reads the relationship. Notes it in investigation: "This ticket is upstream of the SMTP auth failure on TKT-0047. Root cause affects both. Resolving at source."

Score: 94/100. Highest score yet. Chain investigator achievement fires.

**Reaction:** Sees the `chain_investigator` achievement in the completion summary. Reads description: "Identified and documented a linked incident chain." Responds positively.

**Finding:** Incident chain display in the sidebar is naturally discovered — the operator didn't need prompting. The achievement correctly fires on documented chain awareness.

**Ticket 5 — Endpoint Detection Alert — False Positive Assessment (P2 Intermediate)**  
Tests the `p9_summarise_evidence` action for the first time. Reads the "type breakdown + signal density" output. Notes: "4 network events, 2 registry writes, 0 process creates — low signal density, likely FP."

Closes as false positive with documented rationale.

Score: 89/100. False positive correctly identified.

**Finding:** Evidence summary with type breakdown and signal density is directly useful to a SOC analyst. This feature is used naturally without coaching.

**Ticket 6 — Directory Service Replication Failure (P3 Intermediate)**  
First cross-domain ticket (Infrastructure + Security overlap). Handles competently.

Score: 87/100. `cross_domain` achievement fires.

---

## Session 3 — Advanced Tier (50 min)

### Tickets 7–9

**Ticket 7 — Ransomware Precursor Detection (P1 Critical, Advanced)**  
Fully advanced-tier case. Red herring: "AV scan completed successfully at 08:12" — but outbound C2 beacon pattern is visible in network logs. Operator correctly disregards the AV success entry.

In completion reveal: "AV success entry was seeded — AV missed the stage-2 payload."

Score: 96/100. Best score of session.

**Achievement fired:** `advanced_handler` (5 Advanced/Critical tier cases completed)

**Ticket 8 — SSH Brute Force → Successful Authentication (P2 Advanced)**  
Queue is in surge state during this ticket. Surge banner shows: "HIGH — 14 unresolved cases, 3 SLA at risk." Operator reads surge banner, notes SLA state, and adjusts: deprioritises verbose notes slightly to handle the ticket faster.

Score: 81/100. Notes slightly thinner than usual.

**Finding:** Queue surge state is read and acted on correctly. The operator made the right trade-off (speed over documentation depth under surge) — this is realistic operational behaviour. Consequence flag fires for note depth — also correct.

**Ticket 9 — Insider Threat Indicator — File Exfiltration Pattern (P1 Critical)**  
Handles with full methodology. Long investigation notes (280 words). All evidence reviewed. Chain relationship documented.

Score: 93/100.

**Achievement fired:** `root_cause_champion` (10 correct root causes identified)

---

## Sessions 4–5 — Platform Depth Review (65 min)

### Tickets 10–11

**Ticket 10 — Zero Day Indicator — Unpatched Service Exploit (P1 Critical)**  
Escalates with compliance context (environment badge: "DR Site — regulatory SOC 2 context"). Full documentation. Escalation note structured for handover.

Score: 89/100. `documentation_excellence` achievement fires.

**Ticket 11 — Legacy System Vulnerability — End of Life OS Detection (P2 Advanced)**  
Final case. All skills applied. Complete investigation.

Score: 88/100.

---

## Recruiter Dashboard Assessment

Visits `/recruiter` after 11 cases.

**Readiness strip:** "84% — Strong" | Role alignment: "SOC Analyst" | Trend: "Stable at high performance"

**Role readiness section:**  
- SOC Analyst: 91/100 — Strong fit  
- Cloud/DevOps Engineer: 52/100 — Developing  
- IT Support L1/L2: 31/100 — Early stage  
- NOC Analyst: 44/100 — Developing  

**Operator reaction:** "SOC is right. Cloud makes sense too — I've done some cross-domain infrastructure work. IT Support being low is accurate, I don't do that work."

**Finding:** Role affinity scoring correctly differentiates a SOC-focused operator from the helpdesk operator. The relative scoring across all 4 roles is realistic.

**Verified case evidence:** 8 cases shown (score ≥ 70). Operator opens proof for the ransomware case (96/100). Reads through the investigation notes — they're exactly as written.

**Finding:** Proof pages accurately reproduce the operator's work. The scorecard showing "Root cause correct: Yes, Hints: None, Evidence reviewed: Yes" is a strong recruiter signal for analytical capability.

---

## End State

| Metric | Value |
|---|---|
| Cases closed | 11 |
| Average score | 84/100 |
| Achievements | 7 |
| Role affinity | SOC Analyst: Strong (91/100) |
| Recruiter readiness | 84% — Strong |
| Career path progress | SOC Analyst → Advanced milestone |
| Progression timeline events | 14 |

---

# Operator 02 — SOC Analyst — Findings

---

## What Worked Well

### 1. AI Action Credibility at Intermediate/Advanced Tier
The evidence confidence row in `p9_generate_rca` (Advanced tier) — showing "4/6 supporting evidence" — was the single most important trust-building element for this operator. They used it on case 1 and immediately formed a positive opinion of the platform's depth.

### 2. Red Herring System — Realism Validation
The conflicting evidence system (Phase 11/12) was correctly identified on ticket 2 without any prompting. The post-close reveal confirmed the operator's suspicion. This loop ("I suspected this was a red herring → confirmed at close") is the highest-realism feature in the platform for a SOC archetype.

### 3. Incident Chain Discovery
The related incidents panel was discovered naturally. The operator used it to document cross-ticket context on case 4. No prompting needed. The achievement fired on correct behaviour.

### 4. Role Affinity Accuracy
After 11 cases, role affinity produced a credible relative ranking. SOC Analyst at 91 vs IT Support at 31 is correct and credible. The operator validated this out loud.

### 5. Queue Surge State — Behavioural Shift
The surge banner caused a real behavioural change (slightly thinner notes on case 8). This is exactly what queue pressure is supposed to do. The consequence flag on that case was also correct.

---

## Issues Found

### Issue 1 — "Claimed" Presence Strip Ambiguity (LOW)
**Description:** The presence strip says "2 claimed" — the operator wanted to know if this includes their own claimed tickets or only others'. The simulated presence doesn't distinguish between self and ambient.

**Impact:** Minor confusion for technically sophisticated operators.

**Recommendation:** Change "X claimed" to "X under active investigation" to remove the self/other ambiguity. Or add a note: "(including yours if applicable)."

### Issue 2 — Analysis Paralysis Edge Case — No Timer (LOW)
**Description:** This operator spent 8 minutes on case 1 evidence review. At no point did the platform indicate that investigation time matters for operational realism. A real SOC analyst works under time pressure.

**Impact:** The platform doesn't capture time-to-resolution as a quality signal. Very methodical operators get the same score as fast operators.

**Recommendation:** Add an optional "time-aware" mode for Intermediate/Advanced tier that logs investigation duration as a soft signal in the progression profile. Not a hard penalty — just shown in the operational identity readout ("Average investigation time: X min").

### Issue 3 — False Positive Resolution Not Distinguished (MEDIUM)
**Description:** When closing a ticket as a false positive, the score and consequence logic work the same as for a confirmed incident. But the investigation notes for an FP are structurally different (you're documenting absence of evidence, not presence).

**Impact:** FP investigations might be under-scored because the standard evidence review and root cause criteria don't map cleanly to FP methodology.

**Recommendation:** Add a "False Positive" ticket outcome type that adjusts the scoring rubric — reward evidence exclusion rationale instead of root cause identification.

---

## Validation Outcomes

| Test | Pass/Fail | Notes |
|---|---|---|
| Advanced AI action output (evidence confidence rows) | PASS | Used and trusted on case 1 |
| Red herring system fires correctly | PASS | Detected on case 2, confirmed at close |
| Incident chain panel displays | PASS | Discovered naturally on case 4 |
| Critical tier environment badge shows | PASS | Read and acted on in case 3 |
| Escalation tone note shows for Intermediate+ | PASS | Shown on case 3, read and used |
| Queue surge banner fires | PASS | HIGH state on case 8 |
| Achievement chain_investigator fires | PASS | Fires on case 4 |
| Achievement advanced_handler fires | PASS | Fires on case 7 |
| Role affinity SOC scoring accurate | PASS | 91/100 SOC vs 31/100 IT Support |
| Recruiter dashboard differentiates from Operator 1 | PASS | 84% Strong vs 61% Developing |
