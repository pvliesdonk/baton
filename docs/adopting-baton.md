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

---

## Quick‑start (CLI) — bootstrap a new repo with Baton

> Prereqs: `gh` (logged in) and `git`. This creates a new repo, copies templates, enables minimal CI, protects `main`, and opens a first ticket.

```bash
# === Set your variables ===
OWNER=your-org-or-user
REPO=my-new-repo
VISIBILITY=private     # or: public
BATON_SRC=pvliesdonk/baton
BATON_REF=v0.1         # or: main

# 1) Create the repo
gh repo create $OWNER/$REPO --$VISIBILITY --confirm \n  -d "Project bootstrapped with Baton"

# 2) Clone it locally
git clone https://github.com/$OWNER/$REPO.git
cd $REPO

# 3) Fetch Baton kit (temp clone)
TMP=$(mktemp -d)
git clone --depth 1 --branch $BATON_REF https://github.com/$BATON_SRC.git "$TMP/baton"

# 4) Copy templates into place
mkdir -p .github/ISSUE_TEMPLATE .github/workflows
cp "$TMP/baton"/templates/AGENTS.template.md ./AGENTS.md
cp "$TMP/baton"/templates/issue-forms/* .github/ISSUE_TEMPLATE/
cp "$TMP/baton"/templates/.github/pull_request_template.md .github/pull_request_template.md
cp "$TMP/baton"/templates/ci/*.yml .github/workflows/ 2>/dev/null || true
cp "$TMP/baton"/templates/CODEOWNERS.example .github/CODEOWNERS 2>/dev/null || true
cp "$TMP/baton"/templates/.github/dependabot.yml .github/dependabot.yml 2>/dev/null || true

# 5) Minimal blocking CI (copy upstream example)
cp "$TMP/baton"/.github/workflows/ci.yml .github/workflows/ci.yml

# 6) Commit and push
git add .
git commit -m "chore: bootstrap with Baton templates"
git push origin main

# 7) Protect main: require the blocking job
read -r -d '' JSON <<'EOF'
{
  "required_status_checks": { "strict": true, "contexts": ["blocking"] },
  "enforce_admins": true,
  "required_pull_request_reviews": { "required_approving_review_count": 0 },
  "restrictions": null,
  "allow_force_pushes": false,
  "allow_deletions": false
}
EOF


gh api repos/$OWNER/$REPO/branches/main/protection -X PUT \
  -H "Accept: application/vnd.github+json" \
  --input - <<<"$JSON"

# 8) Open the first ticket (or use the web form)
gh issue create --title "feat: initial scaffold" \
  --body "Use the Feature issue form in the repo UI to capture Lane, Context, AI profile, and acceptance criteria."

# 9) Start the first working session
# Paste the Entry Ritual from templates/prompts/entry-ritual.md into your chat with the AI.
```

> Want an AI to do steps 1–9 for you? Use the **Repo Setup Agent** prompt: `templates/prompts/repo-setup.md` (supports MCP Local Ops with workspace `/host/workspace`).
