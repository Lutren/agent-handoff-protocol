# AGENTS.md

Use this file as a project-level operating contract for coding agents.

## Startup

At the start of each session:

1. Read this file and any more specific instructions in the current directory.
2. Inspect the workspace before making claims.
3. Check the current directory, repository root, branch, and dirty files.
4. Identify whether other agents or humans may be editing the same tree.
5. Prefer existing project patterns over new abstractions.

## Worktree Discipline

- Never revert changes you did not make unless the human explicitly asks.
- Never use broad staging in a dirty shared tree.
- Stage exact paths only.
- Keep commits small and grouped by module or behavior.
- Do not mix unrelated cleanup into a feature or bug fix.
- If generated files change, explain which command changed them.

## Execution Standard

When the user asks you to continue, fix, implement, or unblock, act instead of only proposing a plan.

Use this loop:

1. Observe: read files, tests, logs, and current state.
2. Decide: state the smallest useful next step.
3. Change: edit only owned files.
4. Verify: run focused tests or checks.
5. Record: commit or write a handoff with exact evidence.

## Evidence Standard

Only mark work complete when you have direct evidence:

- Passing tests.
- Successful build.
- Verified generated artifact.
- Live route response.
- Reproducible command output.
- Reviewed diff with exact paths.

If evidence is missing, say what is missing and why.

## Delegation

Use a debug or worker agent only for a bounded task with clear ownership.

A delegation brief must include:

- Goal.
- Files or modules owned by the agent.
- Files the agent must not touch.
- Commands it may run.
- Expected output.
- Whether it may commit.

## Public Output

Before publishing anything:

1. Remove private paths, names, secrets, unpublished assets, and client-specific details.
2. Check license posture.
3. Prefer generic workflow language.
4. Verify the final files from a clean checkout or fresh clone if possible.

## Handoff

End each long session with:

- Current truth.
- Changes made.
- Tests run.
- Commits made.
- Blockers.
- Next exact commands.
- Files touched.

Use `templates/HANDOFF.md` when available.

