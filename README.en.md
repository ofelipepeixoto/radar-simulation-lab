# Radar Simulation Lab

[Português](README.md)

An original project for a local simulation lab with wholly synthetic data and auditable results. The proposal helps one person understand parameters, costs, limits and each event contributing to a fictional result.

**Status on 2026-10-22: specification prepared; product not implemented; MVP not accepted.** Publishing documents does not automatically approve the journey or its implementation.

## Proposed minimum journey

Choose a fictional scenario → review parameters and limits → simulate locally → understand a risk block → inspect events and a reconciled result → export a report.

The proposed scope is local, offline and single-user, with one fictional linear instrument and leverage fixed at one. The model and strategy will be original and documented. No external financial account, exchange connection or financial operation is part of this proposal.

**There is no application to install or run here.** The [synthetic example](examples/synthetic/README.md) is a manually calculated accounting exercise, not output from an existing engine.

## Available material

| Material | Status |
| --- | --- |
| Scope, journey and architecture | Proposed; D01–D03 pending |
| Backlog and acceptance criteria | Prepared to guide implementation and validation |
| Accounting example | Fictional and manual, with explicit formulas |
| Engine, interface, persistence and exporter | Not implemented |
| Functional checks, CI and human validation | No evidence; pending |
| Hosted application | None; this repository contains documentation |

## Documentation

Detailed documents are currently in Portuguese:

| Document | Purpose |
| --- | --- |
| [Scope](docs/PRODUCT_SCOPE.pt-BR.md) and [journey](docs/USER_JOURNEY.pt-BR.md) | Proposal and minimum decisions D01–D03 |
| [Architecture](docs/ARCHITECTURE.pt-BR.md) | Original design, not implemented |
| [MVP status](docs/MVP_STATUS.pt-BR.md) | Code, documentation, local checks, CI and human validation |
| [Evidence inventory](docs/EVIDENCE_INVENTORY.pt-BR.md) | Original provenance, example and verification limits |
| [Backlog](docs/BACKLOG.pt-BR.md) | Priority, dependencies, effort, completion evidence and owner decisions |
| [Acceptance](docs/MVP_ACCEPTANCE.pt-BR.md) | Evidence required for acceptance |
| [Security](SECURITY.md) and [rights](RIGHTS.md) | Information handling and provenance |
| [Exclusions](docs/EXCLUDED_MATERIALS.pt-BR.md) and [review](docs/PUBLICATION_REVIEW.pt-BR.md) | Public-batch boundaries |

## Next steps

1. Approve or adjust D01–D03: synthetic/local scope, journey and first minimum delivery.
2. Implement the scenario, engine, accounting, risk and report, then integrate the local journey.
3. Demonstrate functional correctness, local execution, relevant CI and the owner's completion of the journey on an identified version.

Test counts or a green pipeline alone do not establish readiness. Real trading is not planned. External data, mandatory AI, n8n, paid infrastructure, multiple users and deployment are outside this MVP.

## Rights and contributions

This batch contains original documentation and a synthetic example. It does not distribute external platforms' code, assets, records or research reports. Do not submit private information in issues.

No general reuse license has been selected for the original editorial content; see [RIGHTS.md](RIGHTS.md). Implementation depends on the product decisions described in the scope.
