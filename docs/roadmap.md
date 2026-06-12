# Roadmap

## Phase 1: Clean Codex-first skill structure

Status: active

- align root README, SKILL, and AGENTS files
- keep concise project docs under `docs/`
- keep reusable modules under `skill/modules/`
- keep reusable templates under `skill/templates/`
- preserve Export Label Helper benchmark
- keep scoring and quality checks under `eval/`

## Phase 2: Benchmark-driven refinement

Status: next

- run Export Label Helper with full context
- run Export Label Helper as a multi-round discovery test
- run Export Label Helper without showing expected outputs first
- record results under `benchmarks/export-label-helper/results/`
- update skill modules only when repeated failures show a pattern

## Phase 3: Coding-agent contract hardening

Status: next

- refine the coding-agent handoff module
- add example handoff contracts
- test Codex implementation prompts against handoff output

## Phase 4: Runtime mapping

Status: later

- map skill package to VitaClaw or OpenClaw runtime concepts
- preserve host-neutral skill behavior
- avoid runtime-specific coupling in core doctrine
