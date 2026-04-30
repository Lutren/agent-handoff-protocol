# Publication Kit

Use these short posts to announce Agent Handoff Protocol.

## Short Post

Agent Handoff Protocol is now available as an open-source workflow for coding agents working in shared repositories.

It includes a generic `AGENTS.md`, a Claude Code starter file, a Codex-compatible skill, and reusable handoff/debug/release templates.

GitHub: https://github.com/Lutren/agent-handoff-protocol

## Longer Post

I published Agent Handoff Protocol, a small open-source workflow for coding agents that need to collaborate safely in real repositories.

It focuses on practical execution:

- read local instructions first
- inspect dirty worktrees before editing
- own bounded paths
- avoid overwriting human or agent work
- validate before claiming success
- commit exact paths only
- leave a handoff a fresh agent can actually use

The repo includes:

- `AGENTS.md`
- `CLAUDE.md`
- Codex skill: `skills/agent-handoff/SKILL.md`
- templates for handoff, debugging, commits, and release checks

GitHub: https://github.com/Lutren/agent-handoff-protocol

## One-Line Description

A practical handoff workflow for coding agents in shared repositories.

