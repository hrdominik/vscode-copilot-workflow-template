---
name: dockercompose
description: "Create/update Docker Compose for local dev: dependencies, healthchecks, env strategy"
---

Create or update a Docker Compose setup for local development.
Keep it reproducible and secure-by-default.

Inputs:
- Services: ${input:services:What should run (api, worker, ui, etc.)?}
- Dependencies: ${input:deps:db/cache/queue/etc (optional)}
- Ports: ${input:ports:Port mappings (optional)}
- Dev mode: ${input:dev:standard|hotreload (optional)}
- Compose filename: ${input:file:compose.yaml}

Rules:
- No secrets committed. Use `.env.example` patterns only.
- Minimize port exposure; avoid privileged containers unless necessary.
- Add healthchecks for dependencies where practical.
- Provide exact `docker compose` commands for start/stop/logs/clean.

Tasks:
1) Inspect repo run/build conventions via `#codebase` if available.
2) Propose compose services, volumes, env var strategy, and healthchecks.
3) Provide commands and troubleshooting notes.
4) Recommend README updates if compose becomes the primary onboarding path.

Output:
## Proposed compose design
## File changes (compose + env examples)
## Commands to run
## Troubleshooting checklist
