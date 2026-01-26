---
applyTo: "**/*"
description: "Testing baseline (behavior changes require proof)"
---

# Testing baseline
- New behavior requires tests that demonstrate acceptance criteria.
- Bug fixes require a regression test.
- Keep tests deterministic: avoid time/network flakiness; isolate external dependencies.
- If tests are infeasible, document why and provide an alternative verification procedure.
- Prefer small, focused tests with clear intent over broad brittle suites.
