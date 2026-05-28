# Onboarding Analysis

**Validation date:** 2026-05-28  
**Operators tested:** 5 (Operators 01–05)  
**Scope:** First login through first completed case  

---

## Summary

Onboarding is functionally sound for operators with some IT background (Operators 01–04). The wizard correctly orients new users to the platform's purpose without overwhelming them. However, there are critical gaps for complete newcomers (Operator 05) in three areas: verification step discoverability, consequence flag actionability, and the portfolio threshold explanation.

**Onboarding Score: 79/100**

---

## Wizard Assessment

### Strengths
- Clear purpose statement on step 1 ("operational training environment, not a test")
- Tier-appropriate framing (Beginner vs Intermediate wizard content differs correctly)
- Professional, non-gamified language throughout
- "Start Training" CTA is unambiguous

### Issues
- Step 3 (practice areas) lists 8 items — overwhelming for non-IT users
- Wizard doesn't preview what the dashboard looks like — first impression of the queue metrics can be disorienting

**Wizard score: 82/100**

---

## First Ticket Experience

### Operator 01 (Helpdesk Beginner)
- Arrived at first ticket without friction
- First score 38/100 — consequence feedback loop activated immediately
- Recovery to 74/100 on second case confirms the loop works

### Operator 02 (SOC Analyst)
- Arrived sceptical — platform earned trust via ticket content realism by end of case 1
- Trust formation happened during case 1, not during wizard

### Operator 03 (MSP Operator)
- Skipped wizard in 2 minutes — wanted the queue
- No friction, no confusion — the wizard is appropriately skippable

### Operator 04 (Cloud/DevOps)
- Wizard read quickly — "operational consequence framing" specifically noted as credible
- No friction

### Operator 05 (Struggling User)
- Paused at wizard step 3
- Clicked through without full comprehension
- Misread dashboard metrics after wizard
- Wizard failed to prevent dashboard confusion

---

## Dashboard First Impression

| Element | Pass rate across operators | Notes |
|---|---|---|
| Queue metrics understood correctly | 4/5 | Operator 05 misread SLA metric |
| Presence strip understood correctly | 4/5 | Operator 02 had minor claimed/self confusion |
| Activity feed — ignored on first view | 3/5 | Normal — not a friction point |
| "Start training" / incident CTA clear | 5/5 | 100% pass |
| Navigation structure understood | 4/5 | Operator 05 found nav confusing |

---

## Recommendations

### P0 — Critical (fix before next public release)
1. **Verify step discoverability:** Add a progress checklist in the incident header showing the investigation sequence (Evidence → Notes → Verify → Close) with visual step indicators. Found by 2/5 operators without prompting — should be 5/5.

2. **Consequence flag examples:** Add example text to each consequence flag variant. The most common new-user failure is not knowing what "specificity" means in an investigation context.

### P1 — High
3. **Portfolio threshold in empty state:** "Cases scoring 70+ appear here automatically." Currently the empty state gives no explanation.

4. **SLA metric tooltip:** Prevent the "did I break this?" misread.

### P2 — Medium
5. **Wizard step 3 progressive disclosure:** Show 3 bullets, expand for all 8. Reduces newcomer overwhelm.

6. **Dashboard "first session" banner:** Already exists via `is_first_session` flag — verify it fires for Operator 05 archetype.

---

## Onboarding Flow Health

```
Register → Wizard → Dashboard → First ticket → First close → Consequence review
   ✓           ✓        ✓           ✓              ✓              ✓ (for IT-background users)
   ✓           ~        ~           ✓              ✓              ~ (for complete newcomers)
```

The onboarding flow works for 4/5 operator archetypes. The failing case is a complete newcomer with no IT background — a real and important user type. Three targeted fixes (verify discoverability, flag examples, portfolio threshold) would bring this archetype to parity.
