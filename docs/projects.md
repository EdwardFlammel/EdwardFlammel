# Homelab projects

Two projects from my self-hosted Gitea environment: monitoring the lab and
managing its applications through versioned Docker Compose stacks.

## Observability

**Stack:** Zabbix 7.0 · Zabbix Agent 2 · Grafana · PostgreSQL 16 · Docker Compose

### What is in the repository

- Zabbix Server and web interface backed by PostgreSQL, with database healthcheck
  and persistent storage.
- Grafana with the Zabbix plugin declared in Compose.
- A qBittorrent exporter as an additional metrics endpoint.
- Environment templates, explicit bind addresses, resource limits and log rotation.
- Per-stack Compose validation, Gitleaks scanning and HMAC-signed Komodo deploy
  webhooks in Gitea Actions.

### What I work on

Host monitoring with Agent 2, metrics visualization, container persistence and
delivery workflows that keep configuration versioned and credentials separate.

### Current scope

Agent installation and application-side configuration are outside Compose.
Datasources and dashboards are not provisioned or exported in the repository;
alerts are not documented as configured or tested. The exporter does not include
a collector configuration, so its presence alone does not establish end-to-end
metrics ingestion.

The project README still describes a Portainer deployment, while the current
Actions workflows target Komodo. This summary reflects that transition and does
not claim that every running service has already migrated.

## Docker Stacks

**Stack:** Docker Compose · Gitea · Gitea Runner · Komodo Core / Periphery · Gitleaks

### What is in the repository

- Compose stacks for Jellyfin, Sonarr, Radarr, Prowlarr, Seerr and
  qBittorrent/Gluetun.
- Infrastructure definitions for Gitea, its runner and Komodo with MongoDB.
- A development-to-main review flow with per-stack change detection.
- Compose validation before each affected application workflow requests deploy.
- HMAC-SHA256 signed webhooks from Gitea Actions to Komodo.
- Git history scanning through Gitleaks, separate from the deployment workflows.
- Documentation covering persistence, migration from Portainer, secrets,
  troubleshooting and recovery.

### What I work on

Self-hosting, container orchestration with Compose, reproducible configuration and
automated delivery across a homelab. The migration replaces the previous
Portainer delivery workflow with Komodo Core and Periphery.

### Current scope

Compose validation checks configuration, not live application health. Gitleaks
runs independently and is not a dependency that blocks the deployment workflows.
Komodo stack registrations, repository credentials and webhook configuration
still require setup outside the versioned Compose files.

## Kubernetes

Kubernetes is part of my day-to-day work and is listed under my current
infrastructure stack. These two homelab repositories use Docker Compose; they
are not presented as Kubernetes deployments.

## Source and scope

Reviewed against the Gitea `main` references on 24 October 2026:

- `observability`: `5e7fb22`
- `docker-stacks`: `3faffbd`

These are source-code summaries, not uptime claims or audits of the running
servers. Internal addresses and private repository access are not published here.

[Back to profile](../README.md#03--active-missions)
