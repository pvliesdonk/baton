# Glossary (Ultra‑Minimal)

A compact legend agents and humans can rely on. Keep tickets short; link here rather than duplicating definitions.

## Lanes
- **A — routine**: Low risk, familiar change. Proposed Solution optional. Ship if CI green.
- **B — notify‑then‑go**: Moderate risk. Proposed Solution required; Architect acknowledges.
- **C — design‑required**: Higher risk/impact. Do a **mini design** and get Architect ack before building.

**Auto‑C triggers** (escalate to Lane C when any apply):
- Public interface or API contract changes.
- Data/schema/storage changes or migrations.
- Security/authN/Z or cross‑boundary access.
- New runtime dependency or infrastructure surface.
- Breaking change or major capability/behavior shift.

## Context sizes (ticket sizing)
- **small**: fits one focused conversational run; trivial rollback.
- **medium**: 1–2 runs; may need a flag/guardrail.
- **large**: split into smaller issues; avoid starting until scoped.

## AI profiles
- **thinking**: highest reasoning quality; slower/costlier.
- **fast**: latency‑biased; still competent.
- **cheap**: cost‑biased; acceptable for rote tasks.

> Board = control plane. For Lane C, do the mini design; if blocked, run a short spike.
