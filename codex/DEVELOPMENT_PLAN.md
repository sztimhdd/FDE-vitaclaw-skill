# VitaClaw FDE Skill Development Plan

## 1. Current Repository Assessment

### Current state

The repository is now organized as a compact Codex-first FDE skill lab. Its stated purpose is to turn messy customer discovery materials into implementation-ready artifacts that a downstream coding agent can safely execute. The root `README.md` already frames the repo as a skill/eval/handoff repository, not an application implementation repository.

Current top-level shape:

```text
.
├── AGENTS.md
├── README.md
├── SKILL.md
├── agent/
├── skills/
├── templates/
├── benchmarks/
├── evals/
└── codex/
```

Core repository intent is coherent:

- `README.md` defines the canonical workflow from messy materials to FDE artifacts to coding-agent handoff.
- `AGENTS.md` defines coding-agent boundaries and directory discipline.
- `SKILL.md` defines the root skill purpose, usage conditions, modules, outputs, and coding-agent handoff rule.
- `agent/` contains identity, soul, and operating principles.
- `skills/` contains the modular skill behavior from routing through coding-agent handoff.
- `templates/` contains the output artifact templates.
- `benchmarks/export-label-helper/` contains the first real UAT benchmark.
- `evals/` contains the rubric, runbook, and hallucination checks.
- `codex/` contains project instructions and prompt/task files.

### Strengths

1. **The repo is now small and agent-native.**  
   The structure is simple enough for Codex or another vibe-coding agent to inspect without wandering through legacy folders.

2. **The project boundary is explicit.**  
   The repo clearly says it is not a web app, OCR/PDF parser, backend/frontend implementation, meeting recorder, or TTS app.

3. **The generic skill and benchmark are separated.**  
   Export Label Helper is treated as a benchmark fixture rather than core doctrine.

4. **The coding-agent handoff concept is present.**  
   `skills/06_coding_agent_handoff.md` and `templates/coding_agent_handoff_contract.md` exist, which is essential for making the skill useful in vibe-coding workflows.

5. **Eval and hallucination checks are present.**  
   The repo already includes a 100-point rubric and hard-fail conditions.

### Gaps and issues found

1. **Broken legacy path in `skills/06_coding_agent_handoff.md`.**  
   It currently points to `skill/templates/coding_agent_handoff_contract.md`. The correct path should be `templates/coding_agent_handoff_contract.md`.

2. **Broken legacy paths in eval docs.**  
   `evals/run_manual_eval.md` references `eval/scoring_rubric.md`. The correct path is `evals/scoring_rubric.md`.

3. **Broken legacy paths in benchmark README.**  
   `benchmarks/export-label-helper/README.md` references `eval/scoring_rubric.md` and `eval/hallucination_checks.md`. These should be `evals/scoring_rubric.md` and `evals/hallucination_checks.md`.

4. **`AGENTS.md` is good but could be sharper.**  
   It is already usable, but some mission text could be shortened. Coding agents benefit from hard directives over narrative.

5. **`SKILL.md` is solid but routing can be more operational.**  
   It names the modules but does not yet define a strict stage-gate protocol for when to ask questions, when to stop, and when to produce artifacts.

6. **The router is too thin.**  
   `skills/00_router.md` has basic routing, but needs inputs, exit criteria, failure modes, and artifact outputs for each route.

7. **The handoff module is underdeveloped.**  
   It lists required contract sections, but needs explicit anti-vibe-drift rules: inspect-first files, forbidden changes, test evidence, rollback, and stop conditions.

8. **Templates are skeletal.**  
   They exist, but need required fields, placeholder examples, and completion criteria.

9. **Manual eval runbook is present but not yet executable enough.**  
   It describes modes but needs explicit smoke tests, input files, output paths, and no-leakage rules.

10. **No `codex/DEVELOPMENT_PLAN.md` existed before this file.**  
    This plan fills that gap.

## 2. Product Goal

This repository should become a reusable VitaClaw FDE Skill package that helps an agent transform messy customer materials, documents, field checklists, and interviews into operator-grade implementation artifacts. The goal is not merely to generate a PRD. The goal is to produce an agentic delivery contract pack that downstream coding agents can safely execute: mission brief, object model, source-of-truth reasoning, validation matrix, PRD, eval/UAT plan, and coding-agent handoff contract.

## 3. Non-Goals

This repository must not become:

- a web app
- an OCR/PDF parser
- a backend service
- a frontend UI
- an OpenClaw runtime integration
- an ASR/TTS system
- a meeting recorder
- a Meeting Copilot app
- a production browser automation tool
- a generic consulting chatbot
- an Export Label Helper-specific product repo

Export Label Helper is a benchmark. It must not contaminate the generic FDE skill doctrine.

## 4. Target Final Repository Shape

The current repository is already close to the desired minimal shape. The target final shape for the current phase is:

