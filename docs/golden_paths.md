# Golden Paths (starter set)

These are fast, opinionated checklists—follow them to keep work in **Lane B** unless a Lane‑C trigger applies.

## 1) New REST/HTTP endpoint (non‑breaking)
**Before**: Lane B; Context small/medium; AI profile fast/thinking; confirm auth model.
**Do**: add route/handler; validate inputs; reuse response shapes; add minimal observability.
**Tests**: unit (success/validation/auth failure), one integration (router).
**Docs**: examples; note defaults.
**Risk**: avoid blocking I/O; timeouts; respect existing rate‑limits.
**Rollout**: gate via feature flag if risky.

## 2) New CLI command/subcommand
**Before**: Lane B; Context small/medium; AI profile fast.
**Do**: implement command; clear help; sane defaults; validate flags early; confirm flags for destructive ops.
**Tests**: arg parsing, help output, one smoke run.
**Docs**: examples and exit codes.
**Risk**: no implicit config mutations; respect $HOME/XDG; consider dry‑run.

## 3) Feature flag
**Before**: Lane B if default‑off & schema‑compatible, else Lane C.
**Do**: `feature.<area>.<name>`; default‑off; single kill‑switch; minimal telemetry.
**Tests**: both branches covered; one end‑to‑end toggle.
**Docs**: flag description + rollback note.
**Risk**: no schema changes tied to the flag; plan dual‑read/write first if needed.
