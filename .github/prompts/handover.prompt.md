---
name: handover
description: "Update state so the next session can resume without chat history"
---

Create an end-of-session handover by updating `.github/docs/state/state.md`.

Optional note from the engineer:
${input:note:Anything important to include? (optional)}

Tasks:
1) Update state with:
   - current objective and success criteria
   - Done / In progress / Blocked
   - Next steps (top 3–7)
   - Open questions and risks
2) Add concrete commands to run next (setup/build/test/run/IaC/compose as relevant).
3) If a decision changed architecture, propose what to update in `.github/docs/architecture.md` (and recommend an ADR only if needed).

Output:
## State update summary (what to write)
## Resume commands
## Follow-ups / risks
