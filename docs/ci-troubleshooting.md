# CI Troubleshooting

A short playbook for common CI pitfalls when adopting Baton.

## Gitleaks on PRs

- Use `actions/checkout` with `fetch-depth: 0` or PR diffs can fail with "unknown revision".
- Set `env: GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}` on the gitleaks step.
- Do **not** pass `with: args` to `gitleaks/gitleaks-action@v2` — the action reads env/flags internally.
- Pin all actions by **commit SHA**, not tags.
- SBOM generation should live **downstream** (use templates like `templates/ci/sbom-pr.yml`).

## Required checks

- Protect the **job name** you own (e.g., `blocking`), not the workflow name.
- Keep exactly one required job unless you have a compelling risk case.

## Stuck runs

- If a check looks stale, click **Re-run jobs** or push an empty commit: `git commit --allow-empty -m 'ci: nudge' && git push`.
- Use `gh run list` / `gh run watch` to inspect jobs.

## Signals vs noise

- Start new checks **advisory**. Promote to **blocking** only after several green PRs with low/no flake.

> This doc is guidance for downstream projects; the toolkit repo stays minimal.
