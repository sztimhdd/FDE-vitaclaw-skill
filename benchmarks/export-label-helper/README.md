# Export Label Helper Benchmark

This benchmark is a private-case style UAT fixture for evaluating whether `fde-operator-os` can transform messy customer materials into operator-grade FDE artifacts.

The benchmark is intentionally kept outside the core skill doctrine.

## Case Summary

A seafood export business handles PO, AWB, health certificate, printed labels, and a customer-maintained cross-check spreadsheet. The current manual process checks whether labels match the correct source documents before shipment. The desired AI loop is label validation, not label generation.

## What This Benchmark Tests

- Can the skill avoid reducing the case to generic OCR?
- Can it identify the shipment/package as the core operating object?
- Can it separate customer intent, logistics truth, compliance truth, and final label output?
- Can it build a validation matrix from documents, spreadsheet rules, and interview notes?
- Can it control scope and avoid production write-back or blocking automation?
- Can it produce a downstream coding-agent handoff contract?

## Directory Layout

```text
benchmarks/export-label-helper/
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

## Evaluation Rule

Do not expose `expected/` files to the tested skill during blind or progressive evaluation.

Use `evals/scoring_rubric.md` and `evals/hallucination_checks.md` to score results.
