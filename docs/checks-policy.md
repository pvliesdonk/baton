# Checks Policy (Advisory → Blocking)

A pragmatic rule‑set for CI checks in downstream projects.

## Principles
- **Start advisory.** New checks begin as signal‑only comments/status.
- **Promote on evidence.** After ~5–10 green PRs with low flake, consider promotion.
- **Keep one required job.** Protect a single, stable job name (e.g., `blocking`).
- **Pin by SHA.** Avoid tag drift.

## Promotion checklist
- Is the false‑positive rate near zero?
- Does it run in < 5 minutes?
- Do maintainers know how to fix failures?
- Is there a rollback plan if it becomes noisy?

## Examples
- Secrets scan (gitleaks): advisory → blocking once stable.
- Semantic PR title: often advisory forever.
- Path filters: advisory helper for targeted tests, not blocking.

> Keep the toolkit repo minimal; enforce in downstreams via templates.
