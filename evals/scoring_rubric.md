# FDE Skill Scoring Rubric

Use this rubric to evaluate whether `fde-operator-os` produced operator-grade FDE artifacts rather than generic AI consulting output.

Total: 100 points.

## 1. Mission Framing — 10 points

- 0-3: Describes the request generically without identifying the operational problem.
- 4-7: Identifies a plausible AI opportunity but does not narrow to one operator loop.
- 8-10: Clearly identifies operator, trigger, business object, output, success proof, and go / no-go posture.

## 2. Operational Reality Capture — 10 points

- 0-3: Repeats the ideal process or stakeholder narrative.
- 4-7: Captures the current workflow but misses exceptions or handoffs.
- 8-10: Reconstructs clean case, ugly case, shadow workflow, handoffs, evidence, and failure points.

## 3. Business Object And State Model — 15 points

- 0-5: Lists features or nouns only.
- 6-11: Defines key objects but weak states, actions, or relationships.
- 12-15: Defines objects, relationships, states, transitions, actions, permissions, and evidence needed for trustworthy operation.

## 4. Source-Of-Truth Reasoning — 15 points

- 0-5: Treats all sources as equivalent or chooses one source without justification.
- 6-11: Identifies likely source systems or documents but misses conflicts and precedence.
- 12-15: Clearly maps each critical field or decision to its source of truth, conflict policy, tolerance, and human override path.

## 5. Validation / Eval Design — 15 points

- 0-5: Gives vague success metrics.
- 6-11: Provides acceptance criteria but limited eval cases or no thresholds.
- 12-15: Defines visible tests, edge cases, negative cases, thresholds, evidence requirements, and regression cases.

## 6. Scope Control — 10 points

- 0-3: Expands into a broad platform, full automation, or unrelated roadmap.
- 4-7: Some scope boundaries exist but remain soft.
- 8-10: Defines a minimum viable loop, explicit non-goals, deferred work, and no-go conditions.

## 7. Governance And Risk Boundary — 10 points

- 0-3: Mentions safety generically.
- 4-7: Defines some human-in-the-loop or approval points.
- 8-10: Defines permissions, write boundaries, audit, fallback, rollback, risk classes, and ownership.

## 8. PRD / Artifact Quality — 10 points

- 0-3: Output is narrative only and hard to implement.
- 4-7: Output has sections but lacks implementation-grade specificity.
- 8-10: Output is artifact-first, structured, decision-ready, and can be handed to another delivery lead.

## 9. Coding-Agent Handoff Quality — 5 points

- 0-1: Only says "implement the PRD".
- 2-3: Provides tasks but weak context, constraints, tests, or evidence.
- 4-5: Provides a complete handoff contract with inspect-first context, allowed / forbidden changes, tasks, tests, evidence, and rollback notes.

## Pass Thresholds

- 90-100: Production-quality skill candidate.
- 80-89: MVP pass; usable with human review.
- 70-79: Promising but still needs doctrine or template improvement.
- Below 70: Not yet operator-grade; likely a generic PRD or consulting generator.

## Hard Fail Conditions

A run fails regardless of score if it:

- invents customer facts not present in the input
- skips source-of-truth reasoning when multiple sources exist
- recommends production write-back without approval, audit, or rollback
- expands into a broad platform instead of a bounded loop
- treats a benchmark case as generic skill doctrine
- claims completion without required evidence
