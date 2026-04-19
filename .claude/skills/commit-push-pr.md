# Commit, Push & PR Skill

Multi-step workflow to commit changes, push to remote, and create a pull request.

## Trigger
User invokes `/commit-push-pr` or asks to "commit and create a PR".

## Steps

1. **Review changes**
   - Run `git status` and `git diff --staged`
   - If nothing staged, stage relevant changed files (ask user if ambiguous)
   - Run the code-reviewer agent on the diff

2. **Commit**
   - Generate a concise commit message: type(scope): description
   - Types: feat, fix, refactor, test, docs, chore
   - Commit with the message (let pre-commit hook run)

3. **Push**
   - Push to the current branch with `-u` flag
   - If no remote branch exists, create it

4. **Create PR**
   - Generate PR title from commit message(s)
   - Generate PR body with:
     - Summary (2-3 bullets of what changed and why)
     - Test plan (how to verify)
     - Checklist: tests pass, no security issues, docs updated
   - Create PR via `gh pr create`
   - Return the PR URL

## Abort Conditions
- Pre-commit hook fails → fix issues first
- Code reviewer finds critical issues → address before PR
- No changes to commit → inform user
