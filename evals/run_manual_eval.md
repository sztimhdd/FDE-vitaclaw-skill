# Manual Eval Runbook

## Mode 1: Full Context

1. Give the skill all benchmark input files.
2. Ask for the full artifact set.
3. Score with `eval/scoring_rubric.md`.

## Mode 2: Progressive Discovery

1. Start with only `input/customer_brief.md`.
2. Require discovery questions.
3. Add source facts and interview notes in later rounds.
4. Ask for final artifacts.
5. Score both questions and final output.

## Mode 3: Expected-Answer Holdout

1. Provide only input files.
2. Do not expose `expected/` files first.
3. Generate artifacts.
4. Compare manually with expected files.
5. Save results under `benchmarks/export-label-helper/results/`.

## Result File Format

```text
# Eval Result

Benchmark:
Mode:
Runtime:
Date:
Reviewer:

## Score

## Strengths

## Gaps

## Hallucination Checks

## Recommended Updates
```
