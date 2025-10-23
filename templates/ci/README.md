# CI Templates

This folder contains **advisory** workflows for downstream projects. Copy into .github/workflows/ in your repo.

- semantic-pr.yml — checks PR titles against Conventional Commits (non‑blocking).
- path-filters.yml — surfaces schema/public_api/security changes (non‑blocking).
- pr-size-guard.yml — comments when a PR is large (>5 files or >300 LOC).
- sbom-pr.yml — generates a CycloneDX SBOM on PRs (artifact only).

Pin actions to SHAs before enabling.