```text
vitaclaw-fde-onboarding-skill/
├── README.md
├── AGENTS.md
├── SKILL.md
│
├── agent/
│   ├── identity.md
│   ├── soul.md
│   └── operating_principles.md
│
├── skills/
│   ├── 00_router.md
│   ├── 01_mission_qualifier.md
│   ├── 02_reality_capture.md
│   ├── 03_object_modeler.md
│   ├── 04_validation_matrix_builder.md
│   ├── 05_prd_writer.md
│   └── 06_coding_agent_handoff.md
│
├── templates/
│   ├── mission_brief.md
│   ├── object_model.md
│   ├── validation_matrix.md
│   ├── prd.md
│   └── coding_agent_handoff_contract.md
│
├── benchmarks/
│   └── export-label-helper/
│       ├── README.md
│       ├── source-materials/
│       │   ├── manifest.md
│       │   ├── final-prd/
│       │   └── raw-files/
│       ├── input/
│       │   ├── customer_brief.md
│       │   ├── materials_manifest.md
│       │   ├── interview_notes.md
│       │   └── document_facts.md
│       ├── expected/
│       │   ├── expected_questions.md
│       │   ├── expected_object_model.md
│       │   ├── expected_validation_matrix.md
│       │   └── gold_prd_summary.md
│       └── results/
│           └── .gitkeep
│
├── evals/
│   ├── scoring_rubric.md
│   ├── run_manual_eval.md
│   └── hallucination_checks.md
│
└── codex/
    ├── PROJECT_BRIEF.md
    ├── TASKS.md
    ├── PROMPTS.md
    └── DEVELOPMENT_PLAN.md
```

### Required structural fixes

- Fix all `eval/` references to `evals/`.
- Fix all `skill/templates/` references to `templates/`.
- Decide whether `source-materials/` is part of the official benchmark structure. Current benchmark README says yes. That is acceptable because raw/source materials are benchmark fixtures, not generic skill doctrine.
- Keep `results/` as the only output location for benchmark run artifacts.

## 5. Skill File Quality Bar

### `AGENTS.md`

Current status: good, but slightly explanatory.

Required role: repository-level instruction contract for Codex and other coding agents.

Acceptance criteria:

- Clearly states read-first files.
- States hard boundaries.
- States directory discipline.
- States no expected-file leakage during blind eval.
- States coding-agent handoff requirements.
- Uses directive language.

Suggested changes:

- Shorten mission text.
- Add explicit instruction: do not read `expected/` or `source-materials/final-prd/` during blind runs.
- Add explicit instruction: benchmark outputs must go under `benchmarks/export-label-helper/results/`.

### `SKILL.md`

Current status: strong root definition.

Required role: root entry point for the FDE Skill.

Acceptance criteria:

- Defines when to use and when not to use the skill.
- Defines core modules and outputs.
- Defines stage gates.
- Requires question-asking when context is insufficient.
- Requires coding-agent handoff contract before implementation.

Suggested changes:

- Add `00_router.md` to the Core Modules list.
- Add a stage-gate sequence:
  1. qualify
  2. capture reality
  3. model objects
  4. build validation/source authority matrix
  5. write PRD
  6. generate coding-agent handoff
- Add a no-leakage rule for benchmark expected files.

### `agent/identity.md`

Current status: concise and good.

Required role: define the agent identity and voice.

Acceptance criteria:

- Names the role as VitaClaw FDE Onboarding Architect.
- Makes the agent evidence-driven and scope-controlled.
- Avoids sales or generic consulting language.

Suggested changes:

- Add one line saying the agent is responsible for implementation readiness, not code implementation.

### `agent/soul.md`

Current status: very concise and effective.

Required role: define behavioral DNA.

Acceptance criteria:

- Does not merely echo users.
- Narrows scope.
- Prioritizes business loop closure.
- Defaults safe.
- Does not hand ambiguous requirements to coding agents.

Suggested changes:

- Keep short.
- Add one line: “Separate evidence from inference.”

### `agent/operating_principles.md`

Current status: good.

Required role: define non-negotiable FDE principles.

Acceptance criteria:

- Loop before platform.
- Evidence before confidence.
- Source of truth before validation.
- Human boundary before automation.
- Acceptance before implementation.
- Benchmark outside doctrine.
- Handoff as contract.

Suggested changes:

- Add “Eval before claim of success.”

### `skills/00_router.md`

Current status: too thin.

Required role: route a user request or conversation state to the correct skill module.

Acceptance criteria:

- Defines input signals.
- Defines routing rules.
- Defines required output from each route.
- Defines stop conditions.
- Defines what to do when input is ambiguous.

Suggested changes:

- Expand each route with:
  - trigger condition
  - required inputs
  - output artifact
  - do-not-proceed condition

### `skills/01_mission_qualifier.md`

Current status: not fully inspected in this planning pass.

