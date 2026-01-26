---
name: terraform-module
description: "Scaffold a Terraform module with secure defaults, docs, and validation"
---

Create a maintainable Terraform module scaffold aligned with best practices.
If the repo already has Terraform conventions, follow them.

Inputs:
- Module path: ${input:module:Where should the module live? (e.g., infra/modules/network)}
- Provider: ${input:provider:azurerm|aws|google|other}
- Purpose: ${input:purpose:What should this module create/do?}
- Inputs (variables): ${input:variables:List required variables and their meaning}
- Outputs: ${input:outputs:List desired outputs (optional)}
- Environments: ${input:envs:dev|stage|prod (optional)}

Rules:
- No secrets committed. If credentials are needed, use references/integration guidance only.
- Prefer least privilege and explicit network exposure.
- Add variable validation for critical inputs.
- Provide README usage and examples.
- Provide validation commands (fmt/validate/plan).

Deliver:
1) Proposed module structure and files:
   - main.tf
   - variables.tf
   - outputs.tf
   - versions.tf (if appropriate)
   - README.md (inputs/outputs/usage/assumptions)
   - examples/ (optional)
2) A short “how to use” snippet for consumers.
3) Verification commands and notes about blast radius.

Output:
## Module structure (files)
## Variables and validations
## Outputs
## README content (proposed)
## Commands to run (fmt/validate/plan)
## Risks / rollout notes
