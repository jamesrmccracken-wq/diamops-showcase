# DiamOps Showcase

DiamOps is a proof-focused IT work simulation platform for learners preparing for helpdesk, service desk, NOC, SOC, cloud support, and junior operations roles.

This showcase repository is a public, sanitized presentation of the product concept. The active product, admin systems, deployment configuration, databases, and internal validation tooling live in a private core repository.

## Product Overview

DiamOps gives learners a realistic operations-console environment where they can triage tickets, inspect evidence, choose actions, write incident notes, and export portfolio-ready proof of work. The goal is simple: help a candidate show how they think under realistic IT pressure.

## Feature Highlights

- Guided IT ticket simulation
- Evidence review and root-cause workflow
- Learner notes and incident writeups
- Proof report concept for recruiter conversations
- Role coverage across IT support, operations, cloud, SOC, and MSP scenarios
- Recruiter-friendly skill evidence framing
- Demo-safe architecture and sample data

## Screenshots

Add polished screenshots here before public launch:

| Area | Screenshot |
| --- | --- |
| Learner dashboard | `screenshots/diamops-dashboard.png` |
| Ticket workflow | `screenshots/diamops-ticket-workflow.png` |
| Evidence review | `screenshots/diamops-evidence-review.png` |
| Proof report | `screenshots/diamops-proof-report.png` |

## Architecture Overview

```text
Learner UI
  -> Ticket simulation workflow
  -> Evidence review engine
  -> Notes and decision capture
  -> Scoring and feedback layer
  -> Proof report export
```

The private core includes admin operations, data persistence, pilot validation, authentication, deployment configuration, and internal quality gates. Those systems are intentionally excluded from this public repository.

## Technologies Used

- Python
- Flask
- HTML templates
- CSS
- SQLite/Postgres-ready architecture in private core
- Product validation scripts in private core

## Business Positioning

DiamOps is positioned for:

- early-career IT learners
- training providers
- bootcamps
- portfolio-based hiring
- recruiter screening conversations
- practical IT skills validation

## Roadmap

Public-safe roadmap:

- Add polished screenshots and short demo clips
- Publish sanitized sample scenarios
- Add a demo proof report
- Add a short architecture case study
- Prepare a private pilot flow for training partners

Private roadmap:

- admin tooling
- authentication
- persistence and deployment
- enterprise/cohort systems
- AI-assisted guidance
- pilot analytics

## Security Note

This repository must not contain real credentials, databases, admin systems, deployment configs, private validation logs, or internal roadmap files. See `docs/SECURITY.md`.

