# Archive Policy

Archive completed implementation work so future agents can resume from repo-local memory instead of chat history.

## Archive When

- the verification contract is complete, blocked with explicit owner, or deferred with owner
- decisions are recorded
- known failures are updated or ruled out
- remaining risks are explicit

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

## Archive Location

Use `docs/implementation-projects/archive/` as the canonical home for completed implementation-project bundles.

Keep proposed and active numbered project files at the root of `docs/implementation-projects/` while work is still in progress. When an implementation is complete, move its working-memory bundle into `archive/`:

- `implementation-XX-plan.md`
- `implementation-XX-tracker.md`
- `implementation-XX-verification-contract.md`, when one exists
- `implementation-XX-decisions.md`, when one exists
- matching `implementation-XX-seams/` or `implementation-XX-evidence/` directories, when they exist
- `implementation-XX-summary.md`

The root `docs/implementation-projects/index.md` remains the quick lookup surface and must link to the archived files for completed implementations.

Do not call an implementation archived if its completed plan, tracker, verification record, and summary are only present at the root. A completed implementation is archived only when its completed project bundle lives under `docs/implementation-projects/archive/`.
