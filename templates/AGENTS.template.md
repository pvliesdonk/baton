# AGENTS (Project Template) — Baton v1.1.0

This file is intended for **downstream project repos**. It expands the binder with project‑specific details.

**Control plane:** GitHub Issues/Project board.

**Hats:** Planner, Architect, Developer (single profile).

**Lanes & SLAs:**

- A (routine): Proposed Solution optional; ship if CI green.
- B (notify‑then‑go): Proposed Solution required; Architect SLA same day.
- C (design‑required): Mini design + Architect ack; if delayed, run a short spike.

**Auto Lane‑C triggers:** public API, schema/storage, security/auth, cross‑boundary coupling, new runtime dependency, breaking change, major capability.

**Context classes (ticket sizing):** small / medium / large (see `docs/context-sizing.md`).

**AI profile (per ticket):** thinking | fast | cheap.

**Entry ritual:** see `templates/prompts/entry-ritual.md`.

**Golden paths:** feature flag / CLI command / REST endpoint.

**Stuck protocol:** see `docs/stuck.md` in the toolkit.

**Local policy (customize below):**

- Code style/tooling: _fill_
- Supported runtimes: _fill_
- Release cadence/compat: _fill_
- Observability minimums: _fill_
- Security posture (access control, credential handling): _fill_

> Keep this file short. Link out to deeper project docs as needed.
