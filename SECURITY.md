# Security

This upstream repo is a **toolkit** (docs, prompts, templates). It does not ship application code.

- If you spot a problem here, please **open an Issue** (use the Task or Decision template).
- For **downstream software** using this kit, report vulnerabilities via **GitHub Security Advisories (GHSA)** in those repos.
- Use secrets scanning (gitleaks) in CI; rotate any committed credentials immediately.

See `docs/gitleaks-config.example.toml` for a commented example and `templates/SECURITY.template.md` for a downstream SECURITY policy.
