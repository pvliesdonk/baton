# Quickstart: GitHub CLI snippets for Baton adoption

These snippets make a greenfield repo "Baton-ready" fast. Ensure `gh` is authenticated and you have admin rights.

## 1) Create Baton labels (lane/context/profile)
```bash
export OWNER=yourname
export REPO=yourrepo
for L in "lane:A|Baton lane A (routine)" \
         "lane:B|Baton lane B (notify-then-go)" \
         "lane:C|Baton lane C (design-required)" \
         "context:small|Baton context small" \
         "context:medium|Baton context medium" \
         "context:large|Baton context large" \
         "profile:thinking|AI profile thinking" \
         "profile:fast|AI profile fast" \
         "profile:cheap|AI profile cheap"; do
  name="${L%%|*}"; desc="${L#*|}"
  gh api -X POST "/repos/$OWNER/$REPO/labels" -f name="$name" -f color="ededed" -f description="$desc" >/dev/null || echo "(label '$name' may already exist)"
done
```

## 2) Minimal branch protection (require Semantic PR job id `check`)
```bash
cat > /tmp/protection.json <<'JSON'
{
  "required_status_checks": {
    "strict": false,
    "contexts": ["check"]
  },
  "enforce_admins": true,
  "required_pull_request_reviews": {
    "dismiss_stale_reviews": true,
    "required_approving_review_count": 0
  },
  "restrictions": null
}
JSON

gh api -X PUT "/repos/$OWNER/$REPO/branches/main/protection" --input /tmp/protection.json
```

## 3) Allow workflows to post statuses on fresh repos
```bash
gh api -X PUT "/repos/$OWNER/$REPO/actions/permissions" -f default_workflow_permissions=write -f can_approve_pull_request_reviews=false
```

## 4) Re-run checks after changing settings
```bash
# From the PR page you can Rerun checks; or via CLI:
RUN_ID=$(gh run list -R $OWNER/$REPO --json databaseId -q '.[0].databaseId')
if [ -n "$RUN_ID" ]; then gh run rerun $RUN_ID -R $OWNER/$REPO; fi
```

**Notes**
- Required check name should match the **job id** from your workflow (Baton default: `check`).
- See also: `templates/ci/semantic-pr.yml` and `templates/ci/README.md`.
