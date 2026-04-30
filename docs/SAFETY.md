# Safety

This project focuses on operational safety for coding agents.

## Shared Worktree Safety

- Treat unknown diffs as someone else's work.
- Do not revert unknown changes.
- Do not stage all files.
- Do not delete generated artifacts unless the task is cleanup and the target is explicit.
- Check exact paths before recursive operations.

## External Action Safety

External actions include:

- Publishing to GitHub or package registries.
- Uploading files.
- Posting to social platforms.
- Moving user files across drives.
- Installing large dependencies or models.
- Starting long-running services.

For external actions:

1. Confirm the user asked for it.
2. Verify the target.
3. Keep the scope minimal.
4. Record evidence.

## Secret Safety

Never publish:

- API keys.
- Tokens.
- Passwords.
- Private paths with identifying details.
- Proprietary datasets.
- Unreleased assets.
- Client-specific logs.

Run a manual scan and, when available, an automated secret scan before release.

## Claims Safety

Do not say:

- "Done" without evidence.
- "Ready" when only a script was generated.
- "Published" before verifying the remote URL.
- "Tested" without naming the command.

Prefer:

- "Implemented and verified with ..."
- "Blocked by ..."
- "Generated but not published ..."
- "Committed as ..."

