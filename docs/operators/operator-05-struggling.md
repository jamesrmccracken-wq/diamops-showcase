# Operator 05-struggling — Full Showcase

# Operator 05 — Struggling User

**Archetype:** Confused and overwhelmed newcomer  
**Real-world analogue:** Just started using DiamOps after seeing it mentioned in a Discord server. No clear goal. Never worked in IT professionally. Curious but easily frustrated. Has a rough understanding of what tickets are from watching YouTube. Has not read any documentation.  
**Goal on DiamOps:** Unclear. Vaguely wants to "get into IT" but hasn't set a specific role target.

---

## Profile

| Field | Value |
|---|---|
| Experience level | None (student) |
| Current role | N/A |
| DiamOps tier | Beginner |
| Primary concern | "I don't know what I'm doing" |
| Secondary concern | "This is confusing" |
| Device | Windows 11 laptop, 1080p, Chrome |
| Session length | 10–20 minutes (high drop-off risk) |
| Session frequency | Irregular |

---

## Behavioural Characteristics

- **Skips documentation entirely:** Doesn't read ticket symptoms. Opens ticket, immediately starts typing notes
- **Notes are personal reactions, not observations:** "idk what this is, tried restarting it"
- **Actions are guesses:** "Googled it. Tried turning it off and on again."
- **Doesn't use evidence panel:** Doesn't know it exists
- **Never verifies:** Doesn't know what verification means in this context
- **Misreads the queue metrics:** Thinks "12 open" means "12 things broke today because of something I did"
- **Gets confused by the activity drawer:** Opens it, reads the timeline entries, doesn't understand what they represent
- **Escalates everything:** Marks everything as Escalated when uncertain
- **Reads achievement notifications with curiosity:** The first achievement fires and they spend time reading the description

---

## Career Path Target

- **None set** — user hasn't configured a path
- **Role affinity expected:** No meaningful affinity — not enough cases for signal

---

## Expected Outcomes (after 3 cases)

- `first_case` — Yes (after closing case 1, regardless of quality)
- Everything else: No
- Score range: 18–35/100

---

## Sentinel Alignment

This operator tests:
- Does the platform handle very low-quality submissions gracefully?
- Does the consequence flag system help or confuse struggling users?
- Is the beginner wizard enough to orient a complete newcomer?
- What is the minimum meaningful engagement state?
- Does the empty-state portfolio page show a useful "what next" prompt?

---

# Operator 05 — Struggling User — Full Journey

**Session date:** 2026-05-28  
**Total session time:** ~45 min (single session with long idle periods)  
**Cases completed:** 3  
**Final score average:** 27/100  

---

## Session — Single Fragmented Visit (45 min)

### Registration
Types email and password. Selects "None / Just starting" for experience. Leaves job goal blank. Clicks register.

**Finding:** Registration allows blank job goal. No friction, no required field. This is correct — forcing a goal from a user who doesn't know what they want would cause drop-off.

### Beginner Wizard
Lands on wizard. Reads first step ("Welcome to DiamOps — your operational training environment"). Reads second step ("You'll investigate real incident reports"). Gets to step 3 ("What you'll practise") and sees a bullet list of 8 items.

**Pause: 30 seconds.** Then clicks "Start Training" without reading the rest.

**Finding:** The wizard content is appropriate for informed beginners but may lose very casual users at step 3. The list of 8 practice items creates momentary overwhelm for someone with no IT background. Consider progressive disclosure — show 3 items with a "show more" option.

### Dashboard — First View
Sees queue metrics: "12 open · 3 SLA at risk · 2 claimed." Reaction: "3 things are broken already? Did I break them?"

Reads presence strip: "Low operational pressure — 3 active cases today." Doesn't understand what "operational pressure" means.

**Finding:** Two notable issues:
1. "SLA at risk" is misread as a personal failure indicator by a complete newcomer. Consider tooltip on SLA metric: "SLA = the time a case should be resolved by. Pre-existing cases, not related to your actions."
2. "Operational pressure" is jargon. For Beginner tier, simplify to: "3 cases are currently being worked in the system."

Clicks the first item in the activity feed — a recent ticket close event. Confused by the event structure.

---

### Ticket 1 — User Account Password Reset Request (P3 Beginner)

Opens ticket. Does NOT read symptoms section. 

Immediately clicks into "Investigation notes" field. Types: "the person cant login maybe their password is wrong"

Clicks into "Actions taken." Types: "reset their password"

Does NOT open evidence panel.  
Does NOT use AI actions.  
Does NOT verify.  
Clicks close.

**Score: 22/100.**  

