# Journal

One line per working session.

- 2026-10-20 — Project started: ADR-0001 (name `orchestra`, Uptime Kuma first, local → VPS → AWS), repository created.
- 2026-10-20 — Uptime Kuma running locally (Docker Compose, SQLite, persistent volume, bound to 127.0.0.1).
- 2026-10-21 — Master plan validated; Caddy reverse proxy in front of Uptime Kuma (localhost:8080), direct port removed.
- 2026-10-25 — Reverse proxy switched from Caddy to Nginx 1.30 (ADR-0002); WebSocket headers added and verified (101 in logs).
- 2026-11-02 — Repository basics (.gitignore, .editorconfig, MIT license), README updated, Dependabot, protected main, first Uptime Kuma monitor (Nginx, 200 OK).
