# Architecture Decisions

## ADR-001: Codex-first repository structure

Decision: Organize the repository for easy Codex reading and maintenance.

Implication: Use short, single-purpose files and stable top-level folders: `docs/`, `skill/`, `benchmarks/`, `eval/`, and `archive/`.

## ADR-002: Skill is not an application

Decision: The FDE skill package does not include UI, backend, OCR implementation, parser implementation, meeting recorder, or runtime integrations.

Implication: Build work belongs downstream and should be described through a coding-agent handoff contract.

## ADR-003: Benchmark cases stay outside generic skill doctrine

Decision: Export Label Helper is a benchmark, not a domain-specific specialization of the core skill.

Implication: Benchmark material stays under `benchmarks/export-label-helper/` and must not be copied into root skill behavior.

## ADR-004: Preserve benchmark reference folders

Decision: The Export Label Helper benchmark must preserve reference folders for original case materials, final PRD reference, and test inputs.

Implication: Keep `benchmarks/export-label-helper/source-materials/` as the canonical place for reference material and final PRD notes.

## ADR-005: Handoff contract is a first-class artifact

Decision: A PRD alone is not enough for vibe-coding-era implementation.

Implication: Any implementation-ready FDE output should include a coding-agent handoff contract with inspect-first context, allowed changes, forbidden changes, tests, evidence, and rollback.

## ADR-006: Legacy playbook content is archived, not deleted by default

Decision: Older operator-os examples, references, and host-specific wrappers should move to `archive/legacy-operator-os/` when no longer needed for active Codex work.

Implication: The active tree stays clean while older doctrine can still be recovered if needed.
