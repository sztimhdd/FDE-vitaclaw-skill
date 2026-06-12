# Runtime Portability

The skill should remain host-neutral.

## Supported Hosts

The repository is designed to be readable by:

- Codex
- Claude Code
- OpenClaw / VitaClaw runtime
- Hermes-style prompt pack runtimes
- generic agent systems that can load markdown instructions

## Portability Rule

Do not make the core skill depend on:

- one slash-command system
- one tool registry format
- one agent manifest format
- one UI framework
- one runtime approval system

## Stable Portable Surface

The stable surface is:

- `SKILL.md`
- `AGENTS.md`
- `docs/`
- `skill/modules/`
- `skill/templates/`
- `benchmarks/`
- `eval/`

## Host-specific Layer

Host-specific packaging can be added later under a dedicated adapter folder if needed.

Do not mix host-specific configuration into core skill modules.

## Coding-Agent Handoff

The handoff contract is the bridge between FDE artifacts and implementation agents.

It should stay in plain markdown so any coding agent can consume it.
