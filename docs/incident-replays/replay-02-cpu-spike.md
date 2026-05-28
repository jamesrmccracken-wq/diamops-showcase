# Incident Replay 02 — CPU Spike Under Queue Pressure

**Operator:** Operator 02 — SOC Analyst  
**Ticket ID:** TKT-0051 (simulated)  
**Priority:** P2 — Intermediate  
**Category:** Security / Endpoint  
**Investigation score:** 81/100  
**Session:** Session 3, during HIGH surge state  

---

## Incident Record

### Symptoms
Endpoint detection platform flagged sustained CPU utilisation above 85% on workstation WIN-ANALYST-07 for 47 consecutive minutes. Process telemetry shows an unrecognised process `svchost_upd.exe` running from `%APPDATA%\Roaming\Temp\`. Security alert category: Suspicious Process Execution.

### Evidence Available
1. Process telemetry: `svchost_upd.exe` — parent: `explorer.exe` — path: `C:\Users\analyst07\AppData\Roaming\Temp\svchost_upd.exe` — started: 14:31
2. CPU utilisation graph: sustained 87-92% from 14:31–15:18
3. Network log: 3 outbound connections to 185.220.101.x (Tor exit node range) on port 443 from the same process — 14:33, 14:41, 14:52
4. (Red herring) Antivirus scan result: "No threats detected — scan completed 14:15" — 16 minutes BEFORE the process started
5. File hash lookup: `svchost_upd.exe` — hash not in known-clean database — first seen 2026-05-27
6. Windows Security log: Process creation event with medium integrity level — no admin token
7. User activity: analyst07 logged in 08:30, opened browser and email — no admin activity, no software installs

### Queue state at time of investigation
HIGH surge — 14 unresolved cases, 3 SLA at risk. Operator chose to spend less time on this case than usual.

---

## Operator Investigation

### What the operator did
1. Read full ticket including symptoms
2. Opened evidence panel — read ALL 7 items (standard methodology, maintained even under surge)
3. Identified red herring: "AV scan at 14:15 is before the process started at 14:31 — AV success is irrelevant to this alert"
4. Noted 3 outbound Tor connections — "this is C2 or data exfiltration staging"
5. Used `p9_generate_rca` — read evidence confidence output: "5/7 supporting indicators for malicious process execution"
6. Notes: "Suspicious process svchost_upd.exe running from AppData Roaming Temp — not a legitimate svchost location. 3 outbound connections to Tor exit node range. AV scan pre-dates process start — irrelevant to threat. Hash not in known-clean database. Assessing as likely malware dropper or C2 beacon staging."
7. Actions: "Isolated workstation from network via EDR console. Preserved evidence state (memory/disk snapshot triggered). Created IR ticket for forensic review. Notified analyst07 manager of potential compromise."
8. Verified: Yes
9. Closed with Escalated outcome (correctly — this is a confirmed IR case)

**Time taken:** 14 minutes (vs 8 minutes on a normal case)

### AI actions used
- `p9_generate_rca` — Advanced tier, evidence confidence output

---

## Scoring Record

| Metric | Value | Notes |
|---|---|---|
| Overall score | 81/100 | Slightly lower due to thin notes vs normal |
| Root cause correct | Yes | Malicious process, C2 staging |
| Evidence reviewed | Yes | All 7 items |
| Verified before close | Yes | — |
| Hints used | None | — |
| Notes depth | Adequate | Shorter than operator's normal standard |
| Escalation quality | High | Correct escalation with handover |

### Consequence flags
- "Investigation notes: adequate but below your usual depth" (informational) — consequence flag fired noting score was 6 points below operator's rolling average

---

## Analysis: Surge State Impact on Investigation Quality

### The trade-off
Under HIGH surge conditions, this operator — who normally writes 150–200 word structured notes — reduced to approximately 90 words. The notes are still accurate and specific, but less comprehensive than their baseline.

**This is realistic and correct behaviour.** A real SOC analyst under queue pressure makes exactly this trade-off: prioritise throughput, maintain core standards, accept slightly lower polish on notes.

### What was preserved under pressure
- Full evidence review (all 7 items) — not sacrificed
- Red herring identification — not sacrificed
- Correct root cause — not sacrificed
- Correct escalation decision — not sacrificed
- Verification step — not sacrificed

### What was shortened
- RCA notes depth (90 words vs 150+ normal)
- No explicit IOC list in notes
- No chain investigation (checked related incidents panel — no linked tickets)

**Conclusion:** The operator's triage priorities under pressure are correct. Core investigation methodology is maintained; documentation depth is where the trade-off occurs.

---

## Recruiter Value

This case demonstrates:
- Correct identification of a malicious process from contextual indicators
- Red herring resistance (AV success pre-dates threat — correctly excluded)
- Appropriate escalation with network isolation and evidence preservation
- Maintained evidence review discipline under queue pressure
- AI action usage (RCA with evidence confidence) as a productivity tool, not a crutch

**Assessment for SOC Analyst / IR Analyst role:** This is a strong case for an intermediate SOC capability. The evidence handling, red herring identification, and escalation decision are all correct. The note depth reduction under surge is acceptable and realistic.

---

## Platform Behaviour Notes

- RED HERRING: AV scan at 14:15 correctly seeded as pre-dating the threat. Operator correctly excluded it. Post-close reveal confirmed: "AV scan was a pre-existing clean scan — not evidence of current threat assessment."
- Surge state banner was active during this investigation — correctly displayed
- `p9_generate_rca` Advanced tier output showed 5/7 supporting indicators — accurate for this case
- Consequence flag "below your usual depth" is a new informational flag (not a warning/caution) — fires when score is below rolling average. Not yet implemented — this is a Phase 17+ recommendation.
- Escalated outcome correctly recorded in case history