Required role: determine whether the opportunity is worth doing and narrow to one loop.

Acceptance criteria:

- Identifies operator, trigger, object, output, value, and failure cost.
- Rejects broad “AI platform” asks.
- Produces a go / maybe / no-go posture.

Suggested changes:

- Add explicit anti-AI-theater checks.
- Add required output: `mission_brief.md`.

### `skills/02_reality_capture.md`

Current status: not fully inspected in this planning pass.

Required role: capture how work actually happens.

Acceptance criteria:

- Captures clean case, ugly case, exceptions, handoffs, evidence, and failure points.
- Separates customer-provided facts from inference.
- Produces an operational reality map.

Suggested changes:

- Add discovery question patterns.
- Add missing-context reporting.

### `skills/03_object_modeler.md`

Current status: not fully inspected in this planning pass.

Required role: define business objects, states, actions, owners, permissions, and evidence.

Acceptance criteria:

- Defines the core object.
- Defines related documents/systems/actors.
- Defines state transitions.
- Defines evidence for each state/action.

Suggested changes:

- Add template-aligned output section.

### `skills/04_validation_matrix_builder.md`

Current status: not fully inspected in this planning pass.

Required role: map field/decision validation logic across multiple sources of truth.

Acceptance criteria:

- Defines source authority per field or decision.
- Defines match rule, tolerance, conflict policy, and review path.
- Handles optional fields and domain-specific exceptions.

Suggested changes:

- Add rule categories: exact, normalized exact, fuzzy, tolerance, informational, conditional.

### `skills/05_prd_writer.md`

Current status: not fully inspected in this planning pass.

Required role: compile prior artifacts into implementation-ready PRD.

Acceptance criteria:

- Does not invent missing context.
- Includes non-goals.
- Includes acceptance criteria.
- Includes eval/UAT plan.
- Clearly states unresolved assumptions.

Suggested changes:

- Add rule: do not write PRD from customer brief alone unless explicitly marked as provisional.

### `skills/06_coding_agent_handoff.md`

Current status: concept exists but contains a broken template path and needs more operational detail.

Required role: translate FDE artifacts into a downstream coding-agent contract.

Acceptance criteria:

- Uses `templates/coding_agent_handoff_contract.md`.
- Requires inspect-first files.
- Requires assumptions to confirm before coding.
- Requires allowed changes and forbidden changes.
- Requires implementation tasks.
- Requires acceptance criteria, checks, evidence, rollback, and human review notes.
- Prevents loose “build this” prompts.

Suggested changes:

- Fix template path.
- Add “do not start coding if these sections are missing.”
- Add evidence examples: test output, diff summary, screenshots if applicable, lint/typecheck results.

### `templates/mission_brief.md`

Current status: skeletal or not inspected in this planning pass.

Required role: standard Mission Brief artifact.

Acceptance criteria:

- Operator
- Trigger
- Business object
- Output
- Current pain
- Failure cost
- Success proof
- Go / maybe / no-go posture
- Unknowns

### `templates/object_model.md`

Current status: skeletal or not inspected in this planning pass.

Required role: standard object/state/action/evidence artifact.

Acceptance criteria:

- Core object
- Related objects
- States
- Actions
- Owners
- Permissions
- Evidence
- Open questions

### `templates/validation_matrix.md`

Current status: skeletal or not inspected in this planning pass.

Required role: standard field/source validation artifact.

Acceptance criteria:

- Field / decision
- Source of authority
- Target output
- Match rule
- Tolerance
- Exception
- Review path
- Evidence required

### `templates/prd.md`

Current status: skeletal or not inspected in this planning pass.

Required role: implementation-ready PRD template.

Acceptance criteria:

- Executive summary
- User/persona
- Operational loop
- Object model
- Requirements
- Non-goals
- Workflow
- Validation rules
- Data/artifact model
- UAT/eval plan
- Acceptance criteria
- Risks and unresolved assumptions

### `templates/coding_agent_handoff_contract.md`

Current status: good structure, but needs more detail.

Required role: bridge FDE artifacts to vibe-coding implementation.

Acceptance criteria:

- Build Goal
- Business Context
- Required Behavior
- Repo Context To Inspect First
- Assumptions To Confirm Before Coding
- Allowed Changes
- Disallowed Changes
- Implementation Tasks
- Acceptance Criteria
- Required Checks
- Required Evidence
- Rollback Plan
- Human Review Notes

Suggested changes:

- Add examples or bullet guidance under each heading.
- Add a hard stop note: if inspect-first files do not exist, stop and report.

### `evals/scoring_rubric.md`

Current status: good 100-point rubric.

Required role: scoring standard for benchmark and skill outputs.

Acceptance criteria:

- Scores mission framing, reality capture, object model, source authority, comparison/eval design, scope, governance, PRD quality, and coding-agent handoff.
- Has hard fails.
- Has pass thresholds.

