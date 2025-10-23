# Adopting Baton (v0.1)

This repo is the upstream kit. To use it in a project repo:

## 1) Create labels & project fields
- **Fields (Project):** Priority {P0–P3}, Size {XS–XL}, Target {next|later|backlog}, Owner, **Context {small|medium|large}**.
- **Labels:**
  - type:{feature,bug,chore,docs}
  - status:{needs-spec,ready,in-progress,needs-review,blocked}
  - from:{ai,human}
  - risk:security
  - area:{frontend,backend,infra} (trim to what you’ll use)

Create two views: **Planning** (group by status, sort by Priority) and **Delivery** (hide "ready"). See `docs/project-views.md`.

## 2) Copy the docs
Add `AGENTS.md`, `ARCHITECTURE.md`, `DECISIONS.md` from this kit. Update project specifics.

## 3) CI & security
- Enable one **blocking** CI job; keep others **advisory** until stable.
- Turn on branch protection for `main` (PRs‑only; require blocking checks).
- Add CODEOWNERS for hot zones if you have them.
- **Dependency updates:** copy `templates/.github/dependabot.yml` (or use Renovate; choose one).
- SBOM: generate CycloneDX on release (this kit includes a stub).

## 4) Issue/PR templates
- Use the **downstream issue forms** in `templates/issue-forms/` (copy into `.github/ISSUE_TEMPLATE/`).
- Keep the PR template that echoes the Proposed Solution (see `templates/.github/pull_request_template.md`).

## 5) Day‑to‑day usage
- Start sessions with the **Entry Ritual** (`templates/prompts/entry-ritual.md`).
- Keep tickets within the **context** class; split if they swell.
- Use **golden paths** to stay in Lane B; escalate for Lane C triggers.
- When blocked, follow `docs/stuck.md`.

## 6) Upgrading
- Pin this kit by tag; review the changelog before adopting new versions.

## Appendix: Choose one dependency updater
- We provide `templates/.github/dependabot.yml`. If you prefer Renovate, use it instead. Pick **one**.
- Always **pin GitHub Actions** by SHA when enabling CI templates.
