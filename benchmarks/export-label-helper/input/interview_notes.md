# Interview Notes

These notes simulate follow-up discovery conversations.

## Scope Clarifications

- The first version validates labels; it does not generate labels.
- The system should show discrepancies and evidence, not silently block business workflow.
- Human staff remain responsible for final acceptance.
- The system should support incomplete packages because PO, AWB, HC, and labels may arrive at different times.
- Multiple labels may belong to one shipment package.

## Field And Rule Clarifications

- Some fields appear in multiple documents but do not have the same authority.
- PO often represents customer intent and label requirements.
- AWB represents logistics truth such as AWB number, flight, route, and gross weight.
- HC represents official compliance truth such as plant number, BIP, certificate data, species, and official weights.
- Label is the printed output to be checked.
- EU shipments require BIP and piece-count style checks when applicable.
- Lot number can be customer-specific and may need configurable formatting.
- Destination may appear on some customer label templates but not all.
- Weight comparison may require kg/lb conversion and tolerance.
- Company names may need fuzzy matching because legal suffixes and punctuation vary.
- AWB numbers may appear with spaces, dashes, or compact formatting.

## Product Boundary

- No carrier system integration in MVP.
- No external filing integration in MVP.
- No automatic production write-back in MVP.
- No final label generation in MVP.