Suggested changes:

- Consider raising Coding-Agent Handoff from 5 to 10 points, or explicitly define what “5/5” means.
- Add subcriteria for no expected-file leakage.

### `evals/hallucination_checks.md`

Current status: good.

Required role: hard-fail and warning checks.

Acceptance criteria:

- Flags invented facts.
- Flags hidden unknowns.
- Flags expected-file leakage.
- Flags broad platform expansion.
- Flags implementation handoff without checks/evidence.

Suggested changes:

- Add “uses final PRD/source-materials as if provided by customer during blind run.”

### `evals/run_manual_eval.md`

Current status: useful but too high-level and has broken path reference.

Required role: runnable manual eval protocol.

Acceptance criteria:

- Defines run_001 through run_004.
- Defines allowed inputs for each run.
- Defines forbidden files for blind runs.
- Defines output paths.
- Defines scoring steps.

Suggested changes:

- Fix `eval/` path to `evals/`.
- Add exact smoke test protocols from Section 9.

## 6. Development Workstreams

### Workstream A — Repository Hygiene

Goal: Make the repo internally consistent and easy for coding agents to navigate.

Tasks:

- Fix stale path references.
- Ensure README, AGENTS, SKILL, benchmark README, and eval docs all refer to the current directory structure.
- Make `AGENTS.md` shorter and more directive.
- Ensure benchmark results path exists.
- Ensure no old `skill/`, `eval/`, `docs/`, `references/`, `examples/`, `assets/`, or `archive/` references remain unless intentionally documented.

Deliverables:

- Clean repo references.
- Updated root docs.
- Clear benchmark/eval instructions.

### Workstream B — Core Skill Strengthening

Goal: Make the generic FDE Skill reliable and not export-label-specific.

Tasks:

- Strengthen `SKILL.md` as root entry point.
- Expand `skills/00_router.md` with route triggers, inputs, outputs, stop conditions, and ambiguity handling.
- Strengthen each skill module to output a specific artifact.
- Add explicit question-first behavior when context is insufficient.
- Add explicit no-go and scope-down behavior for broad automation requests.

Deliverables:

- Stronger root skill.
- Stronger router.
- Stage-gated modular skill behavior.

### Workstream C — Template Completion

Goal: Make templates usable by downstream agents and humans.

Tasks:

- Complete each template with required fields and placeholder guidance.
- Keep templates concise and artifact-first.
- Make the coding handoff template safe for vibe-coding agents.
- Align templates with skill module outputs.

Deliverables:

- Completed Mission Brief template.
- Completed Object Model template.
- Completed Validation Matrix template.
- Completed PRD template.
- Completed Coding Agent Handoff Contract template.

### Workstream D — Export Label Helper Benchmark

Goal: Create the first real UAT benchmark for the FDE Skill.

Tasks:

- Ensure `input/customer_brief.md` simulates the vague first customer request.
- Ensure `input/materials_manifest.md` lists all materials.
- Ensure `input/document_facts.md` contains distilled facts rather than requiring OCR.
- Ensure `input/interview_notes.md` captures realistic discovery constraints.
- Ensure `expected/` contains gold references.
- Ensure `source-materials/final-prd/` is treated as holdout material during blind runs.
- Ensure `results/` is the only output location for benchmark artifacts.

Deliverables:

- Complete benchmark input set.
- Complete expected output set.
- Clear holdout rule.

### Workstream E — Eval Harness and Manual UAT

Goal: Make the skill testable without expensive or fragile automation.

Tasks:

- Define run_001 through run_004.
- Define output files for each run.
- Define score process.
- Define no-leakage rules.
- Define hallucination checks.
- Define pass/fail thresholds.

Deliverables:

- Updated `evals/run_manual_eval.md`.
- Updated `evals/scoring_rubric.md` if needed.
- Updated `evals/hallucination_checks.md` if needed.

### Workstream F — Coding Agent Handoff Contract

Goal: Convert FDE output into a contract that a downstream vibe-coding agent can safely execute.

Tasks:

- Fix template path in `skills/06_coding_agent_handoff.md`.
- Define required handoff sections.
- Require inspect-first files.
- Require allowed and forbidden changes.
- Require implementation tasks, tests, evidence, rollback, and human review notes.
- Add failure signals.

Deliverables:

- Updated `skills/06_coding_agent_handoff.md`.
- Updated `templates/coding_agent_handoff_contract.md`.

## 7. Task Breakdown

### Task 01 — Fix stale path references

Files to read first:

- `README.md`
- `AGENTS.md`
- `SKILL.md`
- `skills/06_coding_agent_handoff.md`
- `benchmarks/export-label-helper/README.md`
- `evals/run_manual_eval.md`

Files to edit:

