# VS Code Copilot & AI Workflow Template

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![VS Code](https://img.shields.io/badge/VS%20Code-1.80%2B-blue.svg)](https://code.visualstudio.com/)
[![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Enabled-6f42c1.svg)](https://github.com/features/copilot)
[![Language-Agnostic](https://img.shields.io/badge/Language-Agnostic-brightgreen.svg)]()

> A drop-in, language-agnostic workflow pack for AI-assisted software development and Cloud/DevOps engineering in Visual Studio Code with GitHub Copilot Chat.

---

## 📌 Overview

**VS Code Copilot Workflow Template** is a lightweight, drop-in workflow framework tailored for software developers, Cloud/DevOps engineers, and system architects. 

In modern engineering environments—especially Cloud and DevOps roles—you frequently switch between Infrastructure as Code (Terraform, Bicep, Helm), backend services (Go, Python, TypeScript, Rust), CI/CD pipelines, and configuration management. Standardizing AI behavior and maintaining project context across these context switches can be frustrating.

This template provides a **turnkey operational structure** for AI coding assistants (GitHub Copilot Chat, Claude Code, Cursor, and others) inside VS Code:

- 🌐 **Language-Agnostic Core** — Works seamlessly across any programming language, cloud framework, or DevOps stack.
- 🔄 **Optimized for Context Switching** — Structured context files let you and your AI assistant pick up right where you left off without tedious re-explanation.
- 🤖 **Specialized AI Personas** — Pre-configured agent personas for code review, debugging, security auditing, test generation, and technical documentation.
- 🎯 **Domain-Specific Rules** — Modular guardrails for REST APIs, database queries, frontend components, and cloud infrastructure.
- 📚 **Living Documentation** — Standardized tracking templates (`docs/`) for requirements, architecture decisions (ADRs), and development status.

---

## 📂 Repository Structure

```text
.
├── README.md                    # Public overview & setup guide
├── CLAUDE.md                    # Core AI assistant instructions & project metadata
├── CLAUDE.local.example.md      # Personal developer overrides template (gitignored)
├── AI_README.md                 # In-depth AI system reference manual
│
├── .claude/                     # AI workspace configurations & modular assets
│   ├── agents/                  # Specialized AI persona definitions
│   │   ├── code-reviewer.md     # Code quality, maintainability & style review
│   │   ├── debugger.md          # Systematic root-cause bug diagnosis
│   │   ├── test-writer.md       # Unit, integration & regression test generator
│   │   ├── doc-writer.md        # Technical docs & inline documentation writer
│   │   └── security-auditor.md  # OWASP-aligned security vulnerability auditor
│   ├── hooks/                   # Quality gate definitions & pre-commit hooks
│   │   ├── pre-commit.md        # Pre-commit security & debug code checks
│   │   └── on-save.md           # On-save syntax & lint validation
│   ├── rules/                   # Domain-specific coding guardrails
│   │   ├── api.md               # REST / gRPC API standards & error handling
│   │   ├── database.md          # Query safety, indexing & migration rules
│   │   └── frontend.md          # Component structure & accessibility patterns
│   └── skills/                  # Multi-step automated workflow definitions
│       ├── commit-push-pr.md    # Staged review -> commit -> push -> PR workflow
│       └── review-pr.md         # Multi-agent automated PR review execution
│
├── docs/                        # Living Project Documentation
│   ├── REQUIREMENTS.md          # Feature tracking & functional specifications
│   ├── ARCHITECTURE.md          # System overview & Architecture Decision Records (ADRs)
│   └── STATUS.md                # Sprint progress, blockers & development log
│
└── .vscode/
    └── settings.json            # VS Code workspace AI settings & hook integration
```

---

## 🚀 Quick Start

### 1. Using as a Template or Drop-in Pack

#### Option A: Create a New Repository
Click the **"Use this template"** button on GitHub, or clone locally:
```bash
git clone https://github.com/your-username/vscode-copilot-workflow-template.git my-new-project
cd my-new-project
rm -rf .git && git init
```

#### Option B: Drop into an Existing Repository
Copy the workflow assets directly into your current workspace:
```bash
cp -r .claude docs CLAUDE.md .vscode/settings.json /path/to/your-existing-repo/
```

### 2. Configure Project Context

Open `CLAUDE.md` (or your preferred AI workspace configuration) and define your project settings:

```markdown
## Project Context
- **Project:** Cloud Infrastructure API
- **Language:** Go / Terraform
- **Framework:** Gin / AWS SDK
- **Test command:** `go test -v ./...`
- **Lint command:** `golangci-lint run`
- **Build command:** `go build -o bin/server .`
```

### 3. Open in VS Code

Launch Visual Studio Code with GitHub Copilot Chat installed:
```bash
code .
```

---

## 💡 How to Work with AI Assistants

### 🤖 Prompting Specialized AI Agents

You can invoke specialized agent personas directly in your chat prompt (e.g., GitHub Copilot Chat, Claude Code):

| Persona | Example Prompt | Description |
| :--- | :--- | :--- |
| **Code Reviewer** | `"Review the changes in src/api/ for quality and security"` | Evaluates diffs against clean code and project standards |
| **Debugger** | `"Diagnose the connection timeout in worker.go"` | Performs systematic root-cause diagnosis |
| **Test Writer** | `"Write unit tests for the authentication handler"` | Generates comprehensive test suites matching project patterns |
| **Security Auditor** | `"Audit the cloud deployment scripts for hardcoded secrets"` | Scans code for OWASP vulnerabilities and credential leaks |
| **Doc Writer** | `"Update ARCHITECTURE.md with our new caching strategy"` | Maintains technical documentation and ADRs |

### 📚 Maintaining Living Documentation

Keep your context fresh when switching projects or context-switching between operational tasks:

- **Requirements (`docs/REQUIREMENTS.md`)**: Track functional/non-functional items with status tags (`[planned]`, `[in-progress]`, `[done]`).
- **Architecture (`docs/ARCHITECTURE.md`)**: Record structural decisions using lightweight ADR formats.
- **Development Status (`docs/STATUS.md`)**: Update at the end of a session so you can resume work instantly next time.

---

## 🤝 Contributing

Contributions are greatly appreciated! If you have suggestions for improving workflow definitions, adding DevOps/Cloud guardrails, or enhancing AI instructions:

1. **Fork the Project**
2. **Create a Feature Branch** (`git checkout -b feature/devops-rules`)
3. **Commit Your Changes** (`git commit -m "feat: add Kubernetes and Helm rule templates"`)
4. **Push to the Branch** (`git push origin feature/devops-rules`)
5. **Open a Pull Request**

### Contribution Guidelines
- Keep core workflows **language-agnostic** and modular.
- Ensure new rules are placed in `.claude/rules/` and properly referenced.
- Maintain clean, professional documentation standards.

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](file:///Users/dominik.hoehr/Workspaces/repos/private/vscode-copilot-workflow-template/LICENSE) for full details.
