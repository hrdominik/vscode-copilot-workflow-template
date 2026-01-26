# Plan agenda (requirements → tasks)

Use this agenda when you need a clean task breakdown before implementing.

## Inputs you provide
- Objective / feature / change request
- Constraints (security, ops, perf, compliance, timelines)
- Scope boundaries (what is in/out)

## Checklist
1) Read sources of truth:
   - `.github/docs/requirements.md`
   - `.github/docs/architecture.md`
   - `.github/docs/state/state.md`
2) Confirm/define acceptance criteria:
   - Define testable acceptance criteria (AC-*).
   - Identify relevant NFRs (security, ops, reliability, cost).
3) Break into tasks (3–12 max):
   - Each task has a clear outcome.
   - Each task has a Definition of Done (DoD):
     - tests or explicit verification procedure
     - doc updates (README/requirements/architecture) if impacted
     - security considerations if applicable
4) Identify risks and dependencies:
   - high-risk areas (authn/authz, networking, stateful resources)
   - external dependencies (cloud services, policies, CI)
5) Update `.github/docs/state/state.md`:
   - objective, next steps, commands, open questions

## Copy/paste prompt (if not using a dedicated prompt)
> Act as a Planner. Read `.github/docs/requirements.md`, `.github/docs/architecture.md`, and `.github/docs/state/state.md`.
> Produce a task breakdown (3–12 tasks), each with DoD (tests + docs + verification).
> Highlight risks, dependencies, and what must be updated in requirements/architecture/state.
