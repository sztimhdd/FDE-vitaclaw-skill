# Document Facts

This file summarizes facts from one representative shipment case. It is intentionally a fact summary, not an OCR implementation.

## Shipment Identifiers

- AWB number: 014-76712344
- Flight: AC892
- BIP / Border Control Point: ITFCO4
- Destination market: Italy / EU
- Importer / ship-to context: Eurofish Napoli

## Shipment Quantities

- Total boxes / cases: 120
- Net weight: 960 kg
- Gross weight: 1200 kg

## Product / Labeling Facts

- Product: live lobster / Homarus americanus
- Lot number example: F25-250705
- Product size examples include quarter and mixed-pack style labels.
- Piece-count style information may be required for EU shipment labels.

## Compliance / Source Facts

- Plant approval number example: 2391
- Health certificate is the official source for plant, BIP, species, and official weights.
- AWB is the source for AWB number, flight, routing, and logistics data.
- PO is the source for customer intent, product lines, packaging, label requirements, and lot-format expectations.
- Label is the physical output to validate.

## Normalization Examples

- 014-76712344, 014 76712344, and 01476712344 should be treated as the same AWB after normalization.
- Eurofish Napoli S.R.L. and Eurofish Napoli may require fuzzy company matching.
- July 05, 2025, Jul 05 2025, and 2025-07-05 may represent the same pack date.
- kg and lb may need conversion with tolerance.
