# Golden Paths (starter set)

These are fast, opinionated checklists—follow them to keep work in **Lane B** unless a Lane-C trigger applies.

## 1) New REST/HTTP endpoint (non-breaking)
**Before**: Lane B; Context small/medium; AI profile fast/thinking; confirm auth model.
**Do**: add route/handler; validate inputs; reuse response shapes; add minimal observability.
**Tests**: unit (success/validation/auth failure), one integration (router).
**Docs**: examples; note defaults.
**Risk**: avoid blocking I/O; timeouts; respect existing rate-limits.
**Rollout**: gate via feature flag if risky.

## 2) New CLI command/subcommand
**Before**: Lane B; Context small/medium; AI profile fast.
**Do**: implement command; clear help; sane defaults; validate flags early; confirm flags for destructive ops.
**Tests**: arg parsing, help output, one smoke run.
**Docs**: examples and exit codes.
**Risk**: no implicit config mutations; respect $HOME/XDG; consider dry-run.

## 3) Feature flag
**Before**: Lane B if default-off & schema-compatible, else Lane C.
**Do**: `feature.<area>.<name>`; default-off; single kill-switch; minimal telemetry.
**Tests**: both branches covered; one end-to-end toggle.
**Docs**: flag description + rollback note.
**Risk**: no schema changes tied to the flag; plan dual-read/write first if needed.

---

## Wiki/Story golden paths
Use these when **Mode=wiki/story** to keep momentum without continuity surprises.

### A) Create or expand entry
**Before**: Lane A/B; Context small/medium.
**Do**: front-matter (title/tags), outline → paragraph(s); add links to related entries; cite sources if relevant.
**Checks**: links resolve; style guide adherence; spellcheck.

### B) Refactor/split entry
**Before**: Lane B (Lane C if moving many inbound links).
**Do**: extract sections; create child entries; add redirects/links; update backlinks.
**Checks**: run link validation; note rename/move plan in PR.

### C) Outline/plot change
**Before**: Lane C if affecting multiple entries or timeline.
**Do**: one-paragraph premise; 2–3 options + trade-offs; chosen path & why; affected entries list.
**Checks**: update outlines; link to continuity decision if made.

### D) Schema/metadata tweak
**Before**: Lane C if adding/removing fields or changing taxonomy.
**Do**: propose template/front-matter diff; migration notes; example entry.
**Checks**: validate links/backmatter; update style guide if needed.
