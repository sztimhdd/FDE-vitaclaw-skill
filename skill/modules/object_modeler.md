# Object Modeler

## Purpose

Translate operational reality into business objects, relationships, states, actions, permissions, and evidence.

## Use When

- the workflow depends on documents, tickets, orders, cases, shipments, accounts, or other business objects
- state transitions matter
- trust depends on evidence
- humans and AI share responsibility

## Required Output

For each important object, define:

- object name
- owner
- key fields
- relationships
- states
- actions
- permissions
- evidence required for state change
- unresolved ambiguity

## Failure Signals

- nouns without state transitions
- actions without owners
- decisions without evidence
- automation without permission boundary
