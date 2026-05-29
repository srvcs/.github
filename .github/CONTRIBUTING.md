<!-- GENERATED ARTIFACT — do not hand-edit. Source of truth: services/contributing/sections/*.md. Redeployed by .github/workflows/build-contributing.yml -->

# Contributing to srvcs.cloud

Thank you for your interest in contributing. Every contribution is treated as a
first-class, independently deployable change.

Before you begin, please ensure your change owns **exactly one concern.** Changes
that own more than one concern must be decomposed into multiple changes, each with
its own pull request, review cycle, and rollback plan.

---

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

---

## Proposing a New Service

If your change might warrant a new microservice, do not implement it. Open a
**Service Proposal** issue first so the Architecture Review Board can evaluate
whether the change warrants a dedicated runtime boundary.

A function is eligible to become a service when it meets **all** of the following:

- It represents a single, well-bounded concern.
- It can be described in a single sentence.
- It can be deployed, scaled, and operated independently of its callers.

Proposals are reviewed by the Architecture Review Board before any implementation
begins.
