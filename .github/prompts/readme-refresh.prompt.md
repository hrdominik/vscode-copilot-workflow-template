---
name: readme-refresh
description: "Refresh README to match how the project actually builds/runs/tests"
---

Update the repository README to reflect reality (no marketing language; no speculation).

Inputs:
- Target audience: ${input:audience:dev|ops|user}
- Focus: ${input:focus:quickstart|dev-workflow|ops|all}
- README path (optional): ${input:path:README.md}

Process:
1) Use `#codebase` to identify:
   - build commands
   - test commands
   - run commands
   - config expectations and env vars (use examples only)
   - Docker/Compose usage (if present)
2) Propose README edits with:
   - exact copy/pasteable commands
   - explicit prerequisites
   - troubleshooting bullets for common failures
3) Ensure no secrets in examples.

Output:
## Proposed README outline
## Patch plan (sections to add/change)
## Verification checklist
