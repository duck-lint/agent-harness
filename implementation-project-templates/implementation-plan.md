# Implementation XX Plan

## Intent


## Non-Goals


## Delivery Posture

- `scaffold-only | live-wired`
- If fields, DTOs, files, paths, routes, crates, configs, nominal callers, mocks, fixtures, dry runs, or unit tests are the only evidence, say `scaffold-only` explicitly.
- Runtime, model, tool, turn, control, proposal, sidecar, storage, retrieval, UI, CLI, and interface behavior is not `live-wired` until a non-test caller or operator surface exercises the intended path against the intended backend, target, or failure source.

## User-Facing Acceptance

- Acceptance question:
- Named probe:
- Intended backend, target, data, or failure source:
- Pass signal:
- What would prove this is only scaffold:

## Observed Evidence


## Assumptions And Unknowns


## Affected Surfaces


## Blast Radius


## Seams

1. 

## Completion Rule

- Split scaffold-hardening seams from the first live-path seam when both exist.
- Do not mark behavior complete on fixture, mock, dry-run, serialization, type, field, file, path, route, crate, config, or nominal-caller evidence alone.
- A behavior seam is complete only when every `live-wired` behavior claim maps to a passing named user-facing acceptance probe, or the missing caller, backend, target, data, failure source, credential, or operator path is explicit and the posture remains `scaffold-only`, blocked, or deferred with owner.
- A successful command that returns the wrong user-facing answer is a failed behavior probe, not a pass.

## Approval Gates

- [ ] Schema
- [ ] API
- [ ] Auth
- [ ] Storage
- [ ] Deployment
- [ ] Destructive operation
- [ ] Broad architecture
- [ ] Product intent

## Verification Contract

Use `implementation-XX-verification-contract.md`.

## Next Handoff

- Agent Role:
- Scope:
- Stop condition:
