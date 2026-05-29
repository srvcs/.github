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
