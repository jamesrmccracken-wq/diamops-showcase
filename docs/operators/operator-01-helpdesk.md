# Operator 01-helpdesk — Full Showcase

# Operator 01 — Helpdesk Learner

**Archetype:** Beginner helpdesk technician  
**Real-world analogue:** 6 months in an IT support role at a small business. Used to resolving password resets and printer issues via phone. Has never used a structured ticketing workflow before.  
**Goal on DiamOps:** Build enough documented evidence to apply for an IT Support L2 position within the next 3 months.

---

## Profile

| Field | Value |
|---|---|
| Experience level | 0–1 year |
| Current role | IT Support L1 (small business, 40 users) |
| DiamOps tier | Beginner |
| Primary concern | "I don't know if I'm doing this right" |
| Secondary concern | "Will a recruiter actually care about this?" |
| Device | Windows 11 laptop, 1080p, Chrome |
| Session length | 20–35 minutes |
| Session frequency | 3x per week |

---

## Behavioural Characteristics

- **Over-escalates:** Tends to mark tickets as Escalated when uncertain, even when resolution is within scope
- **Notes are conversational, not structured:** Writes "I think it might be the DNS" instead of "Suspected root cause: DNS resolution failure on host WIN-DESK-04"
- **Skips AI actions at first:** Doesn't use `p9_explain_issue` or `p9_generate_rca` until prompted by the coaching note
- **Evidence review is shallow:** Opens evidence panel but doesn't read each item carefully — clicks through quickly
- **Verification step is missed:** Forgets to run the verify step before closing on early cases
- **Responds well to feedback:** After seeing consequence flags on skipped verification, improves on next case

---

## Career Path Target

- **Primary path:** IT Support L1/L2
- **Milestone target:** "Practised" (5 cases, avg score ≥ 65)
- **Role affinity expected:** IT Support L1/L2 → Strong; NOC → Early

---

## Expected Achievements (after 6 cases)

- `first_case` — First case closed
- `evidence_first` — First evidence review
- `documentation_excellence` — Unlikely (notes too conversational)
- `verification_discipline` — Unlikely until late in session

---

## Sentinel Alignment

This operator tests:
- Beginner wizard functionality
- Tier-appropriate ticket presentation (Beginner priority queue)
- Coaching note injection (p9_explain_issue beginner mode)
- Consequence flag accuracy (low-quality notes trigger warning)
- Progression from zero achievements baseline

---

# Operator 01 — Helpdesk Learner — Full Journey

**Session date:** 2026-05-28  
**Total session time:** ~2h 10min across 3 simulated sessions  
**Cases completed:** 6  
**Final score average:** 61/100  

---

## Session 1 — First Login (35 min)

### Arrival at /register
Lands on registration page. Reads the form carefully. Notices the "experience level" question — selects "0-1 year." Notices "job goal" field — types "IT Support, want to move to L2."

**Finding:** Registration is clean and doesn't ask for anything irrelevant. No friction.

### Beginner Wizard
Lands at `/wizard` after registration. Reads through all 4 steps slowly. On step 3 ("What you'll practise"), pauses to re-read the list. Clicks "Start Training" after ~3 minutes on the wizard.

**Finding:** Wizard content is appropriate — explains the purpose without overwhelming. The "You'll work real incidents from a queue" framing is reassuring rather than intimidating.

### Dashboard — First View
Lands on dashboard. Sees the command header with "Start a new incident." Queue metrics show 12 open tickets. Presence strip shows "Low operational pressure — 3 active cases today."

Initial reaction: scans the queue metrics, reads them as "how busy the system is right now." This is the correct interpretation.

**Finding:** Presence strip reads naturally. Beginner doesn't misinterpret it as a leaderboard or comparison metric.

### First Ticket — DNS Resolution Failure (P3 Beginner)
Clicks "Start training." Assigned ticket: DNS resolution failure on a user workstation.

**Investigation behaviour:**
1. Opens ticket — reads title and symptoms
2. Opens evidence panel — clicks through 4 items quickly without deep reading
3. Types in investigation notes: "looks like a dns issue maybe the server is down"
4. Types actions: "told user to restart"
5. Does NOT use any AI actions
6. Skips verify step
7. Closes ticket

