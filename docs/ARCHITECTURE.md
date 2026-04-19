# Architecture

> Living document. Update when making structural decisions.
> Use Claude: "update ARCHITECTURE.md with [decision]" to keep this current.

## How to Use
- Document decisions WHEN they're made, not after
- Include the WHY — the reasoning matters more than the choice
- Update diagrams as the system evolves
- Use ADRs (Architecture Decision Records) for significant choices

---

## System Overview

```
[Client] --> [API Gateway] --> [Service Layer] --> [Database]
                                    |
                              [External APIs]
```

_Replace with your actual architecture diagram using Mermaid, ASCII, or a link._

## Tech Stack

| Layer | Technology | Why |
|-------|-----------|-----|
| Frontend | _TBD_ | |
| Backend | _TBD_ | |
| Database | _TBD_ | |
| Infrastructure | _TBD_ | |

## Architecture Decision Records

### ADR-001: _Title_
- **Date:** YYYY-MM-DD
- **Status:** proposed | accepted | deprecated
- **Context:** _What problem are we solving?_
- **Decision:** _What did we choose?_
- **Consequences:** _What are the trade-offs?_

## Directory Structure

```
src/
├── api/          # API routes and controllers
├── services/     # Business logic
├── models/       # Data models / DB schemas
├── utils/        # Shared utilities
└── config/       # Configuration
```

_Update to match your actual project structure._

## Key Patterns

- _Example: Repository pattern for data access_
- _Example: Middleware chain for auth/logging_

---

_Last updated: YYYY-MM-DD_
