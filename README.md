# Agent Handoff Protocol

A practical handoff workflow for coding agents that share a workspace with a human and other agents.

The goal is simple: keep work resumable, verifiable, and safe when tasks span multiple sessions, tools, models, or contributors.

## What This Is

This repository contains:

- A vendor-neutral agent workflow.
- A Codex-compatible skill in `skills/agent-handoff/SKILL.md`.
- A Claude Code starter file in `CLAUDE.md`.
- A generic `AGENTS.md` you can copy into a workspace.
- Handoff, debugging, commit, and release templates.

It is intentionally small. It does not prescribe a project stack or require a service.

## Quick Start

Landing page: https://lutren.github.io/agent-handoff-protocol/

Announcement issue: https://github.com/Lutren/agent-handoff-protocol/issues/1

Publication gist: https://gist.github.com/Lutren/027e39377fb2e27499ecb0bfa375769d

### For Codex

Copy the skill folder into your Codex skills directory or paste the relevant instructions into your project-level agent instructions:

```text
skills/agent-handoff/SKILL.md
```

Use it when a task needs continuity, debug delegation, commits, release evidence, or safe collaboration with other agents.

### For Claude Code

Copy `CLAUDE.md` into the root of a project, or merge its rules into an existing Claude Code instruction file.

### For Any Agent

Copy `AGENTS.md` into the project root and use `templates/HANDOFF.md` at the end of each session.

## Core Workflow

1. Read local instructions first.
2. Inspect the real workspace before proposing changes.
3. Identify repository boundaries and dirty files.
4. Own only a bounded set of paths.
5. Make small, evidence-backed changes.
6. Validate with commands the next agent can repeat.
7. Commit only the paths you touched.
8. Leave a handoff that states current truth, blockers, tests, and next steps.

## Safety Rules

- Do not claim completion without evidence.
- Do not revert or overwrite unknown changes.
- Do not use broad staging commands in dirty shared trees.
- Do not run destructive cleanup without an explicit target and verification.
- Do not publish, upload, or move user files unless the user asked for that action.
- Treat secrets, private assets, and unpublished work as blocked from public output.

## Repository Contents

```text
AGENTS.md                         Generic workspace instructions
CLAUDE.md                         Claude Code starter instructions
skills/agent-handoff/SKILL.md     Codex skill
docs/PROTOCOL.md                  Full workflow
docs/SAFETY.md                    Safety and boundary rules
templates/HANDOFF.md              End-of-session handoff
templates/DEBUG_BRIEF.md          Debug-agent task brief
templates/COMMIT_LOG.md           Commit notes template
templates/RELEASE_CHECK.md        Public-release checklist
```

## When To Use It

Use this protocol when:

- Work spans more than one session.
- Multiple agents are active.
- A repo is dirty.
- You need commits with verifiable scope.
- You need a debug agent or implementation agent.
- A release or public handoff must not leak private context.

## License

MIT. See `LICENSE`.
