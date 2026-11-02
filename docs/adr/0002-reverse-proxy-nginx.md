# ADR-0002 — Reverse proxy: Nginx

- **Date:** 2026-10-25
- **Status:** Accepted

## Context

orchestra will host several services, but only one entry point should be exposed.
A reverse proxy receives every request and forwards it to the right service on the private Docker network.
It must also handle HTTPS automatically when orchestra moves to a VPS.

## Options

| Option | HTTPS | Configuration | Fit for orchestra |
|---|---|---|---|
| **Caddy** | Automatic (Let's Encrypt built in) | Short `Caddyfile` | Simple, but rare in companies |
| **Traefik** | Automatic (ACME built in) | Docker labels on each service | Powerful, but more concepts to learn |
| **Nginx** | Automatic (native ACME module since 2025) | Longer `nginx.conf` | Most used, industry standard |

Sources:
- Caddy automatic HTTPS: https://caddyserver.com/docs/automatic-https
- Traefik ACME: https://doc.traefik.io/traefik/https/acme/
- Nginx native ACME: https://blog.nginx.org/?p=74612
- Web server market share: https://w3techs.com/technologies/overview/web_server

## Decision

We use Nginx, pinned to `nginx:1.30` (the stable branch).
It is the most used web server today, and it now handles HTTPS automatically with its native ACME module.
Caddy is rejected because it is rare in companies.
Traefik will be reconsidered at the Kubernetes stage.

## Consequences

- Positive: Nginx is a more valuable skill on the job market.
- Negative: longer configuration and more room for mistakes than Caddy.
- Next: the `caddy` service is replaced by `nginx` in `compose.yaml`, with `proxy/nginx.conf`; `localhost:8080` stays the same.
- Later: at the VPS stage, check that the Docker image includes the ACME module.
