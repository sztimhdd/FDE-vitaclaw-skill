# 00 Router

## Purpose

To evaluate the user's input and route the conversation to the most appropriate FDE skill module.

## Routing Logic

- **Qualifying the Opportunity:** Route to `01_mission_qualifier.md` if the fundamental mission, operator, or business object is undefined.
- **Capturing Workflow:** Route to `02_reality_capture.md` if capturing the true operational process (clean case, ugly case, exceptions).
- **Modeling the System:** Route to `03_object_modeler.md` to define business objects, states, actions, and evidence.
- **Validating Logic:** Route to `04_validation_matrix_builder.md` if multiple sources of truth need rule matching and discrepancy tolerance.
- **Writing Specs:** Route to `05_prd_writer.md` to compile the gathered context into an implementation-ready PRD.
- **Handoff to Engineering:** Route to `06_coding_agent_handoff.md` to produce a contract for a downstream coding agent.
