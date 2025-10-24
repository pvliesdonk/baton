# Baton — Agentic Pair‑Engineering Toolkit

Baton is a reusable way to pair‑program with AI using **one control plane** (GitHub Issues/Project), three hats (Planner, Architect, Developer), **lanes** (A/B/C), and **context‑fit tickets** (small/medium/large).

> This repo hosts the **toolkit** (prompts, templates, example CI). Downstream projects **adopt** it; the toolkit repo itself stays minimal.

## What Baton is / isn’t
- **Is:** An upstream toolkit of prompts, docs, and copy‑pasteable templates. The **board is the control plane**. Upstream CI is intentionally minimal; advisory checks are examples under `templates/ci/`.
- **Isn’t:** A framework/CLI/policy engine. This repo does not ship app code, package manifests, SBOMs, or dependency update bots — those belong in **downstream** repos.

## Adopt from `templates/`
Copy only what you need from `templates/` into your project and tune locally. Upstream stays slim.

## Getting started (new project, new repo)

1. **Create labels & project fields** (once per org): see `docs/adopting-baton.md`.
2. **Copy templates** into your repo:
   - `templates/AGENTS.template.md` → project root as `AGENTS.md` (then customize).
   - `templates/issue-forms/*` → `.github/ISSUE_TEMPLATE/` (Feature/Bug/Spike/Decision).
   - `templates/.github/pull_request_template.md` → `.github/pull_request_template.md`.
   - `templates/ci/*.yml` → `.github/workflows/` (choose advisory workflows you want).
   - Optional: `templates/CODEOWNERS.example` → `.github/CODEOWNERS`.
3. **Enable minimal branch protection** (main-first): require your single **blocking** check.
4. **Kick off your first ticket** using the **Feature** form. Fill **Lane, Context, AI profile**, and (optional) **Suggested model**.
5. **Start the session** by pasting the **Entry Ritual** into chat: see `templates/prompts/entry-ritual.md`.
6. **(Optional) Use the Repo Setup Agent**: see `templates/prompts/repo-setup.md` if you want an AI to bootstrap the repo via CLI (with a workspace shell).

## Ongoing use (day-to-day)
- Keep the **board** as the single source of truth (never duplicate status in docs).
- Size tickets to the chosen **context**; split if they grow.
- Default to **Lane B** (notify‑then‑go); escalate to **Lane C** on Auto‑C triggers.
- Follow the **Stuck Protocol** (`docs/stuck.md`).
- Use **golden paths** (software: feature flag / CLI / REST; wiki/story: create/expand/refactor/outline/schema).
- Prefer **one profile** (Planner/Architect/Developer) unless your project truly needs more.

## What’s in this toolkit
- **Prompts:** Planner, Architect, Developer, Entry Ritual, Repo Setup (`templates/prompts/`).
- **Templates:** Issue forms, PR template, CODEOWNERS example, CI examples (`templates/`).
- **Docs:** Adoption guide, compatibility examples, stuck protocol, upstream vs downstream boundary, **CI troubleshooting**, **checks policy**, **stacked PRs**, **context sizing**, **glossary**, **workspace & gh** (`docs/`). See also: **glossary** for **Mode** and role **aliases**.

## Upgrading
- Pin Baton by **tag** in downstreams.
- Review `CHANGELOG.md` and `DECISIONS.md` before upgrading.

## Share your learnings (field reports)
Have something battle‑tested that helped you? Please upstream the learning so others benefit.

- Open an **Issue** (discussion) or a **PR** (docs/templates/prompts).
- Include context (project size/stack, AI profile/models), links to downstream Issues/PRs and CI runs, and a short before/after.
- Keep the toolkit minimal: prefer **templates/docs/prompts** over new enforcement.

See **CONTRIBUTING.md → Field reports & upstreaming** for what to include and acceptance guidelines.

**License:** MIT
