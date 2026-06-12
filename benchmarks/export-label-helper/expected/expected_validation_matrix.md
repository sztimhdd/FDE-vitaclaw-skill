# Expected Validation Matrix

A strong output should convert the customer checklist and source documents into a structured validation matrix.

| Field | Expected Source Of Truth | Target | Match Logic | Notes |
|---|---|---|---|---|
| ship_to_name | PO / HC depending on rule | Label | fuzzy company match | Legal suffixes and punctuation may vary. |
| plant_number | HC | Label | exact or containment | Official approval number. |
| awb_number | AWB | Label | format normalization | Dashes, spaces, and compact form should normalize. |
| flight_number | AWB | Label | exact or partial | Example: AC892. |
| net_weight | PO / HC depending on rule | Label | unit conversion + tolerance | kg/lb conversion may be required. |
| gross_weight | AWB / HC depending on usage | Label or package record | numeric comparison | May be informational if not printed. |
| pack_date | PO / label requirement | Label | flexible date parsing | Date formats vary. |
| lot_number | PO / generated rule | Label | exact or configured pattern | Customer-specific format. |
| bip | HC / PO | Label | exact or containment | EU-specific. |
| number_of_cases | PO / HC | Label or package record | exact numeric | Shipment-level check. |
| destination | AWB | Label | informational / containment | Not all customer label templates include it. |
| packaging_type | PO | Label or package record | informational | May not be a blocking field. |
| size | PO | Label | configured mapping | Customer label wording may differ. |
| piece_count_per_case | PO / label requirement | Label | exact or configured | EU or customer-specific. |

## Required Reasoning

The skill should not say that all fields come from one source. It should map authority by field and explain conflicts.

## Required Tolerance Logic

- AWB normalization.
- Company fuzzy matching.
- Flexible date parsing.
- kg/lb conversion with tolerance.
- EU-specific fields.
- Customer-specific lot formatting.
