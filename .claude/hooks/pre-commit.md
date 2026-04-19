# Pre-Commit Hook

Runs automatically before each commit via Claude Code hooks.

## What It Does
1. Lint staged files for syntax errors
2. Run the security auditor on changed files
3. Check for secrets/credentials in staged changes
4. Validate that tests pass for modified modules
5. Ensure docs/STATUS.md is updated if code changed

## Configuration
This hook is wired in `.vscode/settings.json` under `claude.hooks.preCommit`.

## Checks
- [ ] No `console.log` / debug statements left in production code
- [ ] No hardcoded secrets, tokens, or passwords
- [ ] No `TODO` or `FIXME` without an associated issue number
- [ ] All new functions have corresponding tests
- [ ] No skipped tests (`.skip`, `xit`, `xdescribe`)
