# 🎼 orchestra

**My personal production platform** — a small cloud I build, run and secure myself, step by step, to host and monitor my own applications.

> From concert pianist to platform engineer: after years of performing with an orchestra, I'm now learning to *orchestrate* services.

![Status](https://img.shields.io/badge/status-phase%201%20in%20progress-blue)

## Why this project

My other projects show that I can **build** applications.
`orchestra` shows that I can **run them in production**: deploy them automatically, monitor them, secure them, and recover when something breaks.

It grows with my learning path (Ada Tech School — DevOps / Operations & Security specialisation), one small, documented step at a time.

## Environments

| Stage | Where | Goal | Status |
|---|---|---|---|
| 1 | **Local** (macOS, Docker Desktop) | Build and test the stack safely, at no cost | 🔵 In progress |
| 2 | **VPS** (rented Linux server) | Real domain, HTTPS, SSH, server hardening | ⏳ Planned |
| 3 | **AWS** | Infrastructure as Code with Terraform, budget alerts | ⏳ Planned |

## Roadmap

| Phase | Topic | Main tools |
|---|---|---|
| 1 | Containers | Docker, Docker Compose, reverse proxy |
| 2 | CI/CD | GitHub Actions |
| 3 | Observability | Uptime Kuma, Prometheus, Grafana |
| 4 | DevSecOps | Trivy, secrets management, signed images |
| 5 | Cloud | AWS, Terraform |
| 6 | Orchestration | Kubernetes, GitOps |
| 7 | Chaos days | Planned failures and public incident reports |

## Services

| Service | Role | Status |
|---|---|---|
| Uptime Kuma | Availability monitoring and alerts — monitoring comes before applications | ⏳ Next |
| Conservatoire polyglotte | My multi-language application | ⏳ Planned |

## Decisions

Every important technical choice is recorded as an **Architecture Decision Record (ADR)**:

- [ADR-0001 — Name, scope and first service](docs/adr/0001-name-scope-first-service.md)

## Progress log

See [JOURNAL.md](JOURNAL.md) — one line per working session.

## Working rules

- Small steps: about **30 minutes a day**, one brick per session.
- Everything is **versioned and documented**: one branch per session, one commit per finished block, one pull request per session.
- **Security first**: no secrets in Git, no disabled TLS checks, least privilege.

---

Author: **Victor Metral** — Ada Tech School, Lyon
