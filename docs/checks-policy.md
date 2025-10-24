# Docs checks policy (advisory)

Baton keeps docs checks **advisory** to avoid blocking work. The single **blocking** job in branch protection should stay lightweight.

## What runs
- **Markdown lint**: style nits, headings, spacing.
- **Link check**: verify **internal** links only.

> External links are ignored on purpose to avoid flaky network failures.

## When to check external links
If you want to audit external links occasionally (e.g., before a docs-heavy release), add a **manual** workflow and trigger it with `workflow_dispatch`.

Example snippet:
```yaml
name: external-linkcheck (manual)
# Pin the action SHA as you do elsewhere
on: { workflow_dispatch: {} }
jobs:
  lychee-external:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: lycheeverse/lychee-action@7da8ec1fc4e01b5a12062ac6c589c10a4ce70d67
        with:
          args: --verbose --no-progress "**/*.md"
```

## Editorial checks (for Mode=wiki/story)
- Links resolve
- Style guide adherence
- Spellcheck (optional advisory job)

Keep the toolkit minimal; tighten rules downstream if your repo needs stricter docs gates.
