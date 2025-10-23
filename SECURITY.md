# Security

- Use secrets scanning (gitleaks) in CI.
- Rotate any committed credentials immediately; do not rely on allowlists.
- Prefer narrow allow rules with justification if needed.

See `docs/gitleaks-config.example.toml` for a commented example used by downstream projects.
