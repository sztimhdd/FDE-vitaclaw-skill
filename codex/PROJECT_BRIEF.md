# Project Brief

## Project Name

VitaClaw FDE Onboarding Skill

## Purpose

A minimal, Codex-friendly repository defining an FDE onboarding skill that transforms messy customer materials (documents, field checklists, interviews) into implementation-ready artifacts. The project is focused solely on upstream FDE reasoning, benchmark evaluation, and safe handoffs to coding agents.

## Core Directives

- **No UI/Implementation:** Do not build a web app, OCR/PDF parsing, frontend UI, backend APIs, or meeting copilot features.
- **No Hardcoding:** The generic skill must remain domain-agnostic. The "Export Label Helper" case is kept strictly as a benchmark.
- **Strict Artifact Output:** Outputs must be clean markdown/yaml artifacts.
- **Plan Before Build:** Use `codex/DEVELOPMENT_PLAN.md` as the canonical plan for repository improvement. Implement one batch at a time.

## Development Plan

`codex/DEVELOPMENT_PLAN.md` defines the staged path from the current repo scaffold to a tested FDE Skill MVP.

It includes:

- current repository assessment
- target final repository shape
- file-level quality bar
- development workstreams
- task breakdown
- first implementation batches
- smoke test design
- quality gates
- recommended first implementation prompt

The next implementation session should start with Batch 1 from the development plan unless the user explicitly requests otherwise.

## Success Criteria

The skill succeeds if it can evaluate the messy customer materials in `benchmarks/export-label-helper/` and generate a Mission Brief, Object Model, Validation Matrix, PRD, and Coding Agent Handoff Contract that passes the 100-point rubric in `evals/scoring_rubric.md` (scoring >= 80 for MVP, >= 90 for production).
