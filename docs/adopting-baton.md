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

Create two views: **Planning** (group by status, sort by Priority) and **Delivery** (hide "ready").

## 2) Copy the docs
Add `AGENTS.md`, `ARCHITECTURE.md`, `DECISIONS.md` from this kit. Update project specifics.

## 3) CI & security
- Enable the CI workflows; replace placeholders with pinned actions.
- Turn on branch protection for `main` (PRs‑only; require blocking checks).
- Add CODEOWNERS for hot zones if you have them.
- Enable weekly dependency updates; auto‑merge dev bumps on green CI.
- SBOM: generate CycloneDX on release (this kit includes a stub).

## 4) Issue/PR templates
- Use the **downstream issue forms** in `templates/issue-forms/` (copy into `.github/ISSUE_TEMPLATE/` in your project). They include **Lane**, **Context**, **AI profile**, and **Suggested model**.
- Keep the PR template that echoes the Proposed Solution.

## 5) Day‑to‑day usage
- Start sessions with the **entry ritual** in `AGENTS.md`.
- Keep tickets within the **context** class; split if they swell.
- Use **golden paths** to stay in Lane B; escalate early for Lane C.

## 6) Upgrading
- Pin this kit by tag; review the changelog before adopting new versions.

That’s it—keep the board as the control plane and avoid a second source of truth.