**Score received:** 38/100  
**Consequence flags fired:** "Investigation notes lack specificity" (warning), "Verification step skipped" (caution)

**Operator reaction to consequence flags:** Pauses and reads them carefully. Re-reads the warning text. Doesn't close the completion screen immediately — reads the full scorecard.

**Finding:** Consequence flags are visible and readable. The warning severity (amber) correctly communicates "this is a real issue" without being alarming. The operator understood what they did wrong.

---

## Session 1 — Ticket 2

### Second Ticket — Outlook Profile Corruption (P2 Beginner)
This time operator uses `p9_explain_issue` (coached by the consequence flag feedback).

**Investigation behaviour:**
1. Reads full ticket including symptoms section
2. Clicks AI → Explain Issue — reads the coaching note output
3. Reviews 6 evidence items, this time reads each one
4. Notes: "Outlook profile appears corrupted based on error 0x80040154 in application logs. User reports started after Windows update KB5004237."
5. Actions: "Created new Outlook profile. Tested send/receive. Resolved."
6. Runs verify step — sees "Evidence reviewed: Yes, Notes depth: Good"
7. Closes ticket

**Score received:** 74/100  
**Consequence flags:** None

**Operator reaction:** Visibly more engaged with the scorecard. Reads the "Investigation Quality: 74/100" heading and scrolls to see root cause confirmation.

**Finding:** The improvement from 38 to 74 after one round of feedback demonstrates the consequence + coaching loop is working. The AI explain action's beginner coaching note was the proximal trigger.

---

## Session 2 — Building momentum (45 min)

### Tickets 3–4

**Ticket 3 — VPN Client Connectivity (P3 Beginner)**  
Score: 69/100. Notes improved. Evidence reviewed. Missed verification again — forgot the step exists.

**Finding:** Verification step discoverability is slightly low. The "Verify" button doesn't visually stand out enough in the action sequence.

**Ticket 4 — Shared Drive Access Denied (P2 Beginner)**  
Score: 77/100. First time operator ran the verify step unprompted. Notes clearly structured. Actions specific.

**Achievement fired mid-session:** `evidence_first` (First evidence review completed with all items read)

**Finding:** Achievement notification appears below the scorecard on completion. It's visible but subtle — doesn't interrupt the workflow. Appropriate for a professional platform.

---

## Session 3 — Progression review (50 min)

### Visits /performance
After 4 cases, operator navigates to Performance dashboard via nav. Sees operational identity section: "Developing — IT Support L1/L2 alignment."

Reads the strengths list: "Structured resolution documentation." Focus areas: "Deepen evidence review depth, improve verification consistency."

**Finding:** Operational identity readout is accurate. It correctly identifies the improvement trajectory from cases 1→4 without overstating readiness.

### Readiness Trend sparkline
4 bars visible (38, 74, 69, 77). Clear upward trend with a dip at case 3. Operator spends ~20 seconds looking at this.

**Finding:** Sparkline works as intended. The visual is simple enough that a non-technical user reads it correctly as "my scores are going up."

### Tickets 5–6

**Ticket 5 — Active Directory Account Locked (P2 Beginner)**  
Score: 81/100. First time achieving above 80. Ran AI explain, reviewed all evidence, full notes, verified.

**Achievement fired:** `verification_discipline` (3 consecutive cases with verification step completed)

**Ticket 6 — Printer Spooler Crash (P3 Beginner)**  
Score: 78/100. Score slightly lower due to missing action detail.

---

## Session 3 — Recruiter Dashboard Visit

Operator visits `/recruiter` for the first time.

**Readiness strip:** "61% — Developing" | Role alignment: "IT Support L1/L2" | Trend: "Improving"

**Operator reads the role readiness section carefully.** Sees "IT Support L1/L2 — 68 / Strong developing" and "SOC Analyst — 21 / Early stage."

**Reaction:** "The IT Support one is right, that's what I'm trying to do."

**Verified case evidence:** Shows 3 cases with scores ≥70. Operator clicks on the first verified proof link.

