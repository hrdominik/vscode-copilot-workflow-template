# Environment agenda (Docker, Compose, IaC, local dev)

Use this agenda when you need a reproducible local environment or infrastructure change guidance.

## Inputs you provide
- Services to run locally
- Dependencies (db/cache/queue)
- Ports, volumes, dev mode (hot reload or not)
- Target cloud/IaC type (Terraform/Bicep/K8s)

## Checklist (local environment)
1) Inspect repo conventions:
   - how the app builds/runs/tests (scripts, makefiles, CI)
2) Compose setup:
   - define services and dependencies
   - add health checks where practical
   - keep environment variables in `.env.example` (never real secrets)
   - minimize port exposure and host mounts
3) Dockerfile discipline:
   - deterministic dependency installs
   - minimal base image
   - non-root where feasible
4) Verification:
   - provide exact `docker compose` commands
   - document expected outcomes and common failures

## Checklist (IaC change discipline)
1) Identify blast radius (resources, environments, dependencies).
2) Validate/plan before apply.
3) Rollout/rollback notes for risky changes.
4) Update `.github/docs/architecture.md` if operational behavior changes.

## Copy/paste prompt
> Act as a Container/IaC Engineer. Create/update Docker Compose and/or IaC with secure defaults.
> Provide validation and rollout/rollback guidance and update architecture/state if needed.
