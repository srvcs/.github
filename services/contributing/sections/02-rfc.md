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