Consequence flags:
- "Investigation notes lack specificity (warning)"
- "Insufficient evidence review (caution)"  
- "Verification step skipped (caution)"

**Operator reads consequence flags for 45 seconds.** Reads the warning: "Investigation notes lack specificity." Looks confused: "How do you be more specific about a password reset?"

**Finding:** This is the most important UX finding in the entire validation. For a complete newcomer, the consequence flag "notes lack specificity" assumes they know what specificity means in an IT investigation context. The flag fires correctly but the guidance is insufficiently actionable for this user type.

**Recommended fix:** Add an example to the flag. Instead of "Investigation notes lack specificity," show: "Investigation notes lack specificity. Example of good notes: 'User reported inability to authenticate to [system] since [date]. Event logs confirm authentication failure code 0x80004005. Suspected cause: expired password.'"

---

### Ticket 2 — Network Printer Offline (P3 Beginner)

Operator now tries harder. Has read the consequence flags.

Notes: "the printer is offline. i checked and it looks like the network cable might be disconnected"  
Actions: "told them to reconnect the cable. fixed."  
Evidence: Opens panel! Sees 4 items. Reads item 1. Closes panel.  
Verify: Still doesn't do it — doesn't know where the button is.

**Score: 31/100.** Slight improvement.

**Consequence flags:** "Insufficient evidence review (caution)" · "Verification step skipped (caution)" — notes warning did not fire this time.

**Finding:** 9-point improvement from reading 1 evidence item and slightly improving notes. The consequence feedback loop is working at a micro-scale even for a struggling user. But the verification step is still undiscovered.

**Verification step discoverability:** After case 2, the user explicitly says "what is verify? I don't see a button." This confirms the earlier finding from Operator 01: the verify button is not visually salient enough for new users.

---

### Ticket 3 — Browser Homepage Hijack (P3 Beginner)

Operator asks "what is root cause?" mid-investigation — referring to the AI hint button. Clicks `p9_explain_issue`. Reads the beginner coaching note. Follows 2 of the 3 suggestions.

Notes: "browser settings have been changed by malware or extension. checked installed extensions."  
Actions: "removed suspicious extension. reset browser settings. advised user to check downloads."  
Evidence: 3/5 items read.  
Verify: Still skipped.

**Score: 39/100.**

**Achievement fired:** `first_case` (technically fires on case 1, but first acknowledgement here)

The operator reads the achievement notification: "First case resolved. You've completed your first operational investigation." Pauses and reads carefully. "Wait — I got something for that?"

**Finding:** The achievement fires on any case close, regardless of quality. This is correct — it rewards participation and creates positive reinforcement even for a struggling user. The professional language ("First operational investigation") frames it as meaningful without being condescending.

---

### Performance Dashboard Visit

After case 3, operator clicks "Performance" in the nav.

Sees operational identity: "Developing — IT Support L1/L2 alignment."  
Strengths: (none listed — insufficient cases for strong signals).  
Focus areas: "Increase evidence review depth, improve verification consistency."

Reads focus areas. "I didn't review enough evidence. And I still don't know how to verify."

**Finding:** The focus areas are accurate but the "how to verify" gap is still unaddressed. The platform tells the user WHAT to do but not HOW. For Beginner tier, focus areas should link to documentation or show a tooltip: "Verify means: after writing your resolution, click 'Verify' in the actions panel to confirm your findings before closing."

---

### Portfolio Visit (End of Session)

Visits `/portfolio` via nav.

Sees the empty state card: "No portfolio entries yet. Start training to build your evidence record."  
Sees a "Get started" CTA button.

**Reaction:** "I've done 3 cases and I still have no portfolio?"

**Finding:** Portfolio requires a minimum score threshold to add entries (by design). The empty state doesn't communicate the threshold. The operator doesn't know that their 22, 31, and 39-point cases don't qualify. The empty state should say: "Complete cases with a score of 70+ to add entries to your portfolio."

---

## End State

| Metric | Value |
|---|---|
| Cases closed | 3 |
| Average score | 27/100 |
| Achievements | 1 (first_case) |
| Role affinity | Insufficient data |
| Recruiter readiness | 34% — Early stage |
| Career path progress | None (no path configured) |
| Session dropped after: | ~45 min (probable return) |

**Drop-off risk assessment:** MEDIUM. The operator was frustrated but not completely discouraged. The achievement notification created a moment of positive engagement. The performance dashboard focus areas gave them a specific next step. Without those two elements, this user would likely not return.

---

# Operator 05 — Struggling User — Findings

---

## What Worked Well

### 1. Registration Has No Unnecessary Friction
Blank job goal is allowed. Experience selection is gentle. The user got through registration without frustration.

