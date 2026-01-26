# `.github` AI Workflow Pack (VS Code + Copilot)

This folder is a **drop-in workflow pack** for AI-assisted development in VS Code with GitHub Copilot Chat.
It is intentionally **language-agnostic** and optimized for Cloud/DevOps/software work with frequent context switches.

Everything is self-contained under `.github/`:
- **Docs (source of truth)**: `.github/docs/*`
- **Instruction files** (always-on guardrails): `.github/instructions/*`
- **Prompt files** (slash commands): `.github/prompts/*`
- **Agendas** (human-friendly checklists): `.github/agends/*`
- **Repo-wide Copilot instructions**: `.github/copilot-instructions.md`

## 1) Setup in VS Code

### 1.1 Enable instruction files
In VS Code settings, ensure:

```json
{
  "github.copilot.chat.codeGeneration.useInstructionFiles": true
}
```

This makes Copilot automatically apply `.github/copilot-instructions.md` and `.github/instructions/*.instructions.md` where `applyTo` matches.

### 1.2 Use the prompt files (slash commands)
Open Copilot Chat in VS Code and type `/` to see available prompts. Use:

- `/resume` – rehydrate from repo state (no chat history needed)
- `/handover` – update state for the next session
- `/security-review` – structured security assessment
- `/docu-refresh` – update docs (requirements/architecture/runbook notes)
- `/readme-refresh` – refresh README to match reality
- `/terraform-module` – scaffold Terraform module consistently
- `/dockercompose` – create/update local dev compose setup
- `/refactor` – safe refactoring agenda with guardrails

If prompt files do not appear:
- Ensure you are in a **workspace folder** (not a single loose file).
- Ensure the `.github/prompts/*.prompt.md` files exist and are committed.

## 2) How to work (straightforward loop)

### Start of session
1. Update or review `.github/docs/requirements.md` and `.github/docs/architecture.md` (if needed).
2. Run: `/resume` (optionally provide a goal).

### Implement
1. Pick the next task (from you).
2. Use the relevant agenda:
   - `.github/agends/plan.agend.md` for planning
   - `.github/agends/code.agend.md` for code tasks
   - `.github/agends/environment.agend.md` for Docker/IaC tasks
   - `.github/agends/docu.agend.md` for documentation tasks
3. Execute via prompts (preferred):
   - `/dockercompose`, `/terraform-module`, `/refactor`, `/security-review`, `/docu-refresh`, `/readme-refresh`
   - Or follow the agenda checklists and paste the prompt snippets into chat.

### End of session
Run: `/handover` to update `.github/docs/state/state.md` with:
- what is done
- next steps
- open questions/risks
- commands to run next

## 3) Source-of-truth documents
These documents are designed to be the stable “memory” for interrupt/resume:

- `.github/docs/requirements.md` – FR/NFR, acceptance criteria, evidence mapping
- `.github/docs/architecture.md` – components, trust boundaries, operational assumptions
- `.github/docs/state/state.md` – current objective, progress, next steps, commands

## 4) Best-practice guardrails you get automatically
- No secrets committed (explicit rules)
- Minimal diffs and incremental steps
- Tests required for behavioral changes (or explicit justification)
- Security baseline for input boundaries, auth, secrets/logging, dependencies
- IaC guardrails for blast radius, rollout/rollback, secure defaults
- Documentation standards for maintainers-first, factual docs

## 5) Optional: MCP servers (only if you truly need them)
If you routinely need **live cloud/IaC context** (cluster state, deployed config, provider docs), MCP servers can help.
However, keep governance tight—only use allow-listed, trusted servers and prefer read-only tooling.

Recommended candidates for Cloud/DevOps workflows (optional):
- Terraform-focused tooling (provider/module reference)
- Cloud provider tooling (read-only inventory queries)
- Kubernetes tooling (read-only diagnostics)

If you do not need live context, skip MCP and stay repo-grounded via `#codebase`.

---

## What to customize first
- Fill out `.github/docs/requirements.md` and `.github/docs/architecture.md`
- Keep `.github/docs/state/state.md` current
- Adjust `applyTo` globs in `.github/instructions/*.instructions.md` if your repo layout differs
