# Implementation XX Verification Contract

Use [../../harness/verification-contract.md](../../harness/verification-contract.md) as the source template.

## Contract Header

- Project:
- Seam:
- Owner agent role:
- Last updated:
- Delivery posture: scaffold-only | live-wired
- Status: proposed

## Behavior Reality Rule

- If the seam touches runtime, model, turn, tool, control, proposal, sidecar, storage, retrieval, UI, CLI, or interface behavior, include mapped non-test executable probe coverage for each claim marked `live-wired`.
- The probe must hit the intended backend, target, data, or failure source through a caller or operator surface that exists outside tests.
- Fixture, mock, dry-run, serialization, type, field, file, path, route, crate, config, nominal-caller, or unit coverage alone can validate `scaffold-only` seams, but the missing live caller, backend, target, data, failure source, credential, or operator path must stay explicit.
- A successful process exit is not enough. The pass signal must answer the acceptance question that motivated the seam.

## User-Facing Acceptance Probe

| ID | Acceptance Question | Probe | Intended Backend/Target/Data/Failure Source | Pass Signal | Result | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| U-001 |  |  |  |  | pending |  |

## Claim-To-Probe Map

Every `live-wired` behavior claim must map to at least one passing user-facing acceptance probe. One probe may cover multiple claims only when this table says so.

| Claim ID | Probe ID | Coverage Rationale | Status |
| --- | --- | --- | --- |
| V-001 | U-001 |  | pending |

## Claims Under Test

| ID | Claim | Source | Expected Observable Consequence | Status |
| --- | --- | --- | --- | --- |
| V-001 |  |  |  | proposed |

## Required Checks

| ID | Check | Command or Probe | Pass Signal | Result | Evidence |
| --- | --- | --- | --- | --- | --- |
| C-001 |  |  |  | pending |  |

## Manual Review

| ID | Surface | Reviewer | Required Observation | Result |
| --- | --- | --- | --- | --- |
| M-001 |  |  |  | pending |

## Skipped Or Deferred Checks

| Check | Reason | Risk | Owner | Revisit Trigger |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Acceptance Rule

Every check must be pass, fail, blocked, skipped with reason, or deferred with owner. Failures and blocked items require either implementation follow-up, explicit quarantine, or human approval to proceed.

For behavior-facing work, acceptance also requires every `live-wired` behavior claim to map to a passing `User-Facing Acceptance Probe`. If only structural checks pass, the result is `scaffold-only`, not complete behavior.

If the work changes project-memory state, acceptance also requires a documented closeout result for the relevant implementation bundle, index, and decision pointers: pass, blocked with owner, or deferred with owner.
