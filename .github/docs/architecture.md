# Architecture

Purpose: Describe the current architecture and operational assumptions in a way that supports:
- implementation
- reviews (security, operability)
- incident/debugging work

Keep this document **accurate** and **aligned with the code and IaC**.

## 1) Context and goals
- System purpose:
- Primary user journeys / workflows:
- Key constraints (compliance, platform, org policies):
- Quality attributes (security, reliability, performance, maintainability):

## 2) High-level structure
### Components / services
For each component:
- Responsibility:
- Interfaces (API/CLI/events):
- Dependencies:
- Data it owns:

### Data stores and messaging
- Datastores (type, ownership, lifecycle):
- Messaging/eventing (topics/queues, contracts, ordering, retries):

## 3) Trust boundaries and security posture
- Entry points (public/private):
- Authentication (where/how):
- Authorization model (roles/claims/policies):
- Sensitive data classification and handling:
- Threat assumptions (what is in/out of scope):

## 4) Operational view
- Deployment model (CI/CD, environments):
- Configuration strategy (env vars, config files, feature flags):
- Secrets strategy (secret manager, rotation assumptions):
- Observability (logs/metrics/traces; correlation IDs; SLOs if any):
- Scaling and resilience assumptions:
- Backup/restore and DR assumptions:

## 5) Change impact notes
When you change architecture/ops behavior, update:
- this document
- `.github/docs/requirements.md` evidence mapping (if acceptance is affected)
- `.github/docs/state/state.md` next steps and commands
