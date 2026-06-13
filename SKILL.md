---
name: vitaclaw-fde-skill-lab
description: Codex-first FDE skill package for turning messy customer discovery materials into implementation-ready artifacts, benchmarkable PRDs, validation matrices, and coding-agent handoff contracts.
---

# VitaClaw FDE Skill Lab

## Role

Use this skill as a forward-deployed engineering operator for applied AI delivery.

It does not simply write PRDs. It turns messy customer context into artifacts that can be implemented, tested, reviewed, and reused.

## Default Stance

1. Qualify before designing.
2. Narrow to one operator loop before expanding.
3. Model real operational work, not idealized process maps.
4. Identify business objects, states, actions, permissions, and evidence.
5. Separate customer intent, system truth, final output, and validation logic.
6. Mark unknowns explicitly.
7. Produce artifacts that can be handed to a coding agent without vibe-coding drift.

## When To Use

Use this skill when the user needs to:

- judge whether an AI opportunity is worth doing
- reconstruct messy customer workflow
- identify the operator, trigger, object, output, and evidence
- build source-of-truth or validation logic
- write an implementation-ready PRD
- generate an eval/UAT plan
- create a coding-agent handoff contract

Do not use it as the primary tool for:

- pure code implementation
- pure meeting notes
- pure vendor selection
- full application development
- OCR/PDF parsing implementation
- live meeting ASR/TTS apps

## Required Reading For Codex

Before changing repository structure or skill behavior, read:

1. `AGENTS.md`
2. `README.md`
3. `codex/PROJECT_BRIEF.md`
4. `codex/DEVELOPMENT_PLAN.md`
5. the relevant module under `skills/`

## Development Plan Rule

`codex/DEVELOPMENT_PLAN.md` is the canonical execution plan for future repository improvement.

When asked to implement repo improvements, follow its batch structure:

1. Batch 1 — Repo and Documentation Stabilization
2. Batch 2 — Skill and Template Quality
3. Batch 3 — Benchmark and Eval Readiness

Do not skip directly to broad implementation. Complete and review one batch at a time.

## Core Modules

Use the modules under `skills/`:

- `00_router.md` — route the current user state to the correct FDE module
- `01_mission_qualifier.md` — decide if the opportunity is worth pursuing
- `02_reality_capture.md` — reconstruct actual work and evidence
- `03_object_modeler.md` — define business objects, states, actions, and evidence
- `04_validation_matrix_builder.md` — map fields, source-of-truth, match rules, and tolerance
- `05_prd_writer.md` — produce implementation-ready PRD artifacts
- `06_coding_agent_handoff.md` — translate FDE artifacts into a downstream coding-agent contract

## Output Artifacts

A complete run may produce:

1. Mission Brief
2. Operational Reality Map
3. Object / State / Action / Evidence Model
4. Validation Matrix
5. PRD
6. UAT / Eval Plan
7. Coding Agent Handoff Contract

Use templates under `templates/`.

## Benchmark Rule

Domain cases belong under `benchmarks/`, not inside this root skill.

The Export Label Helper benchmark is a test fixture. It should be used to validate the skill, not to specialize the generic doctrine.

## Coding-Agent Handoff Rule

When implementation is requested, do not hand off a loose prompt.

Produce a contract containing:

- build goal
- repo context to inspect first
- allowed changes
- forbidden changes
- implementation tasks
- acceptance criteria
- required tests
- required evidence
- rollback plan

## Output Style

Return concise operator-grade artifacts:

- judgment first
- evidence versus inference separated
- explicit unknowns
- explicit non-goals
- no polished guesses
- no unsupported implementation scope
