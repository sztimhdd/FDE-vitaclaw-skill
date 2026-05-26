# First-Run Minimal Loop

This example shows the **right way to try `fde-operator-os` for the first time**.

It is intentionally small.

The goal is not to model an entire account, product, or expansion roadmap.  
The goal is to prove that a first-time user can take one messy workflow and compress it into a credible operator loop.

## What This Example Demonstrates

- how to avoid starting with the whole project
- how to select one operator loop
- where to stop on the first run
- what a successful first pass should produce

## Scope Rule

For a first run, define:

- one operator
- one trigger
- one business object
- one output

Everything else stays out of scope unless it directly changes loop viability.

## Example Prompt

```text
Use $fde-operator-os.

Do not analyze the whole account.
Run one bounded loop only:

- Scenario: warehouse exception closure
- Operator: floor supervisor
- Trigger: exception alert arrives
- Business object: exception case
- Output: confirmed closure task with audit record

Produce:
- Mission Brief
- Operational Reality Map
- System Problem Frame
- State, Action & Evidence Model
- AI Intervention Design
- Minimum Viable Loop
- POC Acceptance Contract

Stop before Delivery Architecture unless the operational evidence is already strong.
```

## Recommended First-Run Output

1. `Mission Brief`
2. `Operational Reality Map`
3. `System Problem Frame`
4. `State, Action & Evidence Model`
5. `AI Intervention Design`
6. `Minimum Viable Loop`
7. `POC Acceptance Contract`

## What Not To Do

Do not start by asking for:

- full platform architecture
- account strategy
- pricing and packaging
- organization-wide expansion plan
- generic innovation brainstorm

Those may matter later, but they are not the right first proof.

## Success Standard

A successful first run should make another delivery lead say:

> "I understand who runs the loop, what triggers it, what AI does, what humans still own, and how we would judge the pilot."

If you cannot say that yet, keep narrowing the loop.
