# Changelog

All notable changes to this project will be documented in this file.

The format is based on Keep a Changelog, and this project uses **tags** for releases.

## [Unreleased]
### Added
- **Mode/aliases** guidance across prompts; Architect Lane-C clause for wiki/story.
- **Feature** form: Mode dropdown + optional Sources and Canon status.
- PR template: optional Sources/Preview lines.
- Docs: wiki/story golden paths; checks policy (advisory).

### Changed
- README + AGENTS mention Mode & aliases and link to the glossary.

## [1.0.0] — 2025-10-24
### Added
- Ultra-minimal **glossary** (lanes, context sizes, AI profiles) and **lane legend** in Entry Ritual; linked from AGENTS binders.
- Upstream/Downstream boundary clarified; ultra-minimal stance documented.
- Downstream `SECURITY.template.md` for GHSA reporting.
- Minimal `.editorconfig` and `.gitattributes` (plus template copies).
- Advisory docs checks (markdownlint + link check) with pinned actions; advisory-only.

### Changed
- Upgrading guidance: pin by tag; read `CHANGELOG.md` + `DECISIONS.md`.
- Upstream issue forms collapsed to `Task` + `Decision`.

### Removed
- Upstream Dependabot.
- Upstream SBOM workflow (lives in templates for downstreams).
