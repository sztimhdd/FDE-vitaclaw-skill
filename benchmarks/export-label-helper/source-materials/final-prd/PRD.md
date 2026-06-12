# Export Label Master PRD Reference

This is the benchmark target PRD reference folder.

The full original PRD should be preserved here when binary/text upload is available from a local git client.

## Target Product

Export Label Master is a production-ready export label validation workflow for seafood shipments.

## Core Product Goal

Validate printed shipment labels against the correct source documents:

- PO: customer intent, product lines, packaging, labeling requirements, lot rules
- AWB: logistics facts such as AWB number, flight, routing, pieces, and gross weight
- HC: official compliance facts such as plant, BIP, species, and official weights
- Label: final printed output to compare
- Cross-check spreadsheet: customer-maintained rule seed

## Core Workflow

1. Upload or receive PO, AWB, HC, label, and checklist materials.
2. Classify document types.
3. Extract relevant fields.
4. Group documents into a shipment package.
5. Support incomplete packages because materials may arrive at different times.
6. Validate one or more labels against the package source materials.
7. Show field-by-field results.
8. Let human staff review discrepancies.
9. Archive evidence.

## Core Object Model

```text
Shipment Package
├── PO
├── AWB
├── HC
├── Label(s)
├── extracted fields
├── comparison rules
├── validation results
└── discrepancy records
```

Expected relationship:

```text
1 PO : 1 AWB : 1 HC : N Labels
```

## Critical Fields

- ship_to_name
- plant_number
- awb_number
- flight_number
- net_weight
- gross_weight
- pack_date
- lot_number
- bip
- number_of_cases
- destination
- packaging_type
- size
- piece_count_per_case

## Scope

In scope:

- label validation
- package grouping
- field extraction summary
- discrepancy report
- human review
- evidence archive

Out of scope for MVP:

- final label generation
- carrier system integration
- external filing integration
- automatic production write-back
- automatic business blocking without human review

## Benchmark Use

This file is a target reference. Do not expose it to the tested skill during holdout evaluation.
