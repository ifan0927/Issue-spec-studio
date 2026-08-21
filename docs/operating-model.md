# Operating Model

## Session location and entry

A design session takes place in the target repository, not in a Studio-owned project workspace. The target repository's thin root `AGENTS.md` identifies intent:

- Implementation intent routes to existing project implementation instructions and authoritative engineering documents.
- Design, specification, decomposition, and ambiguity-resolution intent routes to the Studio methodology and the project's Profile.

The router should remain thin. It points to authorities; it does not copy them.

## Roles

### Human

- Sets the product objective and major trade-offs.
- Answers questions that can change scope, strategy, safety, verification, or decomposition.
- Approves Project Profile changes, project policy changes, decompositions when needed, and final issues.
- Stops downstream execution when new evidence invalidates an approved strategy.

### Discussion AI

- Detects design intent and loads only relevant project context.
- Identifies gaps, ambiguity, conflicts, assumptions, and risk.
- Keeps only the current effective decisions and assumptions needed for the active discussion.
- Chooses compact or standard authoring depth.
- Decomposes oversized work without mirroring the project roadmap.
- Produces an implementation plan and coding-ready review.
- Cleans up the active checkpoint when state becomes durable elsewhere or no longer matters.

### Coding agent

- Follows target-repository governance and the approved issue.
- Implements the decided strategy, boundaries, and order.
- Chooses low-level details only within explicit agent discretion.
- Stops and reports evidence when the plan is infeasible, contradictory, or requires a higher-level decision.

### Project-native consumer

GitHub, Linear, another issue manager, a roadmap tool, or an execution controller owns published work and downstream state. It is not a source of Studio methodology and Studio does not mirror it.

## Design stages

These are reasoning stages, not a persistent state machine, and they do not require separate artifacts.

### Analyze

- Restate the outcome.
- Compare intent with project context and current repository evidence.
- Identify gaps, contradictions, unverifiable statements, and risk.
- Decide whether the request needs decomposition.

### Clarify

- Ask only questions that may change scope, strategy, safety, verification, or issue boundaries.
- Convert answers into current confirmed decisions.
- Remove answered questions and rejected alternatives from the checkpoint.

### Decompose

- Split a large request into independently implementable and verifiable outcomes.
- Record only the current proposed boundaries, dependencies, and next learning frontier.
- Publish approved work into the project's existing issue and roadmap authorities instead of maintaining a Studio roadmap.

### Plan

- Decide implementation direction, important boundaries, order, and integration points.
- State what the coding agent may decide.
- Avoid unnecessary low-level prescriptions.

### Review and approve

- Run semantic validation and the coding-ready gate.
- Show blockers, advisories, and the ready result to the human.
- Freeze the issue after approval.
- Exclude the internal validation review from the final issue.

## Lightweight lifecycle

```text
discussion
   | create only if resumption is needed
   v
minimal active checkpoint -> candidate issue -> approved issue -> project issue authority
           ^                                                        |
           | compact or remove                                      v
           +------------------------------------------------ project roadmap/execution authority
```

There is no Studio workflow database or permanent project workspace.

- A checkpoint is optional and continuously rewritten.
- A candidate issue remains editable during review.
- An approved issue is frozen until publication.
- After publication, the project-native authority owns content and status.
- Published or completed design state leaves the checkpoint instead of accumulating.

## Approval points

- Initial Profile mapping for an existing repository.
- Changes to project policy or stable Project Profile facts.
- Issue boundaries and dependencies when decomposition affects multiple published items.
- Final coding-ready issue.

Routine pointer maintenance may be batch-approved. A policy change must land in the target repository before an issue can rely on it.

## Prospective process

The methodology applies to new design work. Existing issues and roadmaps remain valid in their current authorities. Revisit existing work only when substantive redesign is necessary; template availability alone is never a reason to rewrite it. The complete policy is in [Adoption and Migration](adoption-and-migration.md).
