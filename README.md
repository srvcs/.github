<!-- GENERATED ARTIFACT — do not hand-edit. Source of truth: readme/sections/*.md. Redeployed by .github/workflows/build-root-readme.yml -->

<div align="center">

<a href="https://srvcs.cloud"><img src="profile/assets/srvcs-nobg.png" alt="srvcs.cloud" width="160" /></a>

# `.github` — the [srvcs.cloud](https://srvcs.cloud) control plane

### **The organization-level repository. One repo. One concern. Many pipelines.**

_Every document here is an independently deployable artifact._

<br/>

![Artifacts](https://img.shields.io/badge/artifacts-8_deployed-brightgreen?style=for-the-badge)
![Pipelines](https://img.shields.io/badge/pipelines-8_independent-blue?style=for-the-badge)
![Hand_edits](https://img.shields.io/badge/hand--edits-0-informational?style=for-the-badge)
![Drift](https://img.shields.io/badge/drift-reconciled-ff69b4?style=for-the-badge)

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)

</div>

---

## 🛰️ What This Is

This is the **`.github` repository** for the srvcs.cloud organization — the control
plane from which every shared, org-level document is operated.

Profile, contribution policy, security policy, support surface, governance model,
code of conduct, and pull request template are **not files you edit.** They are
**artifacts you deploy.** Each one is assembled from a set of small,
single-purpose sections and continuously reconciled to production by its own
pipeline.

You change the inputs. The platform reconciles the output.

---

## ⚙️ How Deployment Works

Every published document is a **generated artifact.** Its source of truth is a
directory of numbered, independently deployable sections:

```
sections/00-*.md → sections/01-*.md → sections/NN-*.md
                          │
                          ▼
         build-<artifact>.yml  (GitHub Actions)
                          │
                          ▼
              <ARTIFACT>.md  (do not hand-edit)
```

On every push that touches a section — or the workflow itself — the matching
pipeline:

1. **Assembles** the sections in order, separated by horizontal rules, behind a
   generated-artifact banner.
2. **Reconciles** the result against what is currently in production, force-staging
   the artifact (it is gitignored) and diffing against `HEAD`.
3. **Redeploys** only on drift — committing as `github-actions[bot]` and pushing
   with a rebase-and-retry loop to survive concurrent deploys.

Artifacts carry a `GENERATED ARTIFACT — do not hand-edit` banner for a reason.
**Edit the sections. Never edit the artifact.** The next push would reconcile your
change out of existence.

---

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

---

<div align="center">

**[srvcs.cloud](https://srvcs.cloud)** · One concern. One service. One deployment pipeline.

<sub>This README is a generated artifact. Edit `readme/sections/*.md` — the pipeline handles the rest.</sub>

</div>
