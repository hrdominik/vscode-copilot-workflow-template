---
name: refactor
description: "Safe refactor agenda: preserve behavior, keep diffs small, add guardrail tests"
---

Perform a safe refactor with behavior preservation as the primary constraint.

Inputs:
- Scope: ${input:scope:Path/module/component}
- Goal: ${input:goal:readability|duplication|typing|perf|other}
- Constraints: ${input:constraints:no public API change|no deps change|timebox (optional)}

Rules:
- Minimal diffs; refactor in small steps.
- Add/strengthen tests before refactor if coverage is weak.
- Do not change behavior unless explicitly instructed; call out any behavior changes.

Tasks:
1) Define invariants (what must not change) and how to verify them.
2) Identify the smallest refactor steps.
3) Propose file-by-file changes and tests.
4) Provide verification commands.

Output:
## Invariants and verification strategy
## Step plan (small increments)
## Proposed changes (file-by-file)
## Tests / commands to run
## Risks / rollback plan
