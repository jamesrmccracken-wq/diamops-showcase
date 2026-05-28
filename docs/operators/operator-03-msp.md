# Operator 03-msp — Full Showcase

# Operator 03 — MSP Operator

**Archetype:** Fast-paced Managed Service Provider technician  
**Real-world analogue:** 18 months at an MSP managing 12 client environments. Works 30–50 tickets per day. Speed is valued over depth. Documentation is "good enough to be billed, not to be read." SLA compliance is everything — misses mean client escalations.  
**Goal on DiamOps:** Demonstrate operational throughput capability. Wants to show they can handle volume and pressure. Considering a NOC analyst role at a larger company.

---

## Profile

| Field | Value |
|---|---|
| Experience level | 1–2 years |
| Current role | MSP Technician (generalist) |
| DiamOps tier | Intermediate |
| Primary concern | "I work fast — I need to show I can handle real volume" |
| Secondary concern | "Documentation is slow. I want to get through cases." |
| Device | Windows 10 laptop, 1080p, Chrome |
| Session length | 30–45 minutes |
| Session frequency | 4x per week |

---

## Behavioural Characteristics

- **Speed-first:** Aims to close tickets as fast as possible. Reads only the first 2–3 evidence items
- **Action-oriented:** Goes straight to actions without full investigation notes
- **SLA-aware:** Watches the SLA risk indicator actively
- **Weak documentation:** Notes are 1–2 sentences. Rarely reaches the depth required for `documentation_excellence`
- **Verification inconsistent:** Sometimes verifies, sometimes doesn't — depends on whether they notice the button
- **Escalation as tool:** Escalates to clear their queue, not because of genuine severity uncertainty
- **Queue surge energises:** Performs faster (not worse) under surge — treats high-pressure as normal operating state

---

## Career Path Target

- **Primary path:** NOC Analyst
- **Milestone target:** Practised (5 cases, avg score ≥ 65)
- **Role affinity expected:** NOC Analyst → Moderate; IT Support → Strong; SOC → Low

---

## Expected Achievements (after 9 cases)

- `first_case` — Yes
- `evidence_first` — Yes (opens evidence, even if shallow)
- `sla_guardian` — Likely (closes cases before SLA breach)
- `incident_stabiliser` — Possible (resolves high-priority tickets)
- `documentation_excellence` — Unlikely
- `verification_discipline` — Unlikely

---

## Sentinel Alignment

This operator tests:
- SLA risk indicator accuracy
- Consequence flags for thin documentation
- Queue surge response (does surge state display correctly at high volume?)
- Operational presence strip under active load
- Role affinity for non-SOC, non-Cloud archetype

---

# Operator 03 — MSP Operator — Full Journey

**Session date:** 2026-05-28  
**Total session time:** ~2h 45min across 4 simulated sessions  
**Cases completed:** 9  
**Final score average:** 68/100  

---

## Session 1 — Speed Run (35 min)

### Dashboard
Skips wizard quickly (2 minutes). Lands on dashboard. Immediately scans queue metrics: "14 open, 3 SLA at risk." Goes straight to "Start training."

**Finding:** The queue metrics dashboard is immediately actionable for this operator type. They don't need orientation — they need a queue to clear.

### Ticket 1 — Network Switch Unresponsive (P2 Intermediate)
Total time in ticket: 4 minutes.

1. Opens ticket, reads title only
2. Opens evidence panel, reads items 1 and 2 of 6
3. Notes: "Switch rebooted, back up"
4. Actions: "Remote power cycle via IPMI. Device responding."
5. Does NOT verify
6. Closes

Score: 52/100. Consequence flags: "Investigation notes lack specificity (warning)," "Insufficient evidence review (caution)," "Verification step skipped (caution)."

**Reaction:** Reads consequence flags briefly. "I knew I should have read more evidence. But this is how I work in the real world — I don't have time for 400-word notes."

**Finding:** This is a realistic and valid tension. The platform should acknowledge the trade-off rather than simply penalising for speed. The consequence flags are correct, but they read as "you failed" rather than "here's what a stronger case file looks like."

### Ticket 2 — DHCP Pool Exhaustion (P3 Intermediate)
Total time: 5 minutes. Slightly more effort after consequence flag.

