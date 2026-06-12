# Export Label Helper Source Materials Manifest

This folder preserves the benchmark reference materials for Codex.

## Reference Material Set

Keep these materials together:

1. AWB reference document
   - expected filename pattern: `EUROFISH_AWB_014_76712344.pdf`
   - role: logistics source

2. Health Certificate reference document
   - expected filename pattern: `EUROFISH_HC_014_76712344.pdf`
   - role: official compliance source

3. Purchase Order reference document
   - expected filename pattern: `EUROFISH_PO_014_76712344.pdf`
   - role: customer intent and labeling requirements

4. Label reference image
   - expected filename pattern: `EUROFISH_LABEL_014_76712344.jpg`
   - role: final printed output to compare

5. Cross-check spreadsheet
   - expected filename pattern: `labels_cross_check_list.xlsx`
   - role: customer-maintained field checklist and rule seed

6. Final target product document
   - expected location: `source-materials/final-prd/PRD.md`
   - role: gold reference for expected delivery quality

## Benchmark Rule

Codex may read these files when constructing or debugging the benchmark pack.

During evaluation, do not expose the final product document or expected outputs to the tested skill before the run is complete.

## Lightweight Text Facts

The distilled facts used for lightweight benchmark runs live in:

- `../input/document_facts.md`
- `../input/interview_notes.md`
- `../expected/gold_prd_summary.md`
