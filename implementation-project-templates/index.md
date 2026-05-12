# Implementation Projects

This directory holds the canonical templates for repo-local working memory.
Seed these files into the active repo under `docs/implementation-projects/` for multi-step or repo-scoped work.

## State Folders

- `active/` holds the single numbered implementation bundle currently in live execution.
- `inactive/` holds planned or deferred numbered implementation bundles that are not currently active.
- `archive/` holds completed numbered implementation bundles.

## Current Batch Index

This file is a template. After seeding it into a repo, replace the placeholder row with the current project list for that repo.

| Prefix | Title | Status | Plan | Tracker | Verification | Archive |
| --- | --- | --- | --- | --- | --- | --- |
| implementation-01 |  | active | [Plan](active/implementation-01-plan.md) | [Tracker](active/implementation-01-tracker.md) | [Verification](active/implementation-01-verification-contract.md) |  |

## Closeout Rule

When a bundle completes, move it from `active/` to `archive/`, add `implementation-XX-summary.md`, update this index, and repoint any superseded or inactive references that still target the old active paths in the same turn.

Do not close or archive a `live-wired` behavior bundle unless every live behavior claim maps to a passing user-facing acceptance probe. If the evidence proves only fields, DTOs, files, paths, routes, crates, configs, nominal callers, mocks, fixtures, dry runs, or unit tests, keep the result `scaffold-only` and leave the behavior work active, blocked, or deferred with owner.

## Naming Rules

- Use matching numbered prefixes within a state folder: `active/implementation-01-plan.md`, `active/implementation-01-tracker.md`, and `active/implementation-01-verification-contract.md` while a bundle is live.
- Use `implementation-01-decisions.md` when decisions accumulate.
- Use `implementation-01-seams/` for seam-specific handoffs.
- Use `implementation-01-evidence/` for command output summaries, screenshots, logs, or other validation evidence.
- Archive completed bundles under `archive/` and include `implementation-01-summary.md`.
- Keep `open-decisions.md` as the decision authority rather than pointing decisions at stale active trackers from completed bundles.

## Low-Ritual Rule

Create these files for work that needs continuity, handoffs, or verification memory. Do not create them for trivial one-shot edits.
