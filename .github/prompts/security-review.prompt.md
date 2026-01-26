---
name: security-review
description: "Structured security review with prioritized findings and minimal-diff fixes"
---

Perform a security review of a change or component.

Inputs:
- Scope: ${input:scope:Paths/components/features to review}
- Change summary: ${input:change:What changed?}
- Risk focus: ${input:focus:auth|input|deps|secrets|network|all}

Read (as needed):
- `.github/docs/requirements.md` (NFR security requirements)
- `.github/docs/architecture.md` (trust boundaries)
- `.github/docs/state/state.md` (current work context)

Tasks:
1) Identify:
   - assets (data, secrets, credentials)
   - entry points and trust boundaries
2) Check common risk areas:
   - authn/authz correctness
   - input validation / injection risks
   - secrets handling and logging hygiene
   - dependency/supply-chain risks
   - network exposure (IaC/ingress) and least privilege
3) Produce prioritized findings with minimal-diff fixes and verification steps.

Output:
## Findings (Critical/High/Medium/Low)
## Recommended fixes (minimal diffs)
## Verification plan (tests/commands)
## Residual risks / assumptions
