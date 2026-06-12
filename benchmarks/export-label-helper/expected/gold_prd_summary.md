# Gold PRD Summary

This file is a compact reference summary for benchmark evaluation. Do not expose it to the tested skill during blind or progressive runs.

## Product Goal

Build an AI-assisted export label validation workflow for seafood shipments. The system validates printed labels against PO, AWB, HC, checklist rules, and interview-derived business rules.

## User Persona

Export coordinator or operations staff responsible for checking labels before shipment.

## Core Workflow

1. Upload or receive PO, AWB, HC, label, and optional checklist.
2. Classify document types.
3. Extract relevant fields.
4. Group source documents into a shipment package.
5. Allow incomplete package state while documents arrive asynchronously.
6. Upload or select a label for validation.
7. Compare label fields against authoritative source fields.
8. Show match, mismatch, missing, warning, and informational results.
9. Let human staff review, override, screenshot, or archive results.

## Core Business Object

`Shipment Package` is the central object.

Expected relationship:

```text
1 PO : 1 AWB : 1 HC : N Labels
```

## Critical Logic

- PO = customer intent and label requirements.
- AWB = logistics truth.
- HC = compliance truth.
- Label = final physical output to check.
- Checklist = customer rule seed, not complete product spec.
- Interview notes clarify authority, exceptions, tolerance, and scope boundaries.

## MVP Scope

In scope:

- label validation
- field extraction summary
- package grouping
- discrepancy report
- human review
- screenshots / archive evidence

Out of scope:

- label generation
- carrier system integration
- external filing integration
- automatic production write-back
- blocking shipment automatically

## Expected PRD Sections

1. Executive Summary
2. User Persona
3. Source Documents
4. Package Object Model
5. Field Extraction Matrix
6. Validation Rules
7. UI / Workflow
8. Data Model / API Direction
9. Error Handling
10. Monitoring / Archiving
11. Out of Scope
12. UAT Criteria
13. Future Roadmap

## Expected Coding-Agent Handoff

A strong handoff should specify:

- build goal: export label validation MVP
- repo context to inspect first
- allowed changes
- forbidden changes
- implementation tasks
- required tests
- evidence required
- rollback notes
