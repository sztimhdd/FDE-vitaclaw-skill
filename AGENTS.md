# Repository Agent Instructions

These instructions apply to coding agents working in this repository.

## Mission

Maintain `fde-operator-os` as a host-neutral Applied AI / FDE skill pack that turns messy operational problems into delivery-worthy AI operating loops and reusable assets.

## Hard Boundaries

- Do not build a web UI in this repository.
- Do not implement OCR, PDF parsing, backend APIs, frontend screens, ASR, TTS, or meeting-copilot features as part of the core skill.
- Do not hardcode any single customer case into the generic skill doctrine.
- Keep reusable FDE methodology separate from benchmark and case-pack material.
- Keep domain cases under `examples/` or `benchmarks/`, not inside the root `SKILL.md` doctrine.
- Treat benchmarks as test fixtures, not product requirements.

## Required Reading Before Editing

Before changing skill behavior, read:

1. `SKILL.md`
2. `README.md`
3. `references/doctrine.md`
4. `references/runtime-portability.md`

Before changing benchmark or eval behavior, also read:

1. `evals/scoring_rubric.md`
2. `evals/hallucination_checks.md`
3. the relevant `benchmarks/<case>/README.md` if present

## Output Discipline

- Prefer small, durable markdown artifacts over large narrative documents.
- Preserve the current core + suite structure.
- Add new leaf skills only when they represent a repeatable request shape.
- Every new benchmark should include inputs, expected outputs, and scoring criteria.
- Mark unknowns explicitly instead of smoothing them over.
- Separate evidence from inference.

## Coding-Agent Handoff Discipline

When this skill prepares work for a downstream coding agent, produce a handoff contract rather than a loose implementation request. The contract must include:

- build goal
- repo context to inspect first
- allowed changes
- forbidden changes
- implementation tasks
- acceptance criteria
- required tests
- required evidence
- rollback notes

## Current Roadmap Boundary

Current focus:

1. FDE skill package
2. benchmark case packs
3. evaluation and scoring harness
4. coding-agent handoff contract
5. runtime-portable documentation

Backlog only, not current roadmap:

- real-time meeting assistant
- silent meeting copilot
- ASR/TTS customer-interview insertion
- production browser automation
- external system write-back tools
