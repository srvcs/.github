## 🗺️ Repository Map

| Path | Role | Artifact | Pipeline |
|------|------|----------|----------|
| `readme/sections/` | This document's sections | `README.md` | `build-root-readme.yml` |
| `profile/sections/` | Org profile sections | `profile/README.md` | `build-readme.yml` |
| `services/contributing/sections/` | Contribution policy | `.github/CONTRIBUTING.md` | `build-contributing.yml` |
| `services/security/sections/` | Security policy | `.github/SECURITY.md` | `build-security.yml` |
| `services/support/sections/` | Support surface | `.github/SUPPORT.md` | `build-support.yml` |
| `services/governance/sections/` | Governance model | `.github/GOVERNANCE.md` | `build-governance.yml` |
| `services/code-of-conduct/sections/` | Code of conduct | `.github/CODE_OF_CONDUCT.md` | `build-code-of-conduct.yml` |
| `services/pull-request-template/sections/` | PR template | `.github/PULL_REQUEST_TEMPLATE.md` | `build-pull-request-template.yml` |

Hand-maintained control-plane configuration lives alongside the pipelines:

| Path | Role |
|------|------|
| `.github/workflows/` | One independently deployable pipeline per artifact |
| `.github/ISSUE_TEMPLATE/` | Issue intake forms (bug, service proposal, incident retrospective) |
| `.github/CODEOWNERS` | Review routing |
| `.github/dependabot.yml` | Keeps pinned Actions current |
| `profile/assets/` | Shared imagery |

> Every artifact above is **gitignored and force-committed** by its pipeline. If a
> file carries the generated-artifact banner, its source is a `sections/` directory.
