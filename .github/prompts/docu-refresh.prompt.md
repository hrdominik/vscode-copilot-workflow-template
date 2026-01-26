---
name: docu-refresh
description: "Refresh requirements/architecture/state docs after changes (traceable and verifiable)"
---

Refresh documentation so it stays aligned with implementation and operations.

Inputs:
- Area changed: ${input:area:Feature/component/path}
- Docs focus: ${input:focus:requirements|architecture|state|all}
- Audience: ${input:audience:dev|ops|user (optional)}

Read:
- `.github/docs/requirements.md`
- `.github/docs/architecture.md`
- `.github/docs/state/state.md`

Tasks:
1) Identify which doc sections must change based on the area changed.
2) Propose concrete updates:
   - Requirements: acceptance criteria and evidence mapping
   - Architecture: boundaries, trust assumptions, operational view
   - State: next steps and commands
3) Keep docs factual and testable; provide a verification checklist.

Output:
## Doc impact analysis
## Proposed doc updates (file/section)
## Verification checklist
