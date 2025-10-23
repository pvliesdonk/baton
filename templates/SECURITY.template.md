# Security Policy (Template)

Use this file in **downstream repos** that ship software. Customize owners/SLAs.

## Reporting a Vulnerability

- Prefer a private report via **GitHub Security Advisories**.
- If GHSA is not available, email: _security@example.com_ (replace).
- We will acknowledge within _N_ business days and provide status updates.

## Supported Versions

- List supported release lines or tags here.

## Handling Secrets

- Never commit real credentials. If it happens, **rotate immediately**.
- Use secret scanning (gitleaks) in CI; see our example config.

## Links

- GitHub Security Advisories: https://docs.github.com/code-security/security-advisories/about-github-security-advisories
- Example gitleaks config: `docs/gitleaks-config.example.toml`
