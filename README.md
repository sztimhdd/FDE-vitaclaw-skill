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
├── docs/
│   ├── project_brief.md
│   ├── architecture_decisions.md
│   ├── roadmap.md
│   ├── backlog.md
│   └── runtime_portability.md
├── skill/
│   ├── identity.md
│   ├── operating_principles.md
│   ├── modules/
│   │   ├── mission_qualifier.md
│   │   ├── reality_capture.md
│   │   ├── object_modeler.md
│   │   ├── validation_matrix_builder.md
│   │   ├── prd_writer.md
│   │   └── coding_agent_handoff.md
│   └── templates/
│       ├── mission_brief.md
│       ├── object_model.md
│       ├── validation_matrix.md
│       ├── prd.md
│       └── coding_agent_handoff_contract.md
├── benchmarks/
│   └── export-label-helper/
│       ├── README.md
│       ├── source-materials/
│       │   ├── manifest.md
│       │   ├── final-prd/
│       │   │   └── PRD.md
│       │   └── raw-files/
│       │       └── README.md
│       ├── input/
│       ├── expected/
│       └── results/
├── eval/
│   ├── README.md
│   ├── scoring_rubric.md
│   ├── hallucination_checks.md
│   └── run_manual_eval.md
└── archive/
    └── legacy-operator-os/
```

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

Use `skill/templates/coding_agent_handoff_contract.md`.

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

Use `eval/scoring_rubric.md` and `eval/hallucination_checks.md`.

Passing thresholds:

- 90-100: production-quality skill candidate
- 80-89: MVP pass with human review
- 70-79: needs skill/template improvement
- below 70: not operator-grade

## Codex Usage

Before editing, Codex should read:

1. `AGENTS.md`
2. `SKILL.md`
3. `docs/project_brief.md`
4. `docs/architecture_decisions.md`
5. relevant files under `skill/modules/`
6. relevant benchmark files only when running a benchmark

## Maintenance Rule

Keep the repo small and artifact-first.

If a file is not useful to skill behavior, benchmark evaluation, or coding-agent handoff, move it to `archive/` or remove it.
