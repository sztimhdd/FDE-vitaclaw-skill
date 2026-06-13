# VitaClaw FDE Skill Lab

A Codex-first repository for designing, maintaining, and evaluating the VitaClaw FDE onboarding skill.

The repository has one job: turn messy customer discovery materials into implementation-ready artifacts that a downstream coding agent can safely execute.

## What This Repo Is

This repo contains:

- the core FDE skill contract
- reusable skill modules
- output templates
- one preserved real-world benchmark case: Export Label Helper
- evaluation and hallucination checks
- a coding-agent handoff contract for vibe-coding workflows
- a staged development plan for future coding-agent sessions

## What This Repo Is Not

This repo is not:

- a web app
- an OCR/PDF parser project
- a backend/frontend implementation repo
- a meeting recorder or TTS app
- a generic brainstorming prompt collection

Do not add implementation code unless it directly supports skill evaluation or artifact generation.

## Canonical Workflow

```text
messy customer materials
  -> FDE skill modules
  -> Mission Brief / Object Model / Validation Matrix / PRD
  -> Coding Agent Handoff Contract
  -> Codex implementation or evaluation run
```

## Current Clean Directory Structure

```text
.
├── AGENTS.md
├── README.md
├── SKILL.md
├── agent/
│   ├── identity.md
│   ├── operating_principles.md
│   └── soul.md
├── skills/
│   ├── 00_router.md
│   ├── 01_mission_qualifier.md
│   ├── 02_reality_capture.md
│   ├── 03_object_modeler.md
│   ├── 04_validation_matrix_builder.md
│   ├── 05_prd_writer.md
│   └── 06_coding_agent_handoff.md
├── templates/
│   ├── coding_agent_handoff_contract.md
│   ├── mission_brief.md
│   ├── object_model.md
│   ├── prd.md
│   └── validation_matrix.md
├── benchmarks/
│   └── export-label-helper/
├── evals/
│   ├── hallucination_checks.md
│   ├── run_manual_eval.md
│   └── scoring_rubric.md
└── codex/
    ├── DEVELOPMENT_PLAN.md
    ├── PROJECT_BRIEF.md
    ├── TASKS.md
    └── PROMPTS.md
```

## Development Plan

`codex/DEVELOPMENT_PLAN.md` is the canonical plan for future coding-agent work.

Use it before starting implementation. It defines:

- current repository assessment
- target final repository shape
- file-level quality bar
- development workstreams
- task breakdown
- first three implementation batches
- smoke test design
- quality gates
- the recommended first implementation prompt

Do not jump directly from the repo scaffold into broad implementation. Follow the batches in the development plan.

## Core Skill Outputs

A strong run should produce:

1. Mission Brief
2. Operational Reality Map
3. Object / State / Action / Evidence Model
4. Validation Matrix when source-of-truth logic exists
5. PRD
6. UAT / Eval Plan
7. Coding Agent Handoff Contract

## Coding Agent Handoff Contract

The handoff contract is required when FDE artifacts are ready to be implemented by Codex or another coding agent.

It must specify:

- build goal
- business context
- repo context to inspect first
- allowed changes
- forbidden changes
- implementation tasks
- acceptance criteria
- required tests
- required evidence
- rollback plan

Use `templates/coding_agent_handoff_contract.md`.

## Export Label Helper Benchmark

`benchmarks/export-label-helper/` is the first real benchmark case.

It must be preserved because it contains the reference material Codex needs to test whether the FDE skill can reconstruct a real PRD from messy materials.

The benchmark separates:

- source materials
- simulated customer input
- expected outputs
- evaluation results

Do not move benchmark-specific logic into the generic skill.

## Eval Standard

Use `evals/scoring_rubric.md` and `evals/hallucination_checks.md`.

Passing thresholds:

- 90-100: production-quality skill candidate
- 80-89: MVP pass with human review
- 70-79: needs skill/template improvement
- below 70: not operator-grade

## Codex Usage

Before editing, Codex should read:

1. `AGENTS.md`
2. `SKILL.md`
3. `codex/PROJECT_BRIEF.md`
4. `codex/DEVELOPMENT_PLAN.md`
5. relevant files under `skills/`
6. relevant benchmark files only when running a benchmark

## Maintenance Rule

Keep the repo small and artifact-first.

If a file is not useful to skill behavior, benchmark evaluation, project planning, or coding-agent handoff, remove it or explicitly justify why it belongs here.
