# DiamOps Showcase

**DiamOps** is a workforce-readiness platform for simulated IT operations. Learners investigate real-style incidents, review evidence, document their reasoning, and export recruiter-ready proof of their operational capability.

This repository is the **public showcase** — screenshots, validation documentation, operator journey case studies, and incident replays. The active product, admin tooling, authentication, database, and internal validation infrastructure live in a private core repository.

**Platform maturity:** 96/100 · **Sentinel status:** 98/100 RELEASE_READY · **Build:** bea3e8a (Post Phase 16)

---

## What DiamOps Does

A learner opens DiamOps, picks an incident from the operational queue, and works through it: reading symptoms, reviewing evidence, identifying root cause, taking action, documenting everything, and verifying before close. When they're done, the platform scores the investigation and adds it to their recruiter-facing portfolio.

Over time, the platform tracks **role affinity** (SOC analyst vs Cloud/DevOps vs IT Support vs NOC), builds a **progression timeline**, and surfaces an **achievements record** — all based on real investigation behaviour, not vanity metrics.

---

## Screenshot Gallery

> All screenshots captured from the live platform. Desktop: 1440×900 · Mobile: 390×844 · Tablet: 1024×768 · Sentinel captures: multiple viewports.

### Operational Queue & Dashboard

| Screen | Description |
|---|---|
| ![Dashboard](screenshots/dashboard/03-dashboard-high-pressure.png) | **Operational Queue — HIGH PRESSURE** · 80 open incidents · 32 at SLA risk · Escalation bottleneck banner · Next SLA breach in 8 min |
| ![Mode Card](screenshots/dashboard/04-dashboard-mode-card.png) | **Dashboard scrolled** · Operational mode card · Activity feed · Section dividers |
| ![Queue](screenshots/queue/05-incident-queue-full.png) | **Incident Queue** · Full prioritised ticket list across SysAdmin, SOC, Cloud, IT Support, Desktop Support categories |

### Investigation Workspace

| Screen | Description |
|---|---|
| ![Workspace](screenshots/investigation/06-investigation-workspace.png) | **Investigation Workspace** · 3-panel layout: ticket detail + evidence sidebar + activity timeline drawer |
| ![Evidence](screenshots/investigation/07-investigation-evidence-panel.png) | **Evidence Panel** · Structured evidence items · Mixed signal quality at Intermediate/Advanced tier |
| ![Sentinel Before](screenshots/sentinel/sentinel-13-investigation-before.png) | **Investigation (Sentinel capture)** · Workspace before submission — notes, actions, verify sequence |
| ![Sentinel Complete](screenshots/sentinel/sentinel-14-investigation-complete.png) | **Investigation Complete (Sentinel)** · Scorecard with root cause verdict, evidence review, verification status |

### Phase 13 — Operational Progression Engine

| Screen | Description |
|---|---|
| ![Achievements](screenshots/achievements/08-achievements-page.png) | **Achievements** · Professional operational achievements · Earned on real behavioural signals · No XP, no points, no levels |
| ![Achievement Grid](screenshots/achievements/09-achievements-grid.png) | **Achievement Grid** · Earned (green border + icon) vs locked (50% opacity) states |
| ![Role Affinity](screenshots/career/10-career-path-role-affinity.png) | **Role Affinity** · Behavioural scoring across SOC Analyst, NOC Analyst, IT Support L1/L2, Cloud/DevOps Engineer |
| ![Career Progress](screenshots/career/11-career-path-progress.png) | **Career Path Progress** · Milestone tracking: Trainee → Practised → Advanced per role path |
| ![Timeline](screenshots/career/12-career-progression-timeline.png) | **Progression Timeline** · Career event stream: milestones, score jumps, domain firsts, achievements |
| ![Role Paths](screenshots/career/22-role-paths-overview.png) | **Role Paths Overview** · Available career paths and current progress |

### Phase 14 — Recruiter Validation Infrastructure

| Screen | Description |
|---|---|
| ![Recruiter Hero](screenshots/recruiter/13-recruiter-dashboard-hero.png) | **Recruiter Dashboard** · Readiness % · Primary role alignment · Trend direction · At-a-glance summary strip |
| ![Role Readiness](screenshots/recruiter/14-recruiter-role-readiness.png) | **Role Readiness Breakdown** · Per-role scores with signal lists · Strong / Developing / Early labels |
| ![Recruiter Achievements](screenshots/recruiter/15-recruiter-achievements-list.png) | **Achievement Record** · Professional achievement labels with operational context for recruiters |
| ![Case Evidence](screenshots/recruiter/16-recruiter-case-evidence.png) | **Verified Case Evidence** · Scored investigations available as recruiter proof · Each case links to full replay |
| ![Sentinel Proof](screenshots/sentinel/sentinel-17-post-workflow-proof.png) | **Post-workflow Proof (Sentinel)** · Verified incident proof page after case completion |
| ![Sentinel Portfolio](screenshots/sentinel/sentinel-18-post-workflow-portfolio.png) | **Post-workflow Portfolio (Sentinel)** · Portfolio updated with new verified case |

