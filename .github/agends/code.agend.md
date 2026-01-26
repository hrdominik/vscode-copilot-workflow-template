# Code agenda (implementation task)

Use this agenda for typical software development tasks (features, fixes, refactors) under engineer oversight.

## Inputs you provide
- Task statement (from your plan)
- Acceptance criteria (or link to requirement ID)
- Scope/path constraints

## Checklist (implementation discipline)
1) Read:
   - `.github/docs/state/state.md` (current objective and next steps)
   - `.github/docs/requirements.md` (relevant FR/NFR + acceptance)
   - `.github/docs/architecture.md` (relevant boundaries, trust assumptions)
2) Locate the code paths via `#codebase`:
   - entry points
   - callers/consumers
   - test locations and conventions
3) Implement with minimal diffs:
   - no unrelated refactors
   - keep changes incremental
4) Tests:
   - add/extend tests for behavior change
   - regression tests for bug fixes
   - deterministic and maintainable
5) Documentation:
   - update README/docs if usage changes
   - update requirements evidence mapping if acceptance is now proven
6) State update:
   - update `.github/docs/state/state.md` (done/in progress/next steps/commands)

## Copy/paste prompt
> Act as a Code Writer. Implement exactly one task with minimal diffs.
> Use `.github/docs/requirements.md`, `.github/docs/architecture.md`, `.github/docs/state/state.md` as sources of truth.
> Add/update tests, propose verification commands, and propose updates to docs and state.
