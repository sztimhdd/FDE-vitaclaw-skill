# Prompt Library

## Minimum Boot Prompt

Create a new repository called `vitaclaw-fde-onboarding-skill`.

Build only the core scaffold for a reusable FDE onboarding skill.

This project is not a web app. Do not implement OCR, PDF parsing, backend APIs, frontend UI, OpenClaw integration, ASR, TTS, or meeting copilot features.

The purpose of this repository is to define a reusable FDE skill package that can transform messy customer materials and interviews into:

- Mission Brief
- Object Model
- Validation Matrix
- PRD
- Coding Agent Handoff Contract

First implement only:

- README.md
- AGENTS.md
- SKILL.md
- agent/*.md
- skills/*.md
- templates/*.md
- evals/scoring_rubric.md
- codex/PROJECT_BRIEF.md

Keep Export Label Helper as a future benchmark, not hardcoded into the generic skill.

## Development Plan Prompt

Use this when asking a coding agent to inspect the repo and plan work before implementation.

Prompt:

Read `AGENTS.md`, `README.md`, `SKILL.md`, and `codex/PROJECT_BRIEF.md`.

Create or update `codex/DEVELOPMENT_PLAN.md`.

Do not implement code or modify skill behavior yet.

The plan must assess the current repository, define workstreams, list executable tasks, define smoke tests, and recommend the first safe implementation batch.

## Batch 1 Implementation Prompt

Use this after reviewing `codex/DEVELOPMENT_PLAN.md`.

Prompt:

Implement Batch 1 from `codex/DEVELOPMENT_PLAN.md` only.

Read first: `AGENTS.md`, `README.md`, `SKILL.md`, `codex/DEVELOPMENT_PLAN.md`, `benchmarks/export-label-helper/README.md`, `evals/run_manual_eval.md`, `evals/scoring_rubric.md`, `evals/hallucination_checks.md`, and `skills/06_coding_agent_handoff.md`.

Allowed files to edit: `AGENTS.md`, `SKILL.md`, `skills/06_coding_agent_handoff.md`, `benchmarks/export-label-helper/README.md`, `evals/run_manual_eval.md`, and any file containing stale path references to `skill/templates/` or `eval/`.

Forbidden actions: do not build a web UI, do not implement OCR/PDF parsing, do not add backend/frontend code, do not add OpenClaw integration, do not add ASR/TTS or Meeting Copilot features, do not modify benchmark expected files, do not generate benchmark results, do not read expected files as if they were input to the skill, and do not start Batch 2 or Batch 3.

Stop after Batch 1. Summarize changed files and remaining risks.
