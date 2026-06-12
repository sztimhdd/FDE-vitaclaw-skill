# Validation Matrix Builder

## Purpose

Build a field-level comparison matrix when source materials must be checked against a target output.

## Use When

- multiple documents or systems contain overlapping data
- one output must be checked against source materials
- tolerance, normalization, or fuzzy matching is needed
- source authority rules are not obvious

## Required Fields

For each comparison field, define:

- field name
- authoritative source
- target output
- comparison rule
- tolerance or normalization
- exception logic
- severity
- human review rule

## Comparison Rule Examples

- exact match
- normalized match
- fuzzy company match
- date parsing
- unit conversion
- containment
- informational only

## Failure Signals

- all fields use one source without justification
- no conflict policy
- no tolerance logic
- no human review rule
