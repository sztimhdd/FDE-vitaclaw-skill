# Coding Agent Handoff

This reference explains how `fde-operator-os` should hand framed FDE work to a downstream coding agent.

## Why This Exists

FDE output should not collapse into a vague vibe-coding request such as:

```text
Implement the PRD.
```

A downstream coding agent needs a contract that defines scope, context, allowed changes, forbidden changes, tests, evidence, and rollback.

## Relationship To Core Artifacts

The coding-agent handoff is not a replacement for:

- Mission Brief
- Operational Reality Map
- System Problem Frame
- State, Action & Evidence Model
- AI Intervention Design
- Minimum Viable Loop
- POC Acceptance Contract
- Eval Pack
- Governance And Risk Overlay

It is a translation layer from FDE artifacts into implementation instructions.

## When To Use

Use a handoff contract when:

- the operator loop is already framed
- the desired behavior is sufficiently specified
- implementation work is ready to begin
- a coding agent will modify files, tests, schemas, prompts, or configuration

Do not use it when:

- the problem is still unqualified
- the source of truth is unclear
- the workflow has not been reality-captured
- there is no acceptance test or review path

## Required Handoff Qualities

A strong handoff contract is:

- repo-grounded
- testable
- permission-aware
- scope-limited
- evidence-driven
- reversible

## Minimum Contract

Use `assets/templates/coding-agent-handoff-contract.md`.

At minimum, include:

1. Build Goal
2. Business Context
3. Required Behavior
4. Repo Context To Inspect First
5. Assumptions To Confirm Before Coding
6. Allowed Changes
7. Forbidden Changes
8. Implementation Tasks
9. Acceptance Criteria
10. Required Tests
11. Required Evidence
12. Rollback Plan
13. Human Review Notes

## Review Rule

A coding agent should not claim completion unless it can show:

- what changed
- which tests ran
- what evidence proves the behavior
- what assumptions remain
- how to revert safely
