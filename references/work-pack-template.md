# Bounded Work Pack Template

Use this template when delegating execution to a cheaper model or subagent.

```markdown
## Goal
One concrete, testable outcome.

## Why this tier
Why this work does not currently require frontier judgement.

## Scope
Files, directories, components, APIs, or surfaces the worker may touch.

## Constraints
Invariants, interfaces, behaviours, security boundaries, and things that must not change.

## Known context
Only the minimum facts the worker needs. Prefer durable source paths/artefacts over parent-chat history.

## Evidence required
Exact tests, commands, benchmarks, diffs, screenshots, or artefacts the worker must return.

## Stop / escalation conditions
Conditions that require the worker to stop and return evidence instead of guessing or widening scope.

## Return
- files changed
- commands run
- results
- assumptions introduced
- unresolved risks/failures
- scope deviations
- concise rationale
```

## Quality rules

- Keep one primary outcome per pack.
- Do not mix architecture decisions into an implementation pack unless already frozen.
- Do not grant repository-wide write scope when a smaller scope is enough.
- Require failure-path evidence for reliability-sensitive changes.
- Require performance evidence for performance claims.
- Require security review/escalation when trust boundaries change.
