# Requirements

Purpose: Capture requirements in a way that is **testable** and **traceable**.
Keep this document stable and version-controlled; avoid “requirements in chat”.

## 1) Scope
- Purpose:
- In-scope:
- Out-of-scope:
- Assumptions:

## 2) Functional requirements (FR)
Use stable IDs: FR-001, FR-002, ...

Template:
- FR-001: <title>
  - Description:
  - Acceptance criteria (testable):
    - AC-001:
    - AC-002:
  - Evidence (where it is proven):
    - Implementation:
    - Tests:
    - Docs/Runbooks:

## 3) Non-functional requirements (NFR)
Use stable IDs: NFR-SEC-001, NFR-OPS-001, ...

Suggested categories:
- Security
- Operability/Observability
- Reliability/Resilience
- Performance/Scalability
- Compliance
- Cost

Template:
- NFR-SEC-001: <title>
  - Description:
  - Acceptance criteria (testable):
  - Evidence (implementation/tests/docs):

## 4) Constraints
- Regulatory/compliance constraints:
- Platform constraints (cloud, runtime, networking):
- Technology constraints:
- Organizational policies:

## 5) Traceability matrix (maintain)
| Requirement | Implementation (paths) | Tests (paths) | Docs (paths) |
|---|---|---|---|
| FR-001 |  |  |  |
