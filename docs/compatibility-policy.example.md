# Compatibility Policy (Example)

Use this as a starting point in downstream projects.

## Principles
- **SemVer for public interfaces.** Breaking changes require a major bump.
- **Additive by default.** Prefer flags/opt‑ins to removals.
- **Graceful rollouts.** Use feature flags and deprecation windows.

## Breaking (examples)
- HTTP: remove/rename endpoint; change required field; change status codes semantics.
- CLI: change subcommand/flag name; change default behavior.
- Schema/Storage: drop column/table; change type with incompatible cast.
- AuthN/Z: tighten permissions without a migration path.

## Non‑breaking (examples)
- HTTP: add optional field; add new endpoint; broaden accepted inputs.
- CLI: add optional flag; add subcommand; improve help text.
- Schema: add nullable column; add index; widen varchar length.
- Docs: clarify behavior; fix typos.

## Process
- Flag risky changes in tickets (Auto Lane‑C triggers).
- For breaking changes: mini design, migration story, and rollout plan.
- Record the decision in `DECISIONS.md`.
