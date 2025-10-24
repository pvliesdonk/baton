# CI Templates

This directory contains optional CI examples you can adopt.

## semantic-pr.yml
- Enforces conventional commit PR titles.
- **Required check name:** use the **job id** (default: `check`).
- Adds explicit permissions so the check can post statuses on fresh repos:

```yaml
permissions:
  contents: read
  pull-requests: read
  statuses: write
```

## pr-size-guard.yml
- Warns/fails PRs by **diff size** (changed lines).
- **Docs-only exemption** (`docs/**`, `*.md`).
- Thresholds: `WARN=400`, `HARD=800` (override via repo **Variables** `PR_SIZE_WARN` / `PR_SIZE_HARD`).
- Emits a summary table in the job output.

Tip: Keep branch protection minimal — one blocking check is usually enough.
