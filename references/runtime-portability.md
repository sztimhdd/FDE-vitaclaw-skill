# Runtime Portability

This skill is designed to be portable across multiple agent hosts.

The core portable surface is:

- `SKILL.md`
- `README.md`
- `references/`
- `assets/templates/`
- `examples/`

These files define the doctrine, workflow, artifacts, and expected outputs independently of any one host runtime.

## Canonical Name

Use `fde-operator-os` as the canonical package / folder / repository name.

Recommended user-facing aliases:

- `fde`
- `applied`
- `Applied AI Operator OS`

## Host-Specific Notes

### Codex

- Native skill root example: `~/.codex/skills/fde-operator-os`
- Short alias can be provided as a separate wrapper skill such as `~/.codex/skills/fde`
- Typical invocation:
  - `$fde-operator-os`
  - `$fde`

### OpenClaw

Use the repository as a prompt-pack / skill-pack source.

Recommended approach:

1. Keep `SKILL.md` as the canonical workflow contract.
2. Import `references/` and `assets/templates/` as attached supporting files.
3. Register one or more user-facing names such as:
   - `fde-operator-os`
   - `fde`
   - `Applied AI Operator OS`

If the host supports slash aliases, map `/FDE` to the same canonical skill.

### Hermes

Use the repository as a reusable operator playbook.

Recommended approach:

1. Keep the seven-stage workflow and artifact list intact.
2. Treat `SKILL.md` as the system or skill prompt body.
3. Attach `references/` and `templates/` as supporting context.
4. Expose the invocation name as `FDE`, `fde`, or `Applied AI Operator OS`.

### Claude Code

Claude Code may not use the same skill packaging format, so portability should rely on content, not host-specific metadata.

Recommended approach:

1. Use `SKILL.md` as the core operating instruction.
2. Keep templates and references nearby in the repo.
3. Invoke in plain language, for example:
   - `Use Applied AI Operator OS to compress this workflow into a minimum viable loop.`
   - `Run the FDE operator workflow on this bounded loop.`

## Portability Rule

Do not make the workflow depend on:

- one host's slash-command system
- one host's skill manifest format
- one host's tool registry syntax

The host-specific layer should only affect:

- invocation name
- packaging location
- optional wrapper metadata

The doctrine, stages, and artifacts should remain host-neutral.
