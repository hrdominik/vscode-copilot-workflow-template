---
applyTo: "**/*"
description: "Security baseline (repo-wide)"
---

# Security baseline
- Treat all external input as untrusted; validate at trust boundaries.
- Prefer allow-lists for validation and authorization.
- Avoid logging secrets or sensitive data; minimize PII exposure.
- For authn/authz/crypto/dependency/network changes:
  - enumerate threats and mitigations
  - add negative tests / misuse cases where practical
  - document residual risk explicitly
- Favor least privilege and explicit network exposure (no public endpoints by default).
