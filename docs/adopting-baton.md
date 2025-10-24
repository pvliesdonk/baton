# Adopting Baton (Quickstart)

> Board is the control plane: keep status on Issues/Project, not in docs.

## Setup (org/repo)
1. Create labels & project fields (Lane A/B/C; Context small/medium/large; AI profile thinking/fast/cheap).
2. Copy templates from `templates/` into your repo (AGENTS, issue forms, PR template, CI).
3. Enable minimal branch protection on `main` with **one blocking check**.

### Required status check: name it by **job id**
When enabling branch protection for the Semantic PR workflow, set the required check to the **job id** from the workflow, not the workflow name. In Baton’s template the job id is:

```
check
```

If you rename the job (e.g. `semantic-title`), require that exact name instead.

### Workflow permissions (fresh repos)
New repositories default GitHub Actions to *Read* permissions. To let the Semantic PR workflow create its status, Baton’s template declares:

```yaml
permissions:
  contents: read
  pull-requests: read
  statuses: write
```

Alternatively, in **Settings → Actions → General**, set **Workflow permissions** to **Read and write**.

## Day-to-day
- Size tickets by context; split when they grow.
- Default to **Lane B (notify‑then‑go)**; escalate to C on design-required work.
- Follow the Stuck Protocol (`docs/stuck.md`).
- Prefer golden paths and keep the board canonical.