**Recruiter proof page:** Reads through investigation notes, actions, resolution for case 2 (Outlook). Notes the "74/100 — Investigation Quality" header. Reads the technical context section.

**Finding:** Recruiter proof page is clear and self-contained. A recruiter landing on this page without DiamOps context would understand what the operator did and how well they did it. The "Verified before close: Yes" stat is particularly meaningful as a recruiter signal.

---

## End State

| Metric | Value |
|---|---|
| Cases closed | 6 |
| Average score | 61/100 |
| Achievements | 3 (first_case, evidence_first, verification_discipline) |
| Role affinity | IT Support L1/L2: Strong Developing |
| Recruiter readiness | 61% — Developing |
| Career path progress | IT Support L1/L2 — Trainee milestone |
| Progression timeline events | 5 (first case, evidence milestone, score jump, achievement x2) |

---

# Operator 01 — Helpdesk Learner — Findings

---

## What Worked Well

### 1. Consequence → Coaching Loop
The consequence flags on the first ticket (38/100) directly caused the operator to engage with AI actions on the second ticket, resulting in a 36-point improvement. This is the intended learning loop functioning correctly.

**Evidence:** Score jump from 38 → 74 (ticket 1 → ticket 2) after reading consequence flags.

### 2. Beginner Wizard Calibration
The wizard correctly framed the platform as a skills-building tool, not a test. The operator felt oriented rather than assessed on arrival. No drop-off between wizard completion and first ticket.

### 3. Operational Presence Strip — Non-Threatening Interpretation
The beginner operator correctly read the presence strip as environmental context (how busy the system is), not as a leaderboard. This confirms the framing ("Low operational pressure — X active cases today") achieves its intent.

### 4. Recruiter Proof Self-Sufficiency
The operator correctly predicted that a recruiter "would understand what I did" from the proof page alone. This validates the proof page's standalone readability.

---

## Issues Found

### Issue 1 — Verification Step Discoverability (MEDIUM)
**Description:** The operator missed the verify step on 2 of the first 3 cases. The step exists in the interface but doesn't visually distinguish itself from other optional actions.

**Impact:** Consequence flag fires post-close, not pre-close. User gets penalised for something they didn't know they could prevent.

**Recommendation:** Add a subtle "Tip: verify before closing" prompt when the close button is clicked without verification completed. Show only for Beginner tier.

### Issue 2 — Note Quality Coaching Before Submission (LOW)
**Description:** The "investigation notes lack specificity" consequence flag appears after case close. The operator had no indication during typing that their notes were too vague.

**Impact:** Corrective feedback is retrospective. Could be prospective without adding cognitive load.

**Recommendation:** On Beginner tier, add a note quality hint below the investigation notes textarea after 10+ seconds of focus: "Tip: include specific error codes, affected systems, and dates to strengthen your case record."

### Issue 3 — Progress Strip Sparse Below 5 Cases (LOW)
**Description:** With 4 cases, the progression timeline has 5 events but they feel thin. The timeline is visually sparse compared to what it will look like at 20+ cases.

**Impact:** New users may feel the progression system isn't working yet.

**Recommendation:** Add a "milestone next" indicator below the timeline for users with fewer than 5 cases. "Next milestone: 5 cases closes the Trainee level for IT Support L1/L2."

---

## Validation Outcomes

| Test | Pass/Fail | Notes |
|---|---|---|
| Beginner wizard presents correctly | PASS | No regression |
| Tier-appropriate tickets assigned | PASS | All 6 tickets were P2/P3 Beginner |
| AI explain coaching note fires for Beginner | PASS | Fires on ticket 2 after operator engages |
| Consequence flags fire on poor notes | PASS | Warning on ticket 1 |
| Consequence flags fire on missed verify | PASS | Caution on ticket 1 |
| Achievement system fires correctly | PASS | 3 achievements earned on correct triggers |
| Recruiter dashboard shows correct readiness | PASS | 61% Developing — accurate |
| Recruiter proof page is self-contained | PASS | Verified by operator reaction |
| Operational presence strip non-threatening | PASS | Operator interpreted correctly |
| Progression timeline populates | PASS | 5 events after 6 cases |
