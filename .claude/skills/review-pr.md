# Review PR Skill

Review an existing pull request thoroughly using multiple agents.

## Trigger
User invokes `/review-pr` or asks to "review this PR" with a PR number or URL.

## Steps

1. **Fetch PR details**
   - Get PR diff, description, and changed files via `gh pr view` and `gh pr diff`
   - Identify the scope: which modules/areas are affected

2. **Run agents in parallel**
   - **Code reviewer** — full review of the diff (see agents/code-reviewer.md)
   - **Security auditor** — security-focused review (see agents/security-auditor.md)
   - **Test writer** — check if tests cover the changes, suggest missing tests

3. **Compile report**
   ```
   ## PR Review: #[number] — [title]

   ### Code Review
   [code-reviewer output]

   ### Security
   [security-auditor output]

   ### Test Coverage
   [test-writer assessment]

   ### Verdict
   [approve / request changes / needs discussion]
   ```

4. **Post or present**
   - If user wants: post review as PR comment via `gh pr review`
   - Otherwise: display review in chat

## Options
- `--post` — automatically post the review to GitHub
- `--focus=security` — only run the security audit
- `--focus=tests` — only check test coverage
