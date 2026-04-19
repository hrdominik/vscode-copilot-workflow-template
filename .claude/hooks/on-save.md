# On-Save Hook

Runs automatically when a file is saved via Claude Code hooks.

## What It Does
1. Auto-format the saved file using project formatter
2. Check for lint errors in the saved file
3. Run related unit tests if in a test-driven workflow
4. Update import organization

## Configuration
This hook is wired in `.vscode/settings.json` under `claude.hooks.onSave`.

## Behavior
- Only operates on the saved file, not the whole project
- Skips non-code files (images, configs, lockfiles)
- Reports errors inline, does not block the save
