# Glossary (Ultra‑Minimal)

A compact legend agents and humans can rely on. Keep tickets short; link here rather than duplicating definitions.

## Lanes

- **A — routine**: Low risk, familiar change. Proposed Solution optional. Ship if CI green.
- **B — notify‑then‑go**: Moderate risk. Proposed Solution required; Architect acknowledges.
- **C — design‑required**: Higher risk/impact. Do a **mini design** and get Architect ack before building.

**Auto‑C triggers** (escalate when any apply):

**Software:**

- Public interface or API contract changes.
- Data/schema/storage changes or migrations.
- Security/authN/Z or cross-boundary access.
- New runtime dependency or infrastructure surface.
- Breaking change or major capability/behavior shift.

**Wiki/Story:**

- Canon/continuity change or retcon.
- Timeline/outline/POV change.
- Schema/metadata/ontology change.
- Page/entry rename or move affecting links.
- New content type or template.

## Context sizes (ticket sizing)

- **small**: fits one focused conversational run; trivial rollback.
- **medium**: 1–2 runs; may need a flag/guardrail.
- **large**: split into smaller issues; avoid starting until scoped.

## Roles (aliases)

- **Planner** (aka **Curator**) — scoping topics, sources, DoD.
- **Architect** (aka **Loremaster**) — continuity/structure and design decisions.
- **Developer** (aka **Scribe**) — implements edits/entries/scenes.

## Canon status (wiki/story)

- **Draft** — work in progress.
- **Canon** — accepted into continuity.
- **Apocrypha** — deliberately outside or experimental.

## AI profiles

- **thinking**: highest reasoning quality; slower/costlier.
- **fast**: latency‑biased; still competent.
- **cheap**: cost‑biased; acceptable for rote tasks.

> Board = control plane. For Lane C, do the mini design; if blocked, run a short spike.