### 2. Achievement Positive Reinforcement at Rock Bottom
Even at 22/100 on case 1, the `first_case` achievement creates a genuine moment of positive engagement. This is the correct behaviour — the platform rewards participation without rewarding poor quality specifically.

### 3. Consequence Feedback Loop Works at Small Scale
From case 1 → case 3, score improved from 22 to 39 purely from reading consequence flags. The user engaged with the feedback even without understanding it fully.

### 4. AI Explain Action Accessible to Complete Newcomers
The `p9_explain_issue` button was discovered organically and the beginner coaching note was understood and partially followed. No training required.

---

## Issues Found (Priority-Ordered)

### Issue 1 — Consequence Flag Examples Missing (HIGH)
**Description:** "Investigation notes lack specificity" is not actionable for someone who doesn't know what IT investigation specificity means. There are no examples, no templates, no guidance on what good notes look like.

**Impact:** The most common failure mode for struggling users. Flags fire correctly but produce confusion rather than learning.

**Recommendation:** Each consequence flag variant should include a one-line "Example of good practice" tooltip or inline text. This is the single highest-ROI UX improvement for new users.

**Target file:** `core_loop_complete.html` — consequence flags section

### Issue 2 — Verify Button Discoverability (HIGH)
**Description:** 3 operators across 5 failed to discover the verify step without prompting. For Operator 05, the button was never found in 3 cases. This is a systemic discoverability issue, not an operator problem.

**Impact:** Verification is one of the strongest scoring signals. Users who can't find it are systematically penalised.

**Recommendation:**
- Option A: Add a persistent "Verify before closing" tooltip that appears when the Close button is first hovered, dismissable after one click
- Option B: Add a progress checklist in the incident header: "✓ Evidence reviewed · ✓ Notes written · ○ Verify · ○ Close" — the circle on verify makes it visible as an incomplete step
- Option B is preferred as it teaches the investigation sequence

### Issue 3 — "SLA at risk" Misread as Personal Fault (MEDIUM)
**Description:** The dashboard queue metric "3 SLA at risk" was immediately interpreted as "3 things I broke." No explanation of what SLA means is provided.

**Impact:** Creates a false anxiety loop before the user has done anything.

**Recommendation:** Add a tooltip on the SLA metric: "SLA = the time a case should be resolved by. These are pre-existing cases in the queue — not related to your actions."

### Issue 4 — Portfolio Empty State Doesn't Explain Threshold (MEDIUM)
**Description:** Portfolio shows empty after 3 cases without explaining that a minimum score is required. The user doesn't know why their cases haven't appeared.

**Impact:** Creates a false impression that the system isn't working.

**Recommendation:** Change empty state text to: "No portfolio entries yet. Cases with an investigation score of 70+ will appear here automatically. Keep practising to build your evidence record."

### Issue 5 — Wizard Step 3 — Too Many Bullets (LOW)
**Description:** Step 3 of the beginner wizard lists 8 practice areas in a single screen. For non-IT users, this creates information overwhelm.

**Impact:** Users click through without reading rather than engaging with the content.

**Recommendation:** Show 3 bullets with a "Show all practice areas" expand toggle. Lead with the 3 most beginner-relevant items.

### Issue 6 — Performance Focus Areas Don't Link to Help (LOW)
**Description:** Focus areas say "improve verification consistency" but don't tell the user what verification is or how to find it.

**Impact:** Users know what to improve but not how.

**Recommendation:** Add a micro-help icon next to each focus area that opens a tooltip explanation: "'Verify' means: after writing your resolution, click the Verify button in the action panel to confirm your findings before closing."

---

## Validation Outcomes

| Test | Pass/Fail | Notes |
|---|---|---|
| Registration — blank goal allowed | PASS | No friction |
| Beginner tier tickets assigned | PASS | All P3 Beginner |
| first_case achievement fires on any close | PASS | Fires after 22/100 score |
| Consequence flags fire on poor quality | PASS | All 3 flag types fire correctly |
| AI explain accessible to newcomers | PASS | Found organically on case 3 |
| Coaching note readable for non-IT users | PASS | Partially followed |
| Portfolio empty state visible | PASS | Shows CTA |
| Performance focus areas populated | PASS | "evidence review depth" shown |
| Drop-off prevention (achievement + focus) | PASS | User likely returns |
| Verify button found without help | FAIL | Never found in 3 cases |
| Consequence flag examples shown | FAIL | No examples — critical gap |
| Portfolio threshold explained | FAIL | Empty state doesn't explain 70+ requirement |
| SLA metric tooltip | FAIL | Misread as personal fault |
