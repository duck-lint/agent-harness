# Implementation XX Tracker

## Status

- State: proposed | active | blocked | reviewing | archived
- Current agent role:
- Delivery posture: scaffold-only | live-wired
- Current seam:
- Next action:

## User-Facing Acceptance Probe

- Acceptance question:
- Probe:
- Pass signal:
- Current result: pending | pass | fail | blocked | skipped with reason | deferred with owner
- Evidence:

## Work Log

| Date | Agent Role | Change | Evidence | Next |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Seam Status

| Seam | Owner Agent | Status | Verification | Notes |
| --- | --- | --- | --- | --- |
|  |  | proposed |  |  |

## Reality Check

- If behavior is validated only by fields, DTOs, files, paths, routes, crates, configs, nominal callers, mocks, fixtures, dry runs, or unit tests, keep it `scaffold-only`.
- A seam becomes `live-wired` only after one non-test caller or operator surface exercises the intended path against the intended backend, target, or failure source and the named user-facing acceptance probe passes.
- If the probe exits successfully but fails the user-facing question, record `fail` and keep the bundle active, blocked, or deferred. Do not archive it as behavior-complete.

## Blockers

| Blocker | Boundary | Owner Agent | Resolution |
| --- | --- | --- | --- |
|  |  |  |  |

## Closeout Note

- If this bundle completes, move it from `active/` to `archive/`, add `implementation-XX-summary.md`, and update `open-decisions.md` plus any stale paused or deferred pointers in the same turn.
- Do not complete or archive `live-wired` behavior unless every live behavior claim maps to a passing user-facing acceptance probe. If only structural checks passed, record the result as `scaffold-only` and leave the live behavior active, blocked, or deferred with owner.
