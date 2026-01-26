# Documentation agenda (requirements, architecture, README)

Use this agenda when docs drift from implementation or when onboarding/operations changes.

## Inputs you provide
- What changed (feature/component)
- Target audience (dev/ops/user)
- Any known pain points (onboarding, troubleshooting)

## Checklist
1) Read:
   - `.github/docs/requirements.md` (acceptance and evidence expectations)
   - `.github/docs/architecture.md` (ops assumptions)
   - `.github/docs/state/state.md` (current status)
2) Decide doc targets:
   - README (quickstart, run/test commands)
   - requirements (acceptance/evidence mapping)
   - architecture (boundaries, trust assumptions, deployment model)
3) Make docs factual and verifiable:
   - explicit commands and expected output
   - explicit config keys and defaults
   - troubleshooting steps
4) Keep structure stable and maintainers-first.
5) Update `.github/docs/state/state.md` with what was changed and what to validate.

## Copy/paste prompt
> Act as a Documentation Maintainer. Update docs to match actual repo behavior.
> Provide exact commands, config guidance (no secrets), and a verification checklist.
> Update requirements/architecture evidence alignment if needed.
