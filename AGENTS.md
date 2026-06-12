# AGENTS.md

Repository instructions for Codex and other coding agents.

## Mission

Maintain this repo as a clean Codex-first FDE skill lab.

The repo should help an agent transform messy customer materials into:

- Mission Brief
- Object / State / Action / Evidence Model
- Validation Matrix
- PRD
- UAT / Eval Plan
- Coding Agent Handoff Contract

## Read First

Before editing anything, read:

1. `README.md`
2. `SKILL.md`
3. `docs/project_brief.md`
4. `docs/architecture_decisions.md`
5. relevant files under `skill/modules/`

When running Export Label Helper tests, read:

1. `benchmarks/export-label-helper/README.md`
2. `benchmarks/export-label-helper/source-materials/manifest.md`
3. `benchmarks/export-label-helper/input/*`
4. expected files only after the test run is complete

## Hard Boundaries

Do not build these in this repo:

- web UI
- backend service
- frontend app
- OCR/PDF parser
- ASR/TTS
- meeting copilot
- production browser automation
- external system write-back tools

Do not hardcode benchmark-specific logic into the generic skill.

## Directory Discipline

Use the current clean structure:

- `docs/` for project-level decisions and rationale
- `skill/` for reusable skill behavior, modules, and templates
- `benchmarks/` for case packs and source materials
- `eval/` for scoring and hallucination checks
- `archive/` for old material not needed by active Codex work

Do not add new top-level folders unless necessary.

## Output Discipline

- Prefer short markdown files over long mixed-purpose documents.
- Keep each file single-purpose.
- Separate evidence from inference.
- Mark unknowns explicitly.
- Keep generic skill doctrine separate from benchmark cases.
- Update README whenever the directory structure changes.

## Coding-Agent Handoff Discipline

When preparing implementation work, produce a handoff contract rather than a loose vibe-coding prompt.

The contract must include:

- build goal
- repo context to inspect first
- allowed changes
- forbidden changes
- implementation tasks
- acceptance criteria
- required tests
- required evidence
- rollback plan

Use `skill/templates/coding_agent_handoff_contract.md`.
