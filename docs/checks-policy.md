# Docs checks policy (advisory)

Baton keeps docs checks **advisory** to avoid blocking work. The single **blocking** job in branch protection should stay lightweight.

## What runs
- **Markdown lint**: style nits, headings, spacing.
- **Link check**: verify **internal** links only.

> External links are ignored on purpose to avoid flaky network failures.

## When to check external links
Trigger the manual workflow (if you copy it from `templates/ci/`) with `workflow_dispatch` to audit external links occasionally, or before a docs-heavy release.

## Editorial checks (for Mode=wiki/story)
- Links resolve
- Style guide adherence
- Spellcheck (optional advisory job)

Keep the toolkit minimal; tighten rules downstream if your repo needs stricter docs gates.
