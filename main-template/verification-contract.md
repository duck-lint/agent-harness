# Verification Contract

Verification is a first-class contract. A change is not complete until each required item is resolved.

## Contract Header

- Project:
- Seam:
- Owner agent:
- Last updated:
- Delivery posture: scaffold-only | live-wired
- Status: proposed | active | passed | blocked | deferred

## Behavior Reality Rule

- Behavior-facing seams must name the user-facing acceptance question and a probe that can falsify it.
- Passing structure checks is not enough for `live-wired`: DTOs, fields, files, paths, routes, crates, config, nominal callers, mocks, fixtures, dry runs, and unit tests prove shape only.
- A `live-wired` pass requires a non-test caller or operator surface, the intended backend/target/failure source, and the expected user-visible consequence.
- If the probe cannot run or fails, keep the seam `scaffold-only`, active, blocked, or deferred with owner. Do not call it behavior-complete.

## User-Facing Acceptance Probe

| ID | User-Facing Question | Probe | Intended Backend/Target/Failure Source | Pass Signal | Result | Evidence |
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
