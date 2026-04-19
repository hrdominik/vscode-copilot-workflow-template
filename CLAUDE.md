# Project Instructions for Claude

> This file is automatically loaded by Claude Code. It defines the project context,
> active agents, rules, and skills.

## Project Context
<!-- UPDATE THIS SECTION for your project -->
- **Project:** [Your Project Name]
- **Language:** [e.g., TypeScript, Python, Go]
- **Framework:** [e.g., Next.js, FastAPI, Gin]
- **Package manager:** [e.g., npm, pip, go modules]
- **Test command:** [e.g., `npm test`, `pytest`, `go test ./...`]
- **Lint command:** [e.g., `npm run lint`, `ruff check .`]
- **Build command:** [e.g., `npm run build`]

## Active Rules
<!-- These rules are applied based on the code area being modified -->
- API code → follow `.claude/rules/api.md`
- Database code → follow `.claude/rules/database.md`
- Frontend code → follow `.claude/rules/frontend.md`

## Agents
Use these agents by asking Claude to invoke them:
- `code-reviewer` — review code changes for quality and correctness
- `debugger` — systematically diagnose and fix bugs
- `test-writer` — write tests following project patterns
- `doc-writer` — write/update documentation
- `security-auditor` — audit code for security vulnerabilities

## Skills
- `/commit-push-pr` — commit, push, and create a PR in one workflow
- `/review-pr` — run a multi-agent review on a pull request

## Project Tracking
- Requirements: `docs/REQUIREMENTS.md`
- Architecture: `docs/ARCHITECTURE.md`
- Status: `docs/STATUS.md`

Update tracking docs when:
- Adding/completing features → update STATUS.md
- Making architecture decisions → update ARCHITECTURE.md
- Discovering/changing requirements → update REQUIREMENTS.md

## Code Conventions
<!-- UPDATE for your project -->
- Use existing patterns — read before writing
- Keep changes minimal and focused
- Write tests for new functionality
- No secrets in code — use environment variables
