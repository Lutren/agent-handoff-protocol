# Protocol

This protocol is a repeatable loop for agents working in real repositories.

## 1. Intake

Convert the user request into a concrete task.

Ask internally:

- Is the user asking for implementation, review, debugging, planning, or release?
- Is this a local-only task or an external action?
- Is there an existing repo convention?
- Are other agents active?

If the user asks to continue or unblock, start execution after a short status update.

## 2. Workspace Read

Run read-only checks:

```bash
pwd
git status --short --untracked-files=no
git branch --show-current
```

Then inspect relevant files with fast search:

```bash
rg "keyword"
rg --files
```

Use project-specific commands when available.

## 3. Boundary Map

Before editing, classify paths:

- Owned: files needed for this task.
- Adjacent: files to read but not edit.
- Off-limits: private assets, unrelated modules, generated data, or concurrent edits.
- Evidence: reports, logs, screenshots, or generated JSON that prove state.

## 4. Plan By Risk

Use a short plan when the task is broad. Keep it concrete:

1. Reproduce or inspect.
2. Patch.
3. Test.
4. Commit.
5. Handoff.

For small tasks, act directly.

## 5. Patch

Patch the root cause.

Good changes are:

- Local.
- Testable.
- Consistent with nearby code.
- Easy to revert as a unit.
- Backed by a regression test when fixing a bug.

Avoid:

- Broad rewrites.
- Formatting churn.
- Hidden behavior changes.
- Mixing cleanup with feature work.

## 6. Verify

Choose checks that match the risk:

- Unit tests for pure logic.
- Integration tests for cross-module behavior.
- Build checks for packaging.
- Smoke checks for CLIs.
- Render or screenshot checks for UI.
- Checksums or file existence checks for generated artifacts.

Capture exact commands and outcomes.

## 7. Commit

Commit only scoped work.

Recommended command shape:

```bash
git add -- src/module.py tests/test_module.py
git commit -m "Fix module behavior"
```

If the repo is dirty, do not stage unrelated files.

## 8. Handoff

A good handoff lets a fresh agent resume without chat history.

It must answer:

- What is true now?
- What changed?
- What passed?
- What failed or remains blocked?
- What should happen next?
- Which files are relevant?

Use the template in `templates/HANDOFF.md`.