- `skills/06_coding_agent_handoff.md`
- `benchmarks/export-label-helper/README.md`
- `evals/run_manual_eval.md`
- any other file with stale paths found by search

Expected output:

- All `skill/templates/` references corrected to `templates/`.
- All `eval/` references corrected to `evals/`.

Acceptance criteria:

- Repo search for `skill/templates` returns no results.
- Repo search for `eval/` returns no unintended old-path references.
- All benchmark docs point to `evals/`.

Complexity: S

Dependencies: none

Automation safety: Safe

### Task 02 — Tighten `AGENTS.md`

Files to read first:

- `AGENTS.md`
- `README.md`
- `SKILL.md`

Files to edit:

- `AGENTS.md`

Expected output:

- Shorter, more directive repository instruction file.

Acceptance criteria:

- Includes read-first list.
- Includes hard boundaries.
- Includes no expected-file leakage rule.
- Includes output path discipline.
- Does not become a long product overview.

Complexity: S

Dependencies: Task 01 optional

Automation safety: Safe

### Task 03 — Strengthen `SKILL.md` stage gates

Files to read first:

- `SKILL.md`
- `skills/00_router.md`
- all files under `skills/`

Files to edit:

- `SKILL.md`

Expected output:

- Root skill file defines a stage-gated FDE flow.

Acceptance criteria:

- Includes router as core module.
- Defines stage order.
- Defines when to ask questions.
- Defines when not to proceed to PRD or coding handoff.
- Keeps benchmark cases out of generic doctrine.

Complexity: M

Dependencies: Task 01

Automation safety: Safe

### Task 04 — Expand router behavior

Files to read first:

- `skills/00_router.md`
- `SKILL.md`
- all files under `skills/`

Files to edit:

- `skills/00_router.md`

Expected output:

- Router includes trigger conditions, required inputs, outputs, and stop conditions for each module.

Acceptance criteria:

- Ambiguous input routes to question generation, not PRD writing.
- Implementation requests route to handoff contract only after PRD/eval criteria exist.
- Validation/source-of-truth cases route to validation matrix builder.

Complexity: M

Dependencies: Task 03

Automation safety: Safe

### Task 05 — Strengthen mission qualifier

Files to read first:

- `skills/01_mission_qualifier.md`
- `templates/mission_brief.md`
- `agent/operating_principles.md`

Files to edit:

- `skills/01_mission_qualifier.md`
- optionally `templates/mission_brief.md`

Expected output:

- Clear mission qualification behavior and mission brief output.

Acceptance criteria:

- Identifies operator, trigger, object, output, evidence, value, and failure cost.
- Includes go/maybe/no-go posture.
- Pushes back on AI theater.

Complexity: M

Dependencies: Task 03

Automation safety: Safe

### Task 06 — Strengthen reality capture

Files to read first:

- `skills/02_reality_capture.md`
- `agent/operating_principles.md`

Files to edit:

- `skills/02_reality_capture.md`

Expected output:

- Clear discovery behavior for clean case, ugly case, exceptions, evidence, and failure modes.

Acceptance criteria:

- Separates evidence from inference.
- Produces missing-context questions.
- Avoids idealized process maps.

Complexity: M

Dependencies: Task 03

Automation safety: Safe

### Task 07 — Strengthen object modeler

Files to read first:

- `skills/03_object_modeler.md`
- `templates/object_model.md`

Files to edit:

- `skills/03_object_modeler.md`
- optionally `templates/object_model.md`

Expected output:

- Strong object/state/action/evidence modeling behavior.

Acceptance criteria:

- Defines core object and related objects.
- Defines states and transitions.
- Defines actions, owners, permissions, and evidence.

Complexity: M

Dependencies: Task 03

Automation safety: Safe

### Task 08 — Strengthen validation matrix builder

Files to read first:

- `skills/04_validation_matrix_builder.md`
- `templates/validation_matrix.md`
- `benchmarks/export-label-helper/input/document_facts.md`

Files to edit:

- `skills/04_validation_matrix_builder.md`
- optionally `templates/validation_matrix.md`

Expected output:

- Clear source-authority and comparison matrix behavior.

Acceptance criteria:

- Supports exact, normalized, fuzzy, tolerance, informational, and conditional rules.
- Requires source authority per field.
- Requires conflict policy and review path.
- Does not hardcode Export Label facts into generic skill.

Complexity: M

Dependencies: Task 03

Automation safety: Safe

### Task 09 — Strengthen PRD writer

Files to read first:

- `skills/05_prd_writer.md`
- `templates/prd.md`
- `evals/scoring_rubric.md`

Files to edit:

- `skills/05_prd_writer.md`
- optionally `templates/prd.md`

Expected output:

- PRD writer produces implementation-ready artifacts from prior FDE outputs.

Acceptance criteria:

- Does not write full PRD from insufficient context without marking it provisional.
- Includes object model, workflow, validation logic, non-goals, UAT/eval plan, acceptance criteria, risks, and unknowns.

