# External Cognition Harness

This directory is the agent cognition harness: externalized cognition through explicit planning, repo-local memory, bounded agent work, verification contracts, failure memory, and model-swappable execution.

The goal is not speed by default. The goal is lower ritual cost while preserving epistemic discipline.

## Core Principles

- Use a map, not an encyclopedia. Runtime prompts point to deeper docs instead of embedding them.
- Keep repo-local memory as the system of record for completed or paused implementation work.
- Keep the active planning horizon on the current user-authorized implementation goal. Archive completed work, then wait for the user to provide the next end goal before designing the next implementation.
- Separate agents behaviorally even when the same model performs them.
- Treat verification as a contract, not an afterthought.
- Treat user-facing behavior as separate from implementation shape. Structure can be scaffolded; behavior needs a falsifiable acceptance probe.
- Track recurring failure patterns separately from decisions.
- Make prompts local-model compatible: bounded tasks, explicit inputs, observable outputs, and low reliance on intuition.

## Canonical Source Layout

```text
agents/ (in .copilot global agent config already)
  harnessed.agent.md
  harness-planner.agent.md
  harness-implementer.agent.md
  harness-reviewer.agent.md
  harness-adversary.agent.md
  harness-archivist.agent.md
  agent-reference-type-system.md

main-template/
  README.md
  runtime-contract.md
  roles.md
  handoff-packet.md
  verification-contract.md
  known-failures.md
  archive-policy.md
  canon/
    type-system-operational.md
    bridge-schema.md

implementation-project-templates/
  open-decisions.md
  implementation-plan.md
  implementation-tracker.md
  implementation-verification-contract.md
  implementation-decisions.md
  implementation-summary.md
  seam-handoff.md
```

## Seeded Host Structure

```text
docs/harness/
  README.md
  runtime-contract.md
  roles.md
  handoff-packet.md
  verification-contract.md
  known-failures.md
  archive-policy.md
  canon/
    type-system-operational.md
    bridge-schema.md

docs/implementation-projects/
  open-decisions.md
  active/
  inactive/
  archive/
  templates/
    open-decisions.md
    implementation-plan.md
    implementation-tracker.md
    implementation-verification-contract.md
    implementation-decisions.md
    implementation-summary.md
    seam-handoff.md
```

For small one-off work, skip project scaffolding and use a lightweight chat plan. For multi-step, repo-scoped, or architecture-shaping work, create numbered implementation files only for the current user-authorized implementation goal.

The implementation-project state folders are the lookup surface: current work lives in `active/`, paused current-scope work lives in `inactive/`, and completed bundles live in `archive/`. Do not maintain a separate implementation index or project table.

## File Responsibilities

- `runtime-contract.md`: always-on orchestration behavior and approval boundaries.
- `roles.md`: planner, implementer, reviewer, adversary, and archivist responsibilities.
- `handoff-packet.md`: standard payload for agent transitions.
- `verification-contract.md`: required validation structure for non-trivial work.
- `known-failures.md`: recurring harness and repo failure patterns.
- `archive-policy.md`: when and how completed work is summarized.
- `canon/type-system-operational.md`: compact operational version of the claim discipline.
- `canon/bridge-schema.md`: full bridge schema for high-risk or epistemically sensitive moves.
- `open-decisions.md`: authoritative current decision surface.
- `implementation-XX-plan.md`: goal, non-goals, seams, blast radius, and approval gates.
- `implementation-XX-tracker.md`: status, work log, agent handoffs, and current next action.
- `implementation-XX-verification-contract.md`: concrete validation obligations and evidence.
- `implementation-XX-decisions.md`: decisions made during the work, separate from failures.
- `implementation-XX-summary.md`: archive closeout summary for a completed numbered bundle.

## Workflow

1. Main Harnessed Agent scouts the request and identifies the controlling surface.
2. Planner creates or updates the plan, tracker, seams, approval gates, user-facing acceptance probe, and verification contract for the current implementation goal only.
3. Human approval is required before crossing approval boundaries.
4. Implementer executes one seam at a time.
5. Reviewer checks the diff against the plan, verification contract, and behavior acceptance probe.
6. Adversary stress-tests assumptions when risk, uncertainty, or recurrence justifies it.
7. Archivist updates decisions, known failures, verification evidence, state-folder placement, and archive summary before turn closeout when project state changed.

## Escalation Boundaries

Escalate before changing schema, API, auth, storage, deployment, billing, destructive operations, broad architecture, compatibility promises, or any behavior whose safest path depends on product intent rather than local mechanics.

Escalate when an agent discovers that its assigned seam is wrong, too large, blocked, or dependent on an unapproved boundary.

## Approval Boundaries

Approval must name the boundary and scope. Approval for one schema change is not approval for a deployment change. Approval for a local refactor is not approval for a compatibility layer.

If approval is missing, write the escalation note and stop at the boundary.

## Archive Strategy

Archive after the verification contract is complete or explicitly deferred. The archive summary should include what changed, why, evidence, decisions, known failures added, and remaining risks. It should not design the next implementation unless the user has already supplied that next end goal.

Do the state move and pointer cleanup in the same turn: completed bundles leave `active/`, and open decisions or paused/deferred bundles stop pointing at stale active paths.

Do not archive by dumping chat history. Archive by preserving the minimum context needed to understand the completed implementation and any explicit unresolved risks.

## Local-Model Compatibility

- Prefer short sections and numbered procedures.
- Use explicit file paths and bounded scopes.
- Avoid relying on style, taste, or intuition without observable criteria.
- Keep agent prompts single-purpose.
- Put deep references behind links, not in runtime context.
- Write handoffs so a weaker model can continue without guessing the hidden plan.
