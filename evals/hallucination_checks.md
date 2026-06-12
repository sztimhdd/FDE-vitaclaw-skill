# Hallucination Checks

Flag the output if it:

- treats inference as fact
- invents systems, fields, stakeholders, rules, deadlines, or source documents
- hides unknowns behind polished wording
- ignores contradictions between materials
- uses expected benchmark answers as if they were user input
- turns a benchmark case into generic skill doctrine
- expands a bounded loop into a full platform
- recommends production write-back without human review and rollback
- hands work to a coding agent without checks and evidence

## Report Format

```text
Finding:
Severity: low / medium / high / hard fail
Evidence:
Why it matters:
Suggested fix:
```
