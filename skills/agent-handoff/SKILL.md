# Agent Handoff

Use this skill when a coding task needs continuity, debug delegation, safe commits, release evidence, or collaboration with other agents in the same workspace.

## Triggers

Use this skill when the user says:

- continue
- unblock
- debug
- handoff
- make commits
- coordinate agents
- resume from previous work
- publish safely
- do not lose context

## Workflow

### 1. Read Before Acting

- Read project-level instructions first.
- Check the current directory and repository root.
- Check dirty files without staging anything.
- Identify active constraints from the user.
- If memory, lockfiles, reports, or handoff docs exist, read the most relevant one.

### 2. Establish Current Truth

Record:

- Branch.
- Dirty tracked files.
- Important untracked files only if relevant.
- Running services or blocked services.
- Existing test or build state.
- Known blockers.

Do not infer success from intent. Use evidence.

### 3. Scope Ownership

Before editing, decide:

- Files you may touch.
- Files you must not touch.
- Which changes may be concurrent work.
- Whether a commit is appropriate.

In dirty trees, use exact paths for staging. Never broad-stage.

### 4. Execute

- Make the smallest useful change.
- Follow local project style.
- Add regression tests for bugs.
- Keep generated evidence separate from source edits when possible.
- Avoid unrelated refactors.

### 5. Validate

Run the narrowest meaningful checks first:

- Unit test for the touched module.
- Compile or lint for edited files.
- Smoke command for CLI/runtime changes.
- Artifact verification for generated outputs.

If a check cannot run, state the reason.

### 6. Commit

Commit when:

- The diff is scoped.
- Tests or checks passed.
- No unrelated user changes are staged.

Use exact path staging:

```bash
git add -- path/to/file path/to/test
git commit -m "Clear, module-focused message"
```

### 7. Handoff

End with:

- What changed.
- What was verified.
- Commit hashes.
- Current blockers.
- Next commands.
- Any files intentionally not touched.

Use `templates/HANDOFF.md` when available.

## Debug Agent Brief

When delegating, provide:

- Problem statement.
- Owned files.
- Forbidden files.
- Allowed commands.
- Expected evidence.
- Whether the agent may commit.

Use `templates/DEBUG_BRIEF.md`.

## Public Release Check

Before publishing:

- Remove private names, paths, secrets, datasets, keys, and unpublished assets.
- Check license.
- Keep language generic.
- Verify a clean clone if possible.
- Include only reusable workflow or code.

Use `templates/RELEASE_CHECK.md`.

