# ADR-0003 — Hosting: OVHcloud VPS-1

- **Date:** 2026-11-22
- **Status:** Accepted

## Context

orchestra must leave my Mac: a real domain, HTTPS and SSH need a server reachable from the Internet.
It will also host FinancePilot, my CDA project: my mentor asked for a real server instead of a platform like Railway.
The budget is small, the data should stay in the European Union, and AWS stays planned for phase 5 (Terraform).

## Options

| Option | Price | Data location | Fit for orchestra |
|---|---|---|---|
| **OVHcloud VPS-1 (2027 range)** | from €3.81 excl. VAT/month (12 months), €4.49 without commitment | France (Gravelines) | Full Linux server, fixed price |
| **AWS Lightsail 4 GB** | $24/month | Region of choice, US company (CLOUD Act) | Same work, about 5× the price |
| **Railway** | Usage-based | US company | No server to manage: no operations to learn |

Sources:
- OVHcloud VPS 2027 range: https://blog.ovhcloud.com/en/posts/vps-2027/
- Lightsail 4 GB plan: https://www.vpsbenchmarks.com/hosters/amazon_lightsail/plans/4gb_2cores
- AWS Free Tier credits (07/2025): https://aws.amazon.com/about-aws/whats-new/2025/07/aws-free-tier-credits-month-free-plan/
- Railway pricing: https://railway.com/pricing

## Decision

We rent an OVHcloud VPS-1 (2027 range): 2 vCores, 4 GB RAM, 40 GB NVMe, Debian 13, in the Gravelines datacenter, without commitment.
It is the cheapest full Linux server of the three, with a fixed price and data stored in France, and my mentor approved it on 2026-11-07.
AWS Lightsail is rejected because it costs about five times more for the same work, and Railway because it hides the server I need to learn to operate.

## Consequences

- Positive: a real Linux server to operate, in France, for about €5.40 a month (incl. VAT).
- Negative: I am responsible for its security (SSH, firewall, updates, backups).
- Next: ADR-0004 (orchestra hosts FinancePilot, deploy user), then domain name and HTTPS.
- Later: consider the 12-month commitment once real usage is measured.