Complexity: M

Dependencies: Tasks 05-08

Automation safety: Safe

### Task 10 — Fix and strengthen coding-agent handoff module

Files to read first:

- `skills/06_coding_agent_handoff.md`
- `templates/coding_agent_handoff_contract.md`
- `AGENTS.md`

Files to edit:

- `skills/06_coding_agent_handoff.md`
- `templates/coding_agent_handoff_contract.md`

Expected output:

- A robust handoff module and template that prevent loose vibe-coding prompts.

Acceptance criteria:

- Correct template path.
- Requires inspect-first files.
- Requires allowed/forbidden changes.
- Requires tests, evidence, rollback, and human review notes.
- Includes stop conditions.

Complexity: M

Dependencies: Task 01

Automation safety: Safe

### Task 11 — Complete artifact templates

Files to read first:

- all files under `templates/`
- relevant skill modules

Files to edit:

- all files under `templates/`

Expected output:

- Templates contain enough structure for consistent artifact generation.

Acceptance criteria:

- Each template has required fields.
- Each template is concise.
- Templates align with skill module outputs.
- Templates mark unknowns explicitly.

Complexity: M

Dependencies: Tasks 05-10

Automation safety: Safe

### Task 12 — Update benchmark README and input discipline

Files to read first:

- `benchmarks/export-label-helper/README.md`
- files under `benchmarks/export-label-helper/input/`
- files under `benchmarks/export-label-helper/expected/`

Files to edit:

- `benchmarks/export-label-helper/README.md`
- optionally benchmark input docs if gaps are found

Expected output:

- Benchmark usage is clear and protects holdout expected files.

Acceptance criteria:

- Defines what input files are for.
- Defines what expected files are for.
- Defines source-materials/final-prd as holdout during blind runs.
- Defines results path.
- Uses correct `evals/` path.

Complexity: S

Dependencies: Task 01

Automation safety: Safe

### Task 13 — Make manual eval runbook executable

Files to read first:

- `evals/run_manual_eval.md`
- `evals/scoring_rubric.md`
- `evals/hallucination_checks.md`
- `benchmarks/export-label-helper/README.md`

Files to edit:

- `evals/run_manual_eval.md`

Expected output:

- Runbook defines run_001 through run_004 with exact inputs, outputs, and forbidden files.

Acceptance criteria:

- Includes discovery-only run.
- Includes document-facts run.
- Includes interview-notes run.
- Includes PRD + coding-handoff run.
- Defines scoring procedure.

Complexity: M

Dependencies: Task 12

Automation safety: Safe

### Task 14 — Refine scoring rubric

Files to read first:

- `evals/scoring_rubric.md`
- `evals/hallucination_checks.md`
- `templates/coding_agent_handoff_contract.md`

Files to edit:

- `evals/scoring_rubric.md`

Expected output:

- Rubric can score all required outputs consistently.

Acceptance criteria:

- Coding-Agent Handoff category has clear subcriteria.
- No-leakage behavior is captured.
- Hard fail rules remain clear.
- Total remains 100 points.

Complexity: S

Dependencies: Task 13 optional

Automation safety: Safe

### Task 15 — Refine hallucination checks

Files to read first:

- `evals/hallucination_checks.md`
- `benchmarks/export-label-helper/README.md`

Files to edit:

- `evals/hallucination_checks.md`

Expected output:

- Stronger hallucination and leakage checks.

Acceptance criteria:

- Flags use of expected/final PRD as if it were user-provided input.
- Flags invented customer facts.
- Flags hiding unknowns.
- Flags broad platform expansion.
- Flags handoff without evidence.

Complexity: S

Dependencies: Task 12

Automation safety: Safe

### Task 16 — Prepare benchmark smoke test directories

Files to read first:

- `benchmarks/export-label-helper/README.md`
- `evals/run_manual_eval.md`

Files to edit:

- add `.gitkeep` files or README stubs under planned result directories only if needed

Expected output:

- Results directory ready for run_001 through run_004 outputs.

Acceptance criteria:

- `benchmarks/export-label-helper/results/` exists.
- No test outputs are pre-filled as if already run.
- No expected files are copied into results.

Complexity: S

Dependencies: Task 13

Automation safety: Safe

## 8. First Three Implementation Batches

### Batch 1 — Repo and Documentation Stabilization

Objective:

Make the current repo internally consistent and ready for deeper skill/template work.

Included tasks:

- Task 01 — Fix stale path references
- Task 02 — Tighten `AGENTS.md`
- Task 03 — Strengthen `SKILL.md` stage gates
- Task 12 — Update benchmark README and input discipline
- Task 13 — Make manual eval runbook executable

Expected git diff profile:

- Markdown-only changes.
- No new implementation code.
- No new top-level folders.
- No benchmark expected data moved into input.