### Performance Analytics

| Screen | Description |
|---|---|
| ![Performance](screenshots/performance/17-performance-overview.png) | **Performance Overview** · Operational identity · Role alignment · Strengths · Focus areas |
| ![Sparkline](screenshots/performance/18-performance-readiness-sparkline.png) | **Readiness Trend Sparkline** · CSS bar chart showing investigation score trajectory across last 12 cases |
| ![Achievements Preview](screenshots/performance/19-performance-achievements-preview.png) | **Achievements Preview** · Mini achievement grid on performance page |
| ![Sentinel Analytics](screenshots/sentinel/sentinel-02-desktop-analytics.png) | **Analytics (Sentinel capture)** · Full performance / analytics view |

### Proof & Portfolio

| Screen | Description |
|---|---|
| ![Proof](screenshots/proof/20-proof-exports-page.png) | **Proof Exports** · Investigation proof packages ready for portfolio or recruiter conversations |
| ![Portfolio](screenshots/proof/21-portfolio-page.png) | **Portfolio** · Curated evidence record of verified investigations |
| ![Sentinel Proof Exports](screenshots/sentinel/sentinel-15-proof-exports.png) | **Proof Exports (Sentinel)** · Multi-case proof export view |
| ![Sentinel Portfolio](screenshots/sentinel/sentinel-16-portfolio.png) | **Portfolio (Sentinel)** · Portfolio view with case list |

### Onboarding

| Screen | Description |
|---|---|
| ![Login](screenshots/onboarding/01-login-page.png) | **Login** · "Built under pressure. Ready for the job." · Operational identity branding |
| ![Landing](screenshots/onboarding/02-public-landing.png) | **Public Landing** · Feature overview for first-time visitors |
| ![Sentinel Landing](screenshots/sentinel/sentinel-19-public-landing.png) | **Landing (Sentinel)** · Full public landing page capture |
| ![Sentinel Pricing](screenshots/sentinel/sentinel-20-pricing.png) | **Pricing (Sentinel)** · Pricing page capture |

### Mobile — iPhone 14 Pro (390×844)

| Screen | Description |
|---|---|
| ![iPhone Dashboard](screenshots/mobile/23-mobile-dashboard-iphone14.png) | Operational queue on iPhone |
| ![iPhone Achievements](screenshots/mobile/24-mobile-achievements-iphone14.png) | Achievements page on iPhone |
| ![iPhone Recruiter](screenshots/mobile/25-mobile-recruiter-iphone14.png) | Recruiter dashboard on iPhone |
| ![iPhone Queue](screenshots/mobile/26-mobile-queue-iphone14.png) | Incident queue on iPhone |
| ![Sentinel iPhone](screenshots/sentinel/sentinel-05-iphone14-dashboard.png) | Dashboard — iPhone 14 (Sentinel) |
| ![Sentinel iPhoneSE Dashboard](screenshots/sentinel/sentinel-07-iphonese-dashboard.png) | Dashboard — iPhone SE (Sentinel) |
| ![Sentinel iPhoneSE Queue](screenshots/sentinel/sentinel-08-iphonese-queue.png) | Incident queue — iPhone SE (Sentinel) |

### Tablet — iPad (1024×768)

| Screen | Description |
|---|---|
| ![iPad Dashboard](screenshots/mobile/27-tablet-dashboard-ipad.png) | Dashboard at tablet width |
| ![iPad Queue](screenshots/mobile/28-tablet-queue-ipad.png) | Incident queue at tablet width |
| ![iPad Recruiter](screenshots/mobile/29-tablet-recruiter-ipad.png) | Recruiter dashboard at tablet width |
| ![Sentinel iPad Dashboard](screenshots/sentinel/sentinel-09-ipad-dashboard.png) | Dashboard — iPad (Sentinel) |
| ![Sentinel iPad Queue](screenshots/sentinel/sentinel-10-ipad-queue.png) | Queue — iPad (Sentinel) |
| ![Sentinel Pixel](screenshots/sentinel/sentinel-11-pixel-dashboard.png) | Dashboard — Pixel (Sentinel) |

---

## Platform Architecture

