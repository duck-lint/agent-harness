# Known Failures

Track recurring failure patterns here. This is not a bug dump and not a decision log. A known failure is a pattern later sessions should detect earlier.

## Entry Format

| ID | Pattern | Trigger | Symptom | Likely Cause | Prevention Rule | Cheapest Check | Last Seen | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| KF-001 | Shape mistaken for behavior | A seam adds types, fields, files, paths, routes, crates, configs, mocks, fixtures, or a nominal caller and is described as implemented behavior | Tests pass but the user-facing probe fails, is absent, or only proves that output shape exists | Verification checked structure instead of the reason the feature exists | Every `live-wired` behavior claim must map to a passing named user-facing acceptance probe before archive-complete status | Ask: what can the user now do that they could not do before, and which non-test probe proves it? |  | active |

## Rules

- Add an entry when a failure recurs, spreads, or exposes a harness weakness.
- Keep entries short and searchable.
- Link to evidence in implementation-project files when available.
- Do not record blame, moods, or one-off noise.
- Promote repeatable prevention into tooling or runtime rules when possible.
