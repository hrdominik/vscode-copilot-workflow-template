# VS Code Claude Template

A ready-to-use project template for AI-assisted software development with Claude Code in VS Code. Clone this repo, customize `CLAUDE.md`, and start building with intelligent agents, automated hooks, and structured workflows.

---

## Table of Contents

- [VS Code Claude Template](#vs-code-claude-template)
  - [Table of Contents](#table-of-contents)
  - [Quick Start](#quick-start)
  - [What's Included](#whats-included)
  - [Project Structure](#project-structure)
  - [How to Use](#how-to-use)
    - [Setting Up a New Project](#setting-up-a-new-project)
    - [Working with Agents](#working-with-agents)
    - [Using Skills](#using-skills)
      - [`/commit-push-pr`](#commit-push-pr)
      - [`/review-pr`](#review-pr)
    - [Hooks](#hooks)
    - [Rules](#rules)
    - [Tracking Requirements \& Architecture](#tracking-requirements--architecture)
      - [`docs/REQUIREMENTS.md`](#docsrequirementsmd)
      - [`docs/ARCHITECTURE.md`](#docsarchitecturemd)
      - [`docs/STATUS.md`](#docsstatusmd)
  - [Development Workflows](#development-workflows)
    - [Starting a New Feature](#starting-a-new-feature)
    - [Fixing a Bug](#fixing-a-bug)
    - [Reviewing Code](#reviewing-code)
    - [Shipping a Release](#shipping-a-release)
  - [Customization](#customization)
    - [Adding a New Agent](#adding-a-new-agent)
    - [Adding a New Rule](#adding-a-new-rule)
    - [Adding a New Skill](#adding-a-new-skill)
    - [Removing Unused Components](#removing-unused-components)
  - [File Reference](#file-reference)
  - [Tips](#tips)
  - [License](#license)

---

## Quick Start

```bash
# 1. Clone/copy this template into your new project
git clone <this-repo-url> my-project
cd my-project
rm -rf .git && git init

# 2. Customize CLAUDE.md with your project details
#    - Set your language, framework, package manager
#    - Set your test/lint/build commands

# 3. Set up your local overrides (optional, not committed)
cp CLAUDE.local.example.md CLAUDE.local.md

# 4. Open in VS Code with Claude Code extension installed
code .

# 5. Start talking to Claude — it reads CLAUDE.md automatically
```

**Prerequisites:**
- VS Code with [Claude Code extension](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code) installed
- GitHub CLI (`gh`) installed for PR workflows
- Git configured with your identity

---

## What's Included

| Category | Files | Purpose |
|----------|-------|---------|
| **Agents** | 5 specialized AI agents | Code review, debugging, testing, docs, security |
| **Hooks** | Pre-commit, on-save | Automated quality checks |
| **Rules** | API, database, frontend | Domain-specific coding standards |
| **Skills** | commit-push-pr, review-pr | Multi-step automated workflows |
| **Tracking** | Requirements, architecture, status | Living project documentation |

---

## Project Structure

```
your-project/
├── CLAUDE.md                    # Main AI config (edit this first!)
├── CLAUDE.local.example.md      # Template for personal overrides
├── README.md                    # This file — your project docs
│
├── .claude/
│   ├── agents/                  # Agent instruction files
│   │   ├── code-reviewer.md     # Code quality review
│   │   ├── debugger.md          # Systematic bug diagnosis
│   │   ├── test-writer.md       # Test generation
│   │   ├── doc-writer.md        # Documentation writer
│   │   └── security-auditor.md  # Security vulnerability audit
│   │
│   ├── hooks/                   # Hook documentation & config
│   │   ├── pre-commit.md        # Pre-commit checks
│   │   └── on-save.md           # On-save actions
│   │
│   ├── rules/                   # Domain-specific rules
│   │   ├── api.md               # REST API conventions
│   │   ├── database.md          # Database & query rules
│   │   └── frontend.md          # Frontend/UI rules
│   │
│   └── skills/                  # Multi-step workflows
│       ├── commit-push-pr.md    # Commit → push → create PR
│       └── review-pr.md         # Multi-agent PR review
│
├── docs/
│   ├── REQUIREMENTS.md          # Living requirements tracker
│   ├── ARCHITECTURE.md          # Architecture decisions
│   └── STATUS.md                # Current development state
│
└── .vscode/
    └── settings.json            # Claude Code hooks & config
```

---

## How to Use

### Setting Up a New Project

1. **Edit `CLAUDE.md`** — This is the first file Claude reads. Update the Project Context section:
   ```markdown
   ## Project Context
   - **Project:** My App
   - **Language:** TypeScript
   - **Framework:** Next.js
   - **Test command:** `npm test`
   - **Lint command:** `npm run lint`
   - **Build command:** `npm run build`
   ```

2. **Create `CLAUDE.local.md`** from the example — Add your personal preferences and local environment details. This file is gitignored and won't be committed.

3. **Fill in tracking docs** — Open `docs/REQUIREMENTS.md` and start listing what you're building. Claude will help keep these updated as you work.

4. **Remove unused rules** — If your project doesn't have a frontend, delete `.claude/rules/frontend.md`. Keep only what applies.

### Working with Agents

Agents are specialized AI personas that Claude can adopt. Invoke them by asking:

| Agent | How to Invoke | What It Does |
|-------|--------------|--------------|
| **Code Reviewer** | "Review this code" / "Run code-reviewer on my changes" | Reviews diffs for bugs, security, performance, readability |
| **Debugger** | "Debug this error" / "Help me fix this bug" | Systematic root-cause analysis |
| **Test Writer** | "Write tests for this" / "Add test coverage" | Generates tests matching your project patterns |
| **Doc Writer** | "Document this" / "Update the docs" | Writes/updates documentation |
| **Security Auditor** | "Audit this for security" / "Security check" | OWASP-focused vulnerability scan |

**Example:**
```
You: Review the changes I made to src/api/users.ts
Claude: [Adopts code-reviewer agent, provides structured review]
```

Agents are defined in `.claude/agents/`. Edit them to match your team's standards.

### Using Skills

Skills are multi-step workflows you invoke like commands:

#### `/commit-push-pr`
Automates the full commit-to-PR flow:
1. Reviews your staged changes
2. Generates a conventional commit message
3. Pushes to remote
4. Creates a PR with summary and test plan

```
You: /commit-push-pr
Claude: [Reviews changes, commits, pushes, creates PR, returns URL]
```

#### `/review-pr`
Runs a comprehensive multi-agent review on a PR:
1. Fetches the PR diff
2. Runs code-reviewer + security-auditor + test-writer in parallel
3. Compiles a structured review report

```
You: /review-pr 42
Claude: [Fetches PR #42, runs 3 agents, presents combined review]
```

### Hooks

Hooks run automatically at specific points in your workflow:

| Hook | Trigger | What It Checks |
|------|---------|---------------|
| **Pre-commit** | Before each `git commit` | Debug statements, secrets, missing tests, skipped tests |
| **On-save** | File save (disabled by default) | Syntax errors, lint issues |

**Enable/disable hooks** in `.vscode/settings.json`:
```json
{
  "claude.code.hooks": {
    "preCommit": { "enabled": true },
    "onSave": { "enabled": false }
  }
}
```

### Rules

Rules are automatically applied when Claude works on code in specific domains:

- **`api.md`** — RESTful conventions, input validation, error handling, pagination
- **`database.md`** — Parameterized queries, migrations, indexing, transactions
- **`frontend.md`** — Component design, state management, accessibility, security

Claude reads these from `CLAUDE.md` and applies the relevant rules based on what files you're editing. Add or remove rules as needed.

### Tracking Requirements & Architecture

Three living documents in `docs/` help you maintain project context:

#### `docs/REQUIREMENTS.md`
Track what you're building. Use status tags: `[planned]`, `[in-progress]`, `[done]`, `[cut]`.

```
You: Add a requirement: users can reset their password via email, high priority
Claude: [Updates REQUIREMENTS.md with FR-003]
```

#### `docs/ARCHITECTURE.md`
Record structural decisions using ADRs (Architecture Decision Records). Include the WHY.

```
You: We decided to use PostgreSQL because we need JSONB support and strong consistency
Claude: [Adds ADR-002 to ARCHITECTURE.md]
```

#### `docs/STATUS.md`
Track current sprint progress. Update after each work session.

```
You: Update status — auth module is done, starting on the API layer
Claude: [Moves auth to done, adds API tasks as in-progress]
```

---

## Development Workflows

### Starting a New Feature

```
1. Define requirements
   You: "Add requirement: user can upload profile photos, medium priority"
   → Claude updates docs/REQUIREMENTS.md

2. Plan architecture
   You: "How should we implement file uploads? Update architecture doc"
   → Claude discusses options, adds ADR to docs/ARCHITECTURE.md

3. Implement
   You: "Implement the file upload endpoint following our API rules"
   → Claude writes code following .claude/rules/api.md

4. Test
   You: "Write tests for the upload endpoint"
   → Claude uses test-writer agent, follows project test patterns

5. Review & ship
   You: "/commit-push-pr"
   → Claude reviews, commits, pushes, creates PR

6. Update status
   You: "Update status — file upload is done"
   → Claude updates docs/STATUS.md
```

### Fixing a Bug

```
1. Diagnose
   You: "Users are getting 500 errors on login. Debug this."
   → Claude uses debugger agent, traces the issue

2. Fix
   You: "Fix it"
   → Claude applies the minimal correct fix

3. Verify
   You: "Write a regression test for this bug"
   → Claude uses test-writer agent

4. Ship
   You: "/commit-push-pr"
   → Pre-commit hook validates, Claude creates fix PR
```

### Reviewing Code

```
1. Review a PR
   You: "/review-pr 42"
   → Claude runs code-reviewer + security-auditor + test-writer

2. Review local changes
   You: "Review my staged changes"
   → Claude runs code-reviewer on the diff

3. Security audit
   You: "Run a security audit on src/auth/"
   → Claude uses security-auditor agent on the directory
```

### Shipping a Release

```
1. Check status
   You: "What's the current status? Are we ready to release?"
   → Claude reads docs/STATUS.md, checks for blockers

2. Final review
   You: "Run security auditor on the whole project"
   → Claude audits all code for vulnerabilities

3. Update docs
   You: "Update all docs for the v1.0 release"
   → Claude uses doc-writer to update README, ARCHITECTURE, STATUS
```

---

## Customization

### Adding a New Agent

1. Create `.claude/agents/your-agent.md` with role, process, output format, and rules
2. Register it in `.vscode/settings.json` under `claude.code.agents`
3. Reference it in `CLAUDE.md` under the Agents section

### Adding a New Rule

1. Create `.claude/rules/your-domain.md` with constraints and examples
2. Reference it in `CLAUDE.md` under Active Rules

### Adding a New Skill

1. Create `.claude/skills/your-skill.md` with trigger, steps, and abort conditions
2. Register it in `.vscode/settings.json` under `claude.code.skills`
3. Reference it in `CLAUDE.md` under Skills

### Removing Unused Components

Delete the files and remove references from `CLAUDE.md` and `.vscode/settings.json`. Claude only loads what's referenced.

---

## File Reference

| File | Purpose | Edit Frequency |
|------|---------|---------------|
| `CLAUDE.md` | Main AI config — project context, active agents/rules/skills | Once at setup, rarely after |
| `CLAUDE.local.md` | Personal overrides (gitignored) | Per developer |
| `docs/REQUIREMENTS.md` | What we're building | As requirements change |
| `docs/ARCHITECTURE.md` | How we're building it | When making structural decisions |
| `docs/STATUS.md` | Where we are now | Every work session |
| `.claude/agents/*.md` | Agent behavior instructions | When refining AI behavior |
| `.claude/rules/*.md` | Domain coding standards | When standards evolve |
| `.claude/skills/*.md` | Multi-step workflow definitions | When adding/changing workflows |
| `.vscode/settings.json` | Hook wiring and Claude Code config | When adding hooks/agents/skills |

---

## Tips

- **Be specific** — "Review src/api/auth.ts for security issues" works better than "check my code"
- **Keep CLAUDE.md updated** — It's Claude's main context. Outdated info leads to wrong suggestions.
- **Use tracking docs** — They help Claude understand your project's goals and current state
- **Customize agents** — Edit agent files to match your team's review standards and preferences
- **Start small** — Enable hooks and agents incrementally. Don't activate everything at once.

---

## License

Distributed under the MIT License. See [LICENSE](file:///Users/dominik.hoehr/Workspaces/repos/private/vscode-copilot-workflow-template/LICENSE) for more information.
