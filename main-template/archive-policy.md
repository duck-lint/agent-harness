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

Use `docs/implementation-projects/archive/` for completed summaries. Keep active numbered project files at the root of `docs/implementation-projects/` so agents can find them quickly.
