# Incident Replay 01 — DNS Resolution Failure

**Operator:** Operator 01 — Helpdesk Learner  
**Ticket ID:** TKT-0003 (simulated)  
**Priority:** P3 — Beginner  
**Category:** Network / DNS  
**Investigation score:** 69/100  
**Session:** Session 2, Ticket 3  

---

## Incident Record

### Symptoms
User WIN-DESK-12 unable to resolve internal hostnames since this morning. Internet access working (external DNS resolving). Internal systems including file server and email are unreachable by name but accessible by IP address.

### Evidence Available
1. Windows Event Log: DNS Client Events — "DNS name resolution of the name fileserver.corp.local failed after none of the configured DNS servers responded."
2. Network adapter settings: Primary DNS: 192.168.1.10 — Secondary DNS: 192.168.1.11
3. DNS server 192.168.1.10: ping successful, service running, zone file intact
4. DNS server 192.168.1.11: ping TIMEOUT — server unreachable
5. DHCP lease renewal log: DORA sequence completed at 08:34. DNS assigned: 192.168.1.11 (secondary only, primary omitted from scope)
6. netstat output: No active DNS queries in progress
7. (Red herring seeded) nslookup fileserver.corp.local from admin workstation: "Non-existent domain" — same time, different user, different adapter config

---

## Operator Investigation

### What the operator did
1. Read ticket title and first paragraph of symptoms
2. Opened evidence panel — read items 3 and 4
3. Noticed item 4 (DNS server 192.168.1.11 unreachable) as relevant
4. Typed in investigation notes: "DNS server 192.168.1.11 is not responding. This is why the user can't connect."
5. Actions: "Changed primary DNS on user workstation to 192.168.1.10. Tested — file server and email now resolving."
6. Did not verify (button not noticed)
7. Closed ticket

### AI actions used
None — this case predates operator's discovery of AI actions (case 3 of session 2)

---

## Scoring Record

| Metric | Value | Notes |
|---|---|---|
| Overall score | 69/100 | Good resolution, weak notes |
| Root cause correct | Yes | Secondary DNS server unreachable |
| Evidence reviewed | Partial | 2/7 items read |
| Verified before close | No | Button not discovered |
| Hints used | None | — |
| Notes depth | Adequate | Brief but accurate |

### Consequence flags
- Insufficient evidence review (caution) — 2/7 items read
- Verification step skipped (caution)

---

## Full Investigation Context

### What the operator got right
- Correctly identified the root cause: secondary DNS server (192.168.1.11) was unreachable, causing resolution failures when the workstation's DHCP-assigned primary pointed to the secondary
- Resolution was correct and effective: pointing the workstation at the responsive primary (192.168.1.10) restored resolution
- Notes were brief but accurate — the root cause statement was correct

### What the operator missed
- **Red herring (item 7):** The nslookup from the admin workstation ("Non-existent domain") was a misleading artefact — different adapter configuration, different scope. A deeper investigator would have noted this and excluded it.
- **Evidence gap:** DHCP lease renewal log (item 5) explains WHY the workstation was assigned only the secondary DNS — a DHCP configuration issue. Fixing at the workstation level is correct short-term, but the DHCP scope should also be corrected.
- **Systemic fix missing:** The actions resolved the immediate issue but don't prevent recurrence. No action taken on DHCP scope or on determining why 192.168.1.11 was unreachable.

### What full resolution looks like
1. Identify: Secondary DNS unreachable (confirmed)
2. Immediate fix: Point workstation at primary DNS (done)
3. DHCP scope fix: Correct DHCP scope to include primary DNS as first assignment
4. Root cause of secondary failure: Investigate why 192.168.1.11 is unreachable (hardware failure? NIC issue? Needs separate ticket)
5. Document: Update network diagram if DNS server is offline

---

## Recruiter Value

This case demonstrates:
- Basic DNS architecture understanding (primary/secondary DNS roles)
- Correct immediate resolution under incomplete evidence
- Appropriate escalation awareness (secondary failure should be investigated — operator noted this verbally but didn't document it)

**Assessment for IT Support L1/L2 role:** This is the expected capability level for a developing L1 technician. The resolution is correct. The documentation and systemic analysis need development.

---

## Platform Behaviour Notes

- Red herring evidence item (admin workstation nslookup failure) was seeded but not detected — correct for Beginner tier (no completion reveal for Beginner)
- Consequence flags fired correctly on incomplete evidence review
- No AI coaching deployed (operator hadn't discovered AI actions yet)
- Score 69/100 is accurate: correct resolution + correct root cause + adequate notes, minus incomplete evidence and no verification
