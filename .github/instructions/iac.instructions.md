---
applyTo: "**/*.tf,**/*.tfvars,**/*.bicep,**/*.yaml,**/*.yml,**/k8s/**/*.yaml,**/helm/**/*"
description: "IaC standards (secure-by-default, safe rollout, explicit blast radius)"
---

# IaC standards
- Default to **least privilege** and **secure defaults**.
- Identify **blast radius** (what resources, what environments, what dependencies).
- Prefer incremental changes; avoid renaming/moving resources unless necessary (state impact).
- Include **validation gates**:
  - format/lint
  - validate
  - plan/dry-run
- Include **rollout and rollback** notes for changes affecting traffic, identity, networking, stateful resources.
- Never commit secrets (use secret references/integrations).
- If operational behavior changes, update `.github/docs/architecture.md` and `.github/docs/state/state.md`.
