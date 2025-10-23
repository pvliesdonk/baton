# Upstream vs Downstream (Baton)

**Purpose:** This repo hosts the **Baton toolkit**. It provides templates, prompts, and example CI for **downstream projects**. The toolkit repo itself is **not bound** by those rules.

## Upstream (this repo)
- Ships **assets**: prompts, templates under `templates/`, examples, and docs.
- Keeps CI **minimal** (security baseline + basic health).
- May dogfood selectively, but nothing here is mandatory for this repo.
- Guarantees: versioned changes, concise docs, examples that work.

## Downstream (projects using Baton)
- Copy or pin assets from `templates/` and tailor.
- Adopt the rituals: lanes (A/B/C), context sizing (small/medium/large), AI profile (thinking/fast/cheap), golden paths.
- Use the **board as the control plane**; do not split status across docs.

## Where things live
- **Templates:** `templates/` (issue forms, CI examples, AGENTS template, CODEOWNERS examples)
- **Docs:** `docs/` (how to adopt, compatibility examples, stuck protocol)
- **Upstream binders:** minimal `AGENTS.md` (points at templates)

## Non‑goals for upstream
- Enforcing project rituals on this repo.
- Heavy mandatory CI beyond a small security/health baseline.

> Rule of thumb: if it’s a **rule for projects**, it belongs in `templates/` (or docs). If it’s a **rule for this repo**, keep it minimal and pragmatic.
