# Context Sizing (Heuristics)

Tickets should fit in **one conversational run**. Use these rough caps as signals (not rules):

- **small** — single file or ≤300 LOC; trivial schema/docs updates.
- **medium** — 2–4 files or ≤800 LOC; light refactors; minor interface change with tests.
- **large** — multiple modules but still a single coherent slice; consider splitting.

**Split when**: the PR creeps beyond caps, cross‑module coupling grows, or Lane C design emerges.

> These heuristics align with the PR size guard template (5 files / 300 LOC advisory).
