<!-- GENERATED ARTIFACT — do not hand-edit. Source of truth: services/governance/sections/*.md. Redeployed by .github/workflows/build-governance.yml -->

# Governance

srvcs.cloud is governed by the **Architecture Review Board** (ARB), a body that
exists to ensure no function becomes a service without due process.

---

## How Decisions Are Made

All material changes follow the **Request For Comments (RFC)** process:

1. An RFC is opened describing the proposed change and its blast radius.
2. The ARB reviews the RFC for single-concern compliance.
3. No function may become a service without sign-off from at least **three members
   of the Architecture Review Board.**
4. Approved RFCs are merged, deployed, and scheduled for a retrospective.

Decisions are made by consensus of the Architecture Review Board.

---

## Roles

| Role | Responsibility |
|------|----------------|
| **Architecture Review Board** | Approves or rejects new runtime boundaries |
| **Service Owners** | Own exactly one concern each (see `CODEOWNERS`) |
| **On-Call** | Maintains the region and responds to incidents |
| **Contributors** | Decompose problems into services and ship observability |

Roles are assigned per service. No individual may own more than one concern at a
time without an approved exception.
