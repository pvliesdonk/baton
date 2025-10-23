# Contributing to Baton

This is the **upstream toolkit**. Keep changes small and well‑scoped.

- Use Issues/PRs; squash merge.
- Docs and templates should be short, copy‑pastable, and **pinned** (actions by SHA).
- When you add a rule for projects, put it under `templates/` (or docs), **not as enforcement** here.
- Record notable behavior changes in `DECISIONS.md`.

## Field reports & upstreaming
Share battle‑tested learnings from real projects. We prefer **evidence‑backed** changes that help many downstreams.

**How to contribute**
- Open an **Issue** (discussion) or a **PR** (docs/templates/prompts).
- Keep the upstream minimal; propose **templates/docs/prompts**, not new enforcement.

**What to include**
- **Context:** project type/size, stack, AI profiles/models used.
- **Problem & approach:** what broke or worked; what you tried.
- **Evidence:** links to downstream Issues/PRs, CI runs, before/after snippets.
- **Generality:** why this is broadly useful (or how to scope it to a template).

**Where your change should live**
- **`templates/`** — things downstreams copy and enable (CI examples, issue forms, PR template, CODEOWNERS example).
- **`docs/`** — guidance, playbooks, policy examples.
- **`prompts/`** — role prompts used across projects.
- **upstream CI** — stays **minimal**; advisory checks belong in templates.

**Acceptance guidelines**
- Short, **copy‑pasteable** artifacts.
- Pinned actions; no reliance on floating tags.
- Clear boundaries (one source of truth = the board).
- Aligns with compatibility and checks policies.

**License**
Contributions are accepted under the repository’s MIT license.