```
Learner UI (Flask / Jinja2 / SQLite)
  ├── Incident investigation workspace
  │     ├── Evidence panel (conflicting/red-herring evidence at Advanced tier)
  │     ├── AI guidance (Explain Issue / Summarise Evidence / Generate RCA)
  │     ├── Incident chain panel (linked upstream/downstream tickets)
  │     └── Activity drawer (grouped timeline phases: Triage / Investigation / Resolution)
  ├── Operational pressure layer
  │     ├── Queue surge detection (Moderate / High / Critical states)
  │     ├── SLA risk indicators (per-ticket + dashboard)
  │     ├── Escalation bottleneck detection
  │     └── Presence strip (derived from real DB state)
  ├── Progression engine (Phase 13)
  │     ├── Achievement system (12 achievements, behavioural triggers)
  │     ├── Role affinity scoring (SOC / NOC / IT Support / Cloud-DevOps)
  │     ├── Career path milestones (Trainee → Practised → Advanced)
  │     └── Progression timeline (career event stream)
  ├── Recruiter validation (Phase 14)
  │     ├── Recruiter dashboard (readiness %, role breakdown, achievement record)
  │     ├── Verified incident proof (per-case investigation replay)
  │     └── Role-specific readiness signals
  ├── Multi-user presence (Phase 15)
  │     ├── Ticket claiming (intent signal, not exclusive lock)
  │     └── Simulated operational presence (real queue state, no fabrication)
  └── Sentinel QA (Phase 16 — autonomous validation)
        ├── Main Sentinel: 98/100 RELEASE_READY
        ├── Roadmap Sentinel: 98/100 RELEASE_READY
        └── Recruiter Sentinel: 76/100 → 100 post-restart
```

**Stack:** Python · Flask · SQLite · Jinja2 · CSS (no frameworks) · Node.js + Playwright (Sentinel)

---

## Validation Results

Five realistic operator archetypes were simulated through complete platform journeys. Full reports in `docs/validation/`.

| Operator | Role archetype | Cases | Avg score | Recruiter readiness |
|---|---|---|---|---|
| Helpdesk Learner | IT Support L1 | 6 | 61/100 | 61% — Developing |
| SOC Analyst | SOC Tier 1 (MSSP) | 11 | 84/100 | 84% — Strong |
| MSP Operator | NOC / IT Support | 9 | 68/100 | 68% — Developing |
| Cloud/DevOps | Cloud Engineer (AWS) | 12 | 89/100 | 88% — Strong |
| Struggling User | No IT background | 3 | 27/100 | 34% — Early |

**Key findings:**
- Achievement triggers: 29/29 correct across test population (100%)
- Role affinity primary alignment: 5/5 correct
- Recruiter proof pages: standalone-readable without DiamOps context
- Platform RELEASE_READY for operators with any IT background

---

## Documentation Index

### Validation Reports
- [`docs/validation/final-validation-report.md`](docs/validation/final-validation-report.md) — 20-point readiness assessment
- [`docs/validation/realism-analysis.md`](docs/validation/realism-analysis.md) — Incident realism depth (91/100)
- [`docs/validation/recruiter-analysis.md`](docs/validation/recruiter-analysis.md) — Recruiter dashboard validation (90/100)
- [`docs/validation/progression-analysis.md`](docs/validation/progression-analysis.md) — Progression system analysis (87/100)
- [`docs/validation/pressure-analysis.md`](docs/validation/pressure-analysis.md) — Queue pressure & surge analysis (89/100)
- [`docs/validation/usability-analysis.md`](docs/validation/usability-analysis.md) — Navigation & UX analysis (82/100)
- [`docs/validation/onboarding-analysis.md`](docs/validation/onboarding-analysis.md) — Onboarding friction analysis (79/100)

### Operator Journeys
- [`docs/operators/operator-01-helpdesk.md`](docs/operators/operator-01-helpdesk.md) — Beginner helpdesk, 6 cases, 61 avg
- [`docs/operators/operator-02-soc.md`](docs/operators/operator-02-soc.md) — SOC analyst, 11 cases, 84 avg
- [`docs/operators/operator-03-msp.md`](docs/operators/operator-03-msp.md) — MSP operator, 9 cases, 68 avg
- [`docs/operators/operator-04-cloud.md`](docs/operators/operator-04-cloud.md) — Cloud/DevOps, 12 cases, 89 avg
- [`docs/operators/operator-05-struggling.md`](docs/operators/operator-05-struggling.md) — Struggling user, 3 cases, 27 avg

### Incident Replays
- [`docs/incident-replays/replay-01-dns-failure.md`](docs/incident-replays/replay-01-dns-failure.md) — DNS resolution failure (69/100)
- [`docs/incident-replays/replay-02-cpu-spike.md`](docs/incident-replays/replay-02-cpu-spike.md) — CPU spike under queue pressure (81/100)
- [`docs/incident-replays/replay-03-cert-expiry.md`](docs/incident-replays/replay-03-cert-expiry.md) — Certificate expiry chain (93/100)

---

## Security

This repository must not contain credentials, database files, admin routes, deployment configs, private validation logs, or user data. See [`docs/SECURITY.md`](docs/SECURITY.md).

---

*DiamOps — Built under pressure. Ready for the job.*  
*© 2026 James McCracken*
