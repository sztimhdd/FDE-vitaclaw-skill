---
name: coding-agent-handoff
description: Lightweight Applied AI skill for translating FDE artifacts into a downstream coding-agent implementation contract with scope, context, tests, evidence, and rollback boundaries.
---

# Coding Agent Handoff

Use this skill when the main question is:

- how should a downstream coding agent implement this framed loop
- what contract should be handed to Codex, Claude Code, OpenClaw, Hermes, or another build agent
- how do we prevent vibe-coding drift after FDE framing
- what must be inspected, changed, tested, and evidenced during implementation

## Scope

Stay focused on implementation handoff.

This skill does not replace Mission Qualification, Reality Capture, State/Action/Evidence modeling, or PRD writing. It assumes enough upstream FDE framing exists to define a safe implementation contract.

Primary output:

- `Coding Agent Handoff Contract`

## What To Define

- build goal
- business context and operator loop
- required behavior
- repo or system context to inspect first
- assumptions that must be confirmed before coding
- allowed changes
- forbidden changes
- implementation tasks
- acceptance criteria
- required tests
- required evidence
- rollback or revert plan
- human review requirements

## Do Not Expand Into

- generic architecture brainstorming
- autonomous production execution
- tool or runtime integration not required for the immediate build
- full roadmap planning
- customer discovery that should happen upstream

## Completion Standard

A reviewer should be able to say:

> A coding agent can start implementation from this contract without inventing product intent, changing forbidden surfaces, skipping tests, or claiming completion without evidence.

## Output Style

- contract first, explanation second
- explicit allowed versus forbidden changes
- explicit tests and evidence
- repo-grounded assumptions before implementation
- no vague instruction such as "make it better" without acceptance criteria

## Minimum Contract Sections

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

## Failure Signals

- The handoff only says "implement the PRD".
- The handoff does not state which files or modules to inspect first.
- The handoff has no explicit forbidden changes.
- The handoff has no tests or evidence requirements.
- The handoff lets a coding agent invent product scope.
- The handoff gives write authority without human review or rollback.
