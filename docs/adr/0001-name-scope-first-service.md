# ADR-0001 — Name, scope and first service

- **Date:** 2026-10-20
- **Status:** Accepted

## Context

I am starting a personal production platform to host, monitor and secure my own applications.
It must grow with my learning path (containers, CI/CD, observability, DevSecOps, Terraform, Kubernetes) and stay manageable with about 30 minutes of work a day.

Three things must be decided before writing any code: **what to host first**, **where to run it**, and **what to call it**.

## Decision 1 — First service: Uptime Kuma

| Option | Pros | Cons |
|---|---|---|
| **Uptime Kuma** ✅ | No application code to write: pure operations work. Will monitor every future service. | Not my own application |
| Conservatoire polyglotte | My own multi-language application | Heavier first step |
| FinancePilot | My main project | Still under construction |
| Todo App | Already containerised | Team project: I can't defend every line of it alone |

**Choice:** Uptime Kuma first, then Conservatoire polyglotte.
In production, monitoring comes **before** the applications it watches.

## Decision 2 — Scope: local, then VPS, then AWS

| Option | Pros | Cons |
|---|---|---|
| **Local (macOS, Docker Desktop)** ✅ first | Free, safe, fast feedback | Not reachable from the Internet |
| VPS (rented Linux server) | Real domain, HTTPS, SSH: real operations | Small monthly cost, must be hardened |
| AWS | What most companies use | Complex, risk of unexpected bills |

**Choice:** start locally, migrate to a VPS at the end of phase 1, move to AWS (with Terraform and budget alerts) in phase 5.

**Version 1 scope:** Docker Compose + a reverse proxy + Uptime Kuma + this public repository (README, ADRs, journal).

## Decision 3 — Name: `orchestra`

| Option | Comment |
|---|---|
| **`orchestra`** ✅ | Orchestrating services — and a nod to my background as a concert pianist |
| `tempo-cloud` | Nice, less explicit |
| `metral-cloud` | Clear, but neutral |
| `homelab` | Very common, not distinctive |

## Consequences

- **GitHub (public)** is the showcase: code, README, ADRs and history show the progression.
- **Notion (private)** is my logbook: tasks, sessions, decisions in progress.
- No cost at the start. The VPS stage will require DNS, HTTPS (Let's Encrypt), SSH and server hardening.
- Each new important choice gets its own ADR in `docs/adr/`.