Notes: "DHCP pool at 100%. Expanded scope from /24 to /23."  
Actions: "Expanded DHCP scope. Added additional lease exclusions. Confirmed pool back to 40% utilisation."  
Evidence: 3/5 items read. No verify.

Score: 63/100. "Investigation notes: adequate" (no consequence flag on notes). Still missing verify.

**Finding:** The 10-point score improvement from reading one more note validates the scoring rubric is sensitive enough to reward incremental improvement.

### Ticket 3 — SLA at Risk — Storage Capacity Alert (P2 Intermediate)
SLA warning visible on ticket header: "This ticket has 45 minutes remaining before SLA breach."

Operator closes the ticket in 6 minutes. SLA met.

`sla_guardian` achievement fires on completion.

**Finding:** SLA risk indicator on individual tickets (not just the dashboard) is directly useful to MSP archetype. The achievement firing on SLA compliance without breach is the correct trigger — it rewards time-conscious behaviour.

---

## Session 2 — Surge State Testing (40 min)

### Queue surge activates
Between sessions, queue state has changed. Dashboard shows surge banner: "HIGH — 16 unresolved, 4 SLA at risk." Presence strip: "High operational pressure — 9 active cases today, 3 escalations."

Operator reaction: "Good — this is what I'm used to. Let's go."

**Finding:** Surge state is energising for this operator type. This is accurate to MSP culture.

### Tickets 4–6

**Ticket 4 — VPN Gateway Authentication Failure (P1 High)**  
First P1 ticket. Operator reads the full ticket because "P1 means it's billable at a higher rate — I need to document."

Notes: 3 sentences. Evidence: 4/6 items. Verify: YES (first time).

Score: 71/100. First time above 70.

**Finding:** Billing incentive framing (even when internally applied by the operator) produces better documentation. The platform doesn't address billing, but the P1 priority label triggers the right behaviour change.

**Ticket 5 — Backup Job Failure — Off-Site Replication (P2 Intermediate)**  
Score: 65/100. Average effort.

**Ticket 6 — Hypervisor Host Memory Pressure (P2 Intermediate)**  
Reads related incidents sidebar — there's a linked ticket. Doesn't document it but notices it.

Score: 69/100.

---

## Session 3 — Documentation Coaching (30 min)

After session 2, operator reads their operational identity on `/performance`. Sees: "Focus area: Investigation documentation depth."

Makes a deliberate decision to improve notes on next cases.

### Tickets 7–8

**Ticket 7 — DNS Poisoning Indicator (P2 Intermediate)**  
Structured notes: "Symptoms: DNS lookups returning incorrect IPs for internal hosts. Evidence: DNS cache poisoning pattern confirmed in logs (items 1, 3, 4 reviewed). Unusual TTL values on internal zone."  
Actions: "Cleared DNS cache on all DCs. Audited zone records. Enabled DNSSEC validation."

Score: 79/100. Highest score yet.

**Finding:** The operational identity "focus areas" section is read and acted on. This is the intended loop: reflect → adjust → improve.

**Ticket 8 — Certificate Expiry on Load Balancer (P3 Intermediate)**  
Related incident visible: downstream HTTPS failures. Documented in notes.

Score: 76/100.

---

## Session 4 — Recruiter Review (60 min)

### Ticket 9 — SAN Storage Failover Event (P1 High)
Major case. Full documentation effort.

Notes: 5 structured sentences with affected systems, evidence mapping, and resolution confirmation.  
Score: 82/100. 

Achievement fired: `incident_stabiliser` (3 High/Critical priority tickets resolved)

### Recruiter Dashboard

**Readiness strip:** "68% — Developing" | Role alignment: "IT Support L1/L2 / NOC Analyst" | Trend: "Improving"

Role readiness:
- IT Support L1/L2: 74/100 — Developing (strong on throughput, gaps in documentation)
- NOC Analyst: 61/100 — Developing
- SOC Analyst: 29/100 — Early stage
- Cloud/DevOps: 22/100 — Early stage

**Operator reaction:** "NOC is right — that's what I want to do. IT Support being high makes sense too."

**Finding:** Role affinity for an MSP generalist correctly lands between IT Support and NOC — neither as strongly as a dedicated practitioner of either. This is realistic.

