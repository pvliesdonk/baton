# Stacked PRs (Micro How‑To)

Ship small, linear changes without blocking on big reviews.

## Pattern
1. Branch from the previous PR: `git switch -c feat/next`
2. Keep changes tiny (≤5 files or ≤300 LOC preferred).
3. Open PR with base = previous branch: `gh pr create --base feat/prev --head feat/next`
4. Repeat for each step; merge top→down.

## Tips
- Rebase to keep the stack clean: `git rebase feat/prev`
- Name branches clearly: `docs/...`, `templates/...`, `prompts/...`
- Use the PR template to echo the ticket’s Proposed Solution.
- If CI flakes, re-run jobs or push an empty commit.

> Downstreams benefit most; the toolkit repo also uses this for iterative docs changes.
