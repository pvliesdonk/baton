# Decisions

Short ADR‑lite entries. One decision per section. Link to the deciding Issue/PR. Do not delete reversed decisions; add a new one and mark the old as superseded.

---

## [0001] Doc‑set change policy (template)
- **Context:** when architecture grows beyond a page or two.
- **Decision:** Architect may propose a doc‑set change via a single issue; record decision here; update AGENTS.md to point at active set.
- **Consequences:** Docs remain durable knowledge; board remains the only control plane.

## [0002] “One ticket ≈ one run” sizing
- **Context:** keep AI sessions snappy and auditable.
- **Decision:** tickets declare Context (small/medium/large); PR soft caps 5 files / 300 LoC; split when exceeded.
- **Consequences:** tighter reviews; fewer meandering PRs.
