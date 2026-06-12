# Manual Evaluation Runbook

This runbook explains how to evaluate the skill against a benchmark case without turning the benchmark into core doctrine.

## Evaluation Modes

### Mode A: Full Context Test

Use when you want to confirm that the skill can structure a case when all relevant input is available.

1. Provide the customer brief.
2. Provide document facts and interview notes.
3. Ask for Mission Brief, Object / State / Action / Evidence Model, Validation Matrix, PRD, and Coding Agent Handoff Contract.
4. Score against `evals/scoring_rubric.md`.

### Mode B: Progressive Discovery Test

Use when you want to test FDE judgment across rounds.

1. Round 1: provide only a vague customer brief.
2. Require the skill to ask discovery questions before producing a full solution.
3. Round 2: provide materials manifest and selected document facts.
4. Round 3: provide interview notes and constraints.
5. Round 4: request final artifacts.
6. Score both the final artifacts and the quality of intermediate questions.

### Mode C: Blind Reconstruction Test

Use when you want the strongest UAT signal.

1. Provide only customer-facing inputs.
2. Do not expose expected outputs or gold summaries.
3. Ask the skill to produce artifacts.
4. Compare outputs against `benchmarks/<case>/expected/` manually.
5. Record results under `benchmarks/<case>/results/`.

## Required Reviewer Checks

For every run, review:

- Did it identify a bounded operator loop?
- Did it separate evidence from inference?
- Did it model the right business objects and states?
- Did it define source-of-truth and conflict handling?
- Did it include eval / acceptance criteria?
- Did it control scope and risk?
- Did it produce a coding-agent handoff contract when implementation is requested?
- Did it avoid benchmark contamination?

## Suggested Result File

Save each result as:

```text
benchmarks/<case>/results/YYYY-MM-DD-model-mode.md
```

Include:

```text
# Eval Result

Benchmark:
Mode:
Model / Runtime:
Date:
Reviewer:

## Score Summary

Total:
Mission Framing:
Operational Reality:
Business Object Model:
Source-of-Truth Reasoning:
Validation / Eval Design:
Scope Control:
Governance:
PRD / Artifact Quality:
Coding-Agent Handoff:

## Hard Fail Checks

## Strengths

## Gaps

## Recommended Skill Updates
```
