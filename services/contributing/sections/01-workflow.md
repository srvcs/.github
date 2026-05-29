## The Contribution Pipeline

1. **Fork** the repository into your own namespace.
2. **Branch** from `main`. One concern, one branch.
3. **Commit** using [Conventional Commits](https://www.conventionalcommits.org).
   Each commit must be independently revertible.
4. **Open a pull request.** CI will assemble, validate, and stage your change for
   deployment review.
5. **Observability is mandatory.** All contributions must ship with structured
   logging, metrics, and distributed tracing.

We do not squash commits. Each commit is an independently revertible deployment
artifact and is retained for audit.
