# Expected Discovery Questions

A strong run should ask questions like these before producing a final PRD.

## Operator And Workflow

- Who performs the label check today?
- At what point in the shipment workflow does the check happen?
- What happens when a mismatch is found?
- Who has authority to approve, override, or request correction?

## Source Documents

- Which document is authoritative for each critical field?
- What happens when PO, AWB, HC, and label disagree?
- Do documents arrive together or asynchronously?
- Can a shipment package be incomplete while still visible in the system?

## Field Rules

- Which fields are critical versus informational?
- Which fields need exact match, fuzzy match, normalization, or tolerance?
- Which fields are required only for EU shipments or certain customers?
- How is lot number generated or formatted?

## Product And Label Scope

- Does the system validate one label at a time or multiple labels per shipment?
- Can one shipment have multiple product labels?
- Are different customers using different label templates?

## Automation Boundary

- Should the system block shipment, create a warning, or only generate a review report?
- What must remain human-owned?
- What evidence should be saved for audit or later review?

## MVP Boundary

- Should the first version generate labels or only validate labels?
- Are carrier, filing, or external system integrations in scope?
- What is the minimum acceptable validation result for a pilot?
