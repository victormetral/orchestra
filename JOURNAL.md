# Journal

One line per working session.

- 2026-10-20 — Project started: ADR-0001 (name `orchestra`, Uptime Kuma first, local → VPS → AWS), repository created.
- 2026-10-20 — Uptime Kuma running locally (Docker Compose, SQLite, persistent volume, bound to 127.0.0.1).
- 2026-10-21 — Master plan validated; Caddy reverse proxy in front of Uptime Kuma (localhost:8080), direct port removed.
- 2026-10-25 — Reverse proxy switched from Caddy to Nginx 1.30 (ADR-0002); WebSocket headers added and verified (101 in logs).
- 2026-11-02 — Repository basics (.gitignore, .editorconfig, MIT license), README updated, Dependabot, protected main, first Uptime Kuma monitor (Nginx, 200 OK).
- 2026-11-18 — OVHcloud VPS-1 ordered (Debian 13, Gravelines, no commitment).
- 2026-11-19 — VPS secured: SSH keys only, root login disabled, ufw (port 22 only, IPv4 and IPv6), automatic security updates, new kernel loaded.
- 2026-11-21 — Docker Engine 29.10 and Compose v5.8 installed on the VPS from Docker's official apt repository; hello-world test passed.
- 2026-11-22 — ADR-0003 (hosting: OVHcloud VPS-1) and a pull request template.
- 2026-11-23 — ADR-0004: Orchestra hosts FinancePilot, deployed by a restricted user (SSH key limited to one script), with a Mermaid deployment diagram.
