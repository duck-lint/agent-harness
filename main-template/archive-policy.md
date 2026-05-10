# Archive Policy

Archive completed implementation work so future agents can resume from repo-local memory instead of chat history.

## Archive When

- the verification contract is complete, blocked with explicit owner, or deferred with owner
- decisions are recorded
- known failures are updated or ruled out
- remaining risks are explicit
- the same turn also updates `docs/implementation-projects/index.md`, `open-decisions.md`, and any superseded or inactive pointers that still target the completed bundle

## Archive Summary Must Include

- project prefix
- goal and final status
- files or surfaces changed
- verification evidence
- decisions made
- known failures added or updated
- unresolved risks and revisit triggers

## Do Not Archive

- raw chat transcript
- speculative plans that were never acted on
- stale tasks without status
- implementation details that are already obvious from the diff unless they explain a future risk
- completed bundles left in `active/` as a "retained foundation" exception
- open decisions or inactive bundles that still point at a completed bundle's former active path

## State Folders

Use explicit state folders under `docs/implementation-projects/` as the canonical location for numbered implementation bundles:

- `active/` for the single implementation bundle currently in live execution
- `inactive/` for numbered implementation bundles that are planned, deferred, or otherwise not currently active
- `archive/` for completed implementation bundles

The root `docs/implementation-projects/` directory is not a canonical home for numbered implementation plan, tracker, verification, decisions, seam, evidence, or summary files. Keep only the shared lookup and support surfaces there, such as `index.md`, `open-decisions.md`, `templates/`, and the state folders themselves.

## Archive Location

Use `docs/implementation-projects/archive/` as the canonical home for completed implementation-project bundles.

Keep non-archived numbered project files under `active/` or `inactive/` until work is complete. When an implementation is complete, move its working-memory bundle into `archive/`:

- `implementation-XX-plan.md`
- `implementation-XX-tracker.md`
- `implementation-XX-verification-contract.md`, when one exists
- `implementation-XX-decisions.md`, when one exists
- matching `implementation-XX-seams/` or `implementation-XX-evidence/` directories, when they exist
- `implementation-XX-summary.md`

The root `docs/implementation-projects/index.md` remains the quick lookup surface and must link to the archived files for completed implementations.

`docs/implementation-projects/open-decisions.md` remains the decision authority. Its summary table should link to the decision section itself or another still-authoritative surface, not to a stale active tracker from a completed implementation.

Do not call an implementation archived if its completed plan, tracker, verification record, and summary are only present outside `docs/implementation-projects/archive/`. A completed implementation is archived only when its completed project bundle lives under `docs/implementation-projects/archive/`.

Do not call an implementation active or inactive if its numbered bundle lives at the root. A non-archived implementation is canonical only when its numbered bundle lives under `docs/implementation-projects/active/` or `docs/implementation-projects/inactive/`.

## Same-Turn Closeout

When work changes an implementation state from active to complete, do the archive move and pointer cleanup in the same turn:

- move the numbered bundle from `active/` to `archive/`
- add or update the archive summary
- update `index.md` to remove the completed bundle from the live active set
- repoint `open-decisions.md` and any inactive or superseded bundles that still target the old active paths
- if any of this cannot be completed, mark the closeout blocked with owner instead of leaving the repo in a mixed state