Manual review checklist:

- Search confirms no stale `skill/templates/` path.
- Search confirms no accidental `eval/` path remains.
- `AGENTS.md` is short and directive.
- `SKILL.md` clearly stage-gates the FDE process.
- Benchmark README defines holdout rules.
- Manual eval runbook includes run_001 through run_004.

Stop condition:

Stop after Batch 1 changes are complete and summarized. Do not begin skill/template rewrites in the same coding session.

### Batch 2 — Skill and Template Quality

Objective:

Improve the reusable FDE logic and artifact templates.

Included tasks:

- Task 04 — Expand router behavior
- Task 05 — Strengthen mission qualifier
- Task 06 — Strengthen reality capture
- Task 07 — Strengthen object modeler
- Task 08 — Strengthen validation matrix builder
- Task 09 — Strengthen PRD writer
- Task 10 — Fix and strengthen coding-agent handoff module
- Task 11 — Complete artifact templates

Expected git diff profile:

- Markdown-only changes under `skills/` and `templates/`.
- No benchmark-specific facts added to generic skill files.
- No implementation code.

Manual review checklist:

- Each skill module has clear inputs, outputs, and stop conditions.
- Templates are structured but not bloated.
- Handoff contract blocks loose vibe-coding.
- No Export Label-specific data appears in generic skill doctrine.

Stop condition:

Stop after skill and template changes. Do not run benchmark outputs in the same session unless explicitly requested.

### Batch 3 — Benchmark and Eval Readiness

Objective:

Make Export Label Helper UAT runnable and scoreable.

Included tasks:

- Task 14 — Refine scoring rubric
- Task 15 — Refine hallucination checks
- Task 16 — Prepare benchmark smoke test directories
- Run manual smoke tests only if explicitly asked

Expected git diff profile:

- Markdown-only changes under `evals/` and `benchmarks/export-label-helper/`.
- Results directories may be created but should not contain fake results.

Manual review checklist:

- Rubric totals 100 points.
- Handoff quality is scoreable.
- Expected-file leakage is a hard fail.
- Smoke tests define exact inputs/outputs.

Stop condition:

Stop before generating actual benchmark results unless explicitly asked.

## 9. Smoke Test Design

### Run 001 — Discovery Only

Input:

- `benchmarks/export-label-helper/input/customer_brief.md`

Forbidden during run:

- `benchmarks/export-label-helper/expected/`
- `benchmarks/export-label-helper/source-materials/final-prd/`
- prior `results/` from the same benchmark

Expected behavior:

- Ask discovery questions.
- Identify missing context.
- Produce initial mission frame.
- Do not write PRD.
- Do not generate implementation tasks.
- Do not hallucinate document facts.

Output:

- `benchmarks/export-label-helper/results/run_001/discovery_questions.md`
- `benchmarks/export-label-helper/results/run_001/missing_context.md`
- `benchmarks/export-label-helper/results/run_001/initial_mission_frame.md`
- `benchmarks/export-label-helper/results/run_001/self_check.md`

### Run 002 — Document Facts Added

Input:

- `benchmarks/export-label-helper/input/customer_brief.md`
- `benchmarks/export-label-helper/input/materials_manifest.md`
- `benchmarks/export-label-helper/input/document_facts.md`

Forbidden during run:

- `benchmarks/export-label-helper/expected/`
- `benchmarks/export-label-helper/source-materials/final-prd/`

Expected behavior:

- Identify core business objects.
- Identify PO/AWB/HC/Label source-of-truth roles.
- Propose initial validation fields.
- Mark unresolved assumptions.
- Do not read expected files.

Output:

- `benchmarks/export-label-helper/results/run_002/object_model_draft.md`
- `benchmarks/export-label-helper/results/run_002/source_authority_draft.md`
- `benchmarks/export-label-helper/results/run_002/initial_validation_fields.md`
- `benchmarks/export-label-helper/results/run_002/self_check.md`

### Run 003 — Interview Notes Added

Input:

- `benchmarks/export-label-helper/input/customer_brief.md`
- `benchmarks/export-label-helper/input/materials_manifest.md`
- `benchmarks/export-label-helper/input/document_facts.md`
- `benchmarks/export-label-helper/input/interview_notes.md`

Forbidden during run:

- `benchmarks/export-label-helper/expected/`
- `benchmarks/export-label-helper/source-materials/final-prd/`

Expected behavior:

- Update scope.
- Build validation matrix.
- Identify edge cases.
- Identify non-goals.
- Identify human review boundaries.

Output:

- `benchmarks/export-label-helper/results/run_003/validation_matrix.md`
- `benchmarks/export-label-helper/results/run_003/scope_and_non_goals.md`
- `benchmarks/export-label-helper/results/run_003/edge_cases.md`
- `benchmarks/export-label-helper/results/run_003/self_check.md`

