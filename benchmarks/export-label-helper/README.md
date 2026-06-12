# Export Label Helper Benchmark

This benchmark is the first real-world UAT fixture for the VitaClaw FDE skill.

It evaluates whether the skill can transform messy customer materials into operator-grade artifacts and a coding-agent handoff contract.

The benchmark is intentionally outside the core skill doctrine.

## Case Summary

A seafood export business handles PO, AWB, health certificate, printed labels, and a customer-maintained cross-check spreadsheet.

The current manual process checks whether printed labels match the right source documents before shipment.

The desired AI loop is label validation, not label generation.

## What This Benchmark Tests

- Does the skill avoid reducing the case to generic document extraction?
- Does it identify shipment/package as the core operating object?
- Does it separate customer intent, logistics facts, compliance facts, and final label output?
- Does it build a source-authority and comparison matrix?
- Does it control scope and avoid automatic production write-back?
- Does it produce a downstream coding-agent handoff contract?

## Directory Layout

```text
benchmarks/export-label-helper/
├── README.md
├── source-materials/
│   ├── manifest.md
│   ├── final-prd/
│   │   └── PRD.md
│   └── raw-files/
│       └── README.md
├── input/
│   ├── customer_brief.md
│   ├── materials_manifest.md
│   ├── interview_notes.md
│   └── document_facts.md
├── expected/
│   ├── expected_questions.md
│   ├── expected_object_model.md
│   ├── expected_validation_matrix.md
│   └── gold_prd_summary.md
└── results/
    └── .gitkeep
```

## Source Materials

Keep original case materials under `source-materials/` so Codex can read them when refining the benchmark.

Use `source-materials/manifest.md` as the file checklist.

## Evaluation Rule

For holdout-style evaluation, do not expose `expected/` or `source-materials/final-prd/` to the tested skill until after the run is complete.

Use `eval/scoring_rubric.md` and `eval/hallucination_checks.md` to score results.