**Verified case evidence:** 5 cases shown (≥70). Fewer than Operator 02, but still a meaningful portfolio for the role applied for.

**Finding:** A 68% Developing profile with throughput focus and SLA compliance signal is a credible NOC candidate portfolio — different from the SOC operator's evidence but equally readable.

---

## End State

| Metric | Value |
|---|---|
| Cases closed | 9 |
| Average score | 68/100 |
| Achievements | 4 (first_case, evidence_first, sla_guardian, incident_stabiliser) |
| Role affinity | IT Support L1/L2: Developing · NOC: Developing |
| Recruiter readiness | 68% — Developing |
| Career path progress | NOC Analyst — Trainee |
| Progression timeline events | 8 |

---

# Operator 03 — MSP Operator — Findings

---

## What Worked Well

### 1. SLA Risk Signal Is Operationally Actionable
The SLA warning on individual tickets produced a direct behavioural response (faster close, still with adequate documentation). This is the correct outcome.

### 2. Surge Banner — Correct Emotional Register
For an MSP operator, high-pressure is normal. The surge banner's phrasing ("High operational pressure") doesn't cause anxiety — it causes engagement. The platform doesn't over-dramatise the surge state.

### 3. Operational Identity "Focus Areas" — Used
After reading the focus area "documentation depth," the operator explicitly changed behaviour on the next session. This validates the operational identity section as a practical coaching tool, not just a vanity metric.

### 4. Role Affinity — Correct Generalised Profile
MSP generalists land between IT Support and NOC rather than matching either cleanly. The scoring is realistic.

---

## Issues Found

### Issue 1 — Consequence Flag Tone for Speed-First Operators (MEDIUM)
**Description:** The consequence flags read as criticism ("Investigation notes lack specificity") without acknowledging the operational context. A real MSP tech isn't failing — they're making a time trade-off.

**Impact:** The flags are accurate but can feel punitive. An operator who knows why they did something might disengage from the feedback loop if it feels moralistic.

**Recommendation:** Add a "context-aware" variant for Intermediate tier: "For high-throughput environments, brief notes are realistic. For role progression proof, richer notes strengthen your recruiter case." Gives the operator agency rather than just criticism.

### Issue 2 — No Throughput Achievement (MEDIUM)
**Description:** There's no achievement for operational throughput (e.g., closing 5 tickets in one session, or 3 P1 cases in a week). This undervalues the MSP archetype's primary strength.

**Impact:** An MSP operator's recruiter profile shows fewer achievements than a SOC operator who takes twice as long per case, even though throughput is a valid and valued skill.

**Recommendation:** Add a `throughput_operator` achievement: "Closed 5 or more cases in a single session with average score ≥ 60." This rewards speed-with-quality without penalising the fast-paced working style.

### Issue 3 — Billing Context Not Surfaced (LOW)
**Description:** The P1 priority label triggered documentation improvement because the operator internally associated P1 with billing priority. But the platform doesn't surface the "this matters for client/evidence value" framing that MSP operators respond to.

**Impact:** The platform assumes IT department framing (severity = impact to org). MSP framing is severity = billing tier. Making both framings explicit would improve relevance for this archetype.

**Recommendation:** On P1 tickets, add a one-line environment context: "High-priority cases generate the strongest recruiter evidence — document thoroughly." (Currently this logic exists for Advanced tier AI actions but not for priority tier.)

---

## Validation Outcomes

| Test | Pass/Fail | Notes |
|---|---|---|
| Surge banner fires under load | PASS | HIGH state correctly shown |
| SLA risk indicator on individual tickets | PASS | 45-minute warning displayed |
| sla_guardian achievement fires | PASS | Fires on SLA-compliant close |
| incident_stabiliser achievement fires | PASS | Fires on 3rd High+ priority close |
| Operational identity focus areas shown | PASS | "Documentation depth" shown correctly |
| Role affinity NOC/IT Support for MSP | PASS | Both Developing — accurate |
| Recruiter readiness lower than SOC | PASS | 68% Developing vs 84% Strong |
| Consequence flags fire on thin docs | PASS | Warning on tickets 1 and 2 |