### Run 004 — PRD + Coding Handoff

Input:

- all files under `benchmarks/export-label-helper/input/`
- relevant generic skill files and templates

Forbidden during run:

- `benchmarks/export-label-helper/expected/`
- `benchmarks/export-label-helper/source-materials/final-prd/`

Expected behavior:

- Generate PRD.
- Generate coding-agent handoff contract.
- Generate self-check.
- State unresolved assumptions.
- Do not claim implementation success.

Output:

- `benchmarks/export-label-helper/results/run_004/prd.md`
- `benchmarks/export-label-helper/results/run_004/coding_agent_handoff_contract.md`
- `benchmarks/export-label-helper/results/run_004/unresolved_assumptions.md`
- `benchmarks/export-label-helper/results/run_004/self_check.md`

## 10. Quality Gates

Hard quality gates:

1. Generic skill does not hardcode Export Label Helper.
2. Benchmark remains separate from generic skill doctrine.
3. No web UI, OCR/PDF parser, backend service, frontend app, OpenClaw integration, ASR/TTS, or Meeting Copilot is added.
4. No expected-file leakage into blind runs.
5. The skill asks questions when context is insufficient.
6. PRD includes object model, validation/source authority logic, workflow, non-goals, UAT/eval plan, and acceptance criteria.
7. Coding handoff includes inspect-first files, allowed changes, forbidden changes, implementation tasks, tests/checks, evidence, rollback, and human review notes.
8. Evaluation rubric can score outputs consistently.
9. Hallucination checks catch invented facts and unsupported implementation readiness.
10. All generated benchmark outputs are written only under `benchmarks/export-label-helper/results/`.

## 11. Recommended First Implementation Prompt

Use this prompt for the next coding session. It intentionally implements Batch 1 only.

```text
You are working in `sztimhdd/FDE-vitaclaw-skill`.

Implement Batch 1 from `codex/DEVELOPMENT_PLAN.md` only.

Read first:
- `AGENTS.md`
- `README.md`
- `SKILL.md`
- `codex/DEVELOPMENT_PLAN.md`
- `benchmarks/export-label-helper/README.md`
- `evals/run_manual_eval.md`
- `evals/scoring_rubric.md`
- `evals/hallucination_checks.md`
- `skills/06_coding_agent_handoff.md`

Allowed files to edit:
- `AGENTS.md`
- `SKILL.md`
- `skills/06_coding_agent_handoff.md`
- `benchmarks/export-label-helper/README.md`
- `evals/run_manual_eval.md`
- any file containing stale path references to `skill/templates/` or `eval/`

Forbidden actions:
- Do not build a web UI.
- Do not implement OCR/PDF parsing.
- Do not add backend/frontend code.
- Do not add OpenClaw integration.
- Do not add ASR/TTS or Meeting Copilot features.
- Do not modify benchmark expected files.
- Do not generate benchmark results.
- Do not read expected files as if they were input to the skill.
- Do not start Batch 2 or Batch 3.

Exact deliverables:
1. Fix stale path references.
2. Tighten `AGENTS.md` into concise coding-agent instructions.
3. Add stage-gate flow to `SKILL.md`.
4. Fix benchmark README eval paths and holdout rules.
5. Expand `evals/run_manual_eval.md` with run_001 through run_004 protocols.
6. Summarize changed files and remaining risks.

Stop condition:
Stop after Batch 1. Do not continue into skill-module or template rewrites unless explicitly asked.
```

## 12. Final Output Requirements For This Planning Session

This planning session created `codex/DEVELOPMENT_PLAN.md` only.

Files inspected during planning:

- `README.md`
- `AGENTS.md`
- `SKILL.md`
- `codex/PROJECT_BRIEF.md`
- `codex/TASKS.md`
- `codex/PROMPTS.md`
- `evals/scoring_rubric.md`
- `evals/run_manual_eval.md`
- `evals/hallucination_checks.md`
- `skills/00_router.md`
- `skills/06_coding_agent_handoff.md`
- `templates/coding_agent_handoff_contract.md`
- `agent/identity.md`
- `agent/soul.md`
- `agent/operating_principles.md`
- `benchmarks/export-label-helper/README.md`
- `benchmarks/export-label-helper/input/customer_brief.md`
- `benchmarks/export-label-helper/input/document_facts.md`

Top 5 risks found:

1. Stale path references remain after restructuring.
2. Router and handoff module are present but under-specified.
3. Templates may be too skeletal for reliable artifact generation.
4. Manual eval runbook is not yet executable enough.
5. Benchmark holdout boundaries need to be reinforced to prevent expected-file leakage.

Recommended next batch:

- Batch 1 — Repo and Documentation Stabilization.

Repository readiness:

- Ready for Batch 1 implementation.
- Not yet ready for full benchmark execution.
- Not yet ready to claim FDE Skill MVP pass.
