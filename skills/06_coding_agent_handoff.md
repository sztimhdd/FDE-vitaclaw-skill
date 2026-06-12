# Coding Agent Handoff

## Purpose

Translate FDE artifacts into a contract that a downstream coding agent can implement safely.

## Use When

- the product document is ready for implementation
- Codex or another coding agent will modify files
- implementation requires explicit scope, checks, and evidence

## Required Contract

Use `skill/templates/coding_agent_handoff_contract.md`.

The handoff must include:

- build goal
- business context
- repo context to inspect first
- assumptions to confirm before coding
- allowed changes
- forbidden changes
- implementation tasks
- acceptance criteria
- required checks
- required evidence
- rollback plan
- human review notes

## Failure Signals

- only says "build this"
- no inspect-first file list
- no forbidden changes
- no checks
- no evidence requirement
- no rollback plan
