# Expected Object Model

A strong output should identify the shipment package as the core operating object.

## Core Objects

### Shipment Package

Represents one shipment validation unit.

Expected relationships:

- one PO
- one AWB
- one HC
- one or more labels
- many extracted fields
- many validation results
- many discrepancy records

Expected package keys may include:

- AWB number
- shipping date
- importer / ship-to name
- customer name

### Document

Represents an uploaded or discovered source file.

Document types:

- PO
- AWB
- HC
- Label
- spreadsheet / checklist
- interview note

### Label

Represents the final printed or customer-facing output to validate.

A package may have multiple labels because product lines, sizes, or templates may differ.

### Field Extraction Result

Represents a field extracted from a source document or label.

Expected attributes:

- field name
- raw value
- normalized value
- source document
- confidence
- extraction notes

### Validation Rule

Represents the rule used to compare a label field with one or more source fields.

Expected attributes:

- field
- authoritative source
- target label field
- match type
- tolerance
- exception logic
- customer-specific notes

### Validation Result

Represents the result of checking one field on one label.

Expected statuses:

- match
- mismatch
- missing
- warning
- informational
- needs human review

### Discrepancy

Represents a concrete mismatch or missing value that requires review.

Expected attributes:

- field
- label value
- expected value
- source document
- severity
- explanation
- reviewer action

### Manual Override / Golden Record

Represents a human-reviewed correction or accepted exception.

### Archive / Evidence Record

Represents stored screenshots, source files, reports, and validation evidence for later review.
