# Hallucination And Drift Checks

Use these checks when reviewing outputs from `fde-operator-os` or any leaf skill.

## Evidence Discipline

Flag the output if it:

- treats an inference as a fact
- invents systems, documents, fields, APIs, stakeholders, deadlines, or compliance rules
- fills unknowns with polished narrative instead of marking them as unknown
- ignores contradictions between provided materials
- cites a benchmark expected output as if it were customer input

## Scope Drift

Flag the output if it:

- expands a bounded loop into a full platform
- proposes production execution before pilot acceptance exists
- turns validation into generation without user confirmation
- turns advisory output into automated write-back without approval
- designs architecture before the operator loop is clear

## Source-Of-Truth Errors

Flag the output if it:

- treats one document, system, or stakeholder as the universal source of truth without justification
- does not define conflict handling between sources
- does not define tolerance, normalization, or human override for disputed fields
- ignores official or compliance sources when they are present

## FDE Reasoning Failures

Flag the output if it:

- has no named operator or accountable owner
- has no trigger
- has no business object
- has no output or evidence of completion
- has no clean case / ugly case distinction when the workflow is operational
- has no fallback path when AI is wrong or uncertain
- has no acceptance criteria

## Coding-Agent Handoff Failures

Flag the output if the handoff:

- only says "implement this PRD"
- does not specify files or modules to inspect first
- does not specify allowed and forbidden changes
- lacks tests or evidence requirements
- allows changes to production systems without review
- has no rollback or revert path

## Benchmark Contamination

Flag the output if it:

- hardcodes benchmark-specific terms into the generic skill
- uses benchmark expected files as hidden source material during a blind test
- optimizes for a single case at the expense of cross-industry portability
- moves private customer case material into root doctrine

## Review Output Format

When reporting hallucination or drift, use this format:

```text
Finding:
Severity: low / medium / high / hard fail
Evidence:
Why it matters:
Suggested fix:
```
