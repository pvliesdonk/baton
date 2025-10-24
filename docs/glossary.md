# Glossary (Ultra‑Minimal)

A compact legend agents and humans can rely on. Keep tickets short; link here rather than duplicating definitions.

## Lanes
- **A — routine**: Low risk, familiar change. Proposed Solution optional. Ship if CI green.
- **B — notify‑then‑go**: Moderate risk. Proposed Solution required; Architect acknowledges.
- **C — design‑required**: Higher risk/impact. Do a **mini design** and get Architect ack before building.

**Auto‑C triggers** (escalate when any apply):
_Software_ → public interface/API contract; data/schema/storage or migrations; security/authN/Z or cross‑boundary access; new runtime dependency/infrastructure; breaking change or major capability.
_Wiki/Story_ → canon/continuity change or retcon; timeline/outline/POV change; schema/metadata/ontology change; page/entry rename or move affecting links; new content type/template.

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
