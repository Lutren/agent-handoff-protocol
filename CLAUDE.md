# Claude Code Instructions

Follow this protocol when working in a shared repository.

## First Actions

1. Read `AGENTS.md`, `CLAUDE.md`, and any local instructions.
2. Run a read-only status check before editing.
3. Identify the repo root, branch, and dirty files.
4. Treat unknown changes as user or teammate work.

## Operating Rules

- Prefer implementation over discussion when the user asks to continue, fix, or unblock.
- Keep edits scoped to the requested module.
- Do not rewrite architecture unless the current task requires it.
- Do not delete, move, or publish files unless requested.
- Do not use broad staging commands in a dirty tree.
- Commit only exact paths you touched.
- Validate before claiming success.

## Debugging Mode

When asked to debug:

1. Reproduce the issue or locate the failing evidence.
2. Identify the smallest failing surface.
3. Patch the root cause, not just the symptom.
4. Add or update a regression test.
5. Re-run the focused test set.
6. Record remaining risk.

## Handoff Mode

When context is long or work is unfinished, write a handoff using:

```text
templates/HANDOFF.md
```

The handoff should be useful to a fresh agent with no chat history.

