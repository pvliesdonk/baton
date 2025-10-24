# Workspace Shells & `gh` (Generic)

Many clients provide a **workspace shell** and access to **GitHub CLI** (`gh`). Baton doesn’t require a specific setup, but these tips help:

## Concepts

- **Workspace shell:** a terminal context where the agent can run commands. Examples include *MCP Local Ops* (workspace path often `/host/workspace`) and other vendor shells.
- **`gh` CLI:** authenticated GitHub CLI for repo, PR, and run management.

## Good practices

- Keep the **board** as the single source of truth; don’t store status in the workspace.
- Prefer idempotent scripts and pinned action SHAs.
- Use small, stacked PRs; re-run checks via `gh run` when needed.

## Handy commands

```bash
# Repo info / PRs
gh repo view
gh pr list --json number,title,headRefName,mergeStateStatus

# Runs
gh run list --workflow ci --limit 10
gh run watch <run-id>

# Branch protection (example)
gh api repos/<owner>/<repo>/branches/main/protection
```

> Note: If your client exposes a different workspace path or API, adapt the examples accordingly.
