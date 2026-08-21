# Decomposition and Roadmap Boundaries

## Purpose

Studio helps a human and discussion AI split a bounded goal into independently implementable and verifiable issue outcomes. It does not own a durable roadmap.

The target project's existing issue and roadmap systems remain authoritative for published work, sequencing, priority, schedule, and status. A Project Profile may point to those systems but must not copy them.

## Working decomposition

Before publication, a project-owned checkpoint or optional temporary decomposition may hold:

- The bounded goal and success condition.
- Confirmed scope boundaries.
- Proposed issue outcomes.
- Necessary dependencies.
- Why each outcome can be verified independently.
- The next learning frontier.
- Unresolved decisions that still affect the split.

It must not hold:

- Full issue specifications.
- Live status, priority, assignment, or scheduling copied from an issue system.
- Pull-request, CI, or executor logs.
- Historical versions or rejected splits.
- A speculative long-range issue inventory.

Use [the decomposition template](../templates/decomposition.md) only when the active checkpoint's `Current decomposition` section is too small to remain readable. Remove or compact the temporary artifact after approved outcomes are published.

## Decomposition rules

Prefer smaller issues when each one:

- Delivers a meaningful outcome.
- Can start from a clear repository state.
- Can be reviewed independently.
- Has its own acceptance and verification evidence.
- Can fail or roll back without forcing unrelated work to roll back.
- Does not require the coding agent to infer another issue's strategy.

Common split signals include:

- Multiple user outcomes.
- Preparation, migration, cutover, and cleanup in one item.
- An unknown technical premise that needs a spike or evidence.
- A change too large for reasonable review.
- Verification in different environments or times.
- A failure in one part that makes the entire item unsafe.
- Likely requirement changes that would affect only part of the work.

## Planning frontier

Plan in detail only through the next point that will create important information, such as:

- Completing an architecture spike.
- Confirming migration feasibility.
- Delivering the first vertical slice.
- Validating an integration contract.
- Obtaining production-behavior evidence.

Beyond that frontier, keep only the intended outcome and a provisional direction. Update the project roadmap in its authority after new evidence arrives.

## Publication and change handling

- Publish approved issue outcomes into the project's existing issue authority.
- Record durable sequencing or milestone changes only in the project's existing roadmap authority.
- Do not keep synchronized copies in a Studio-shaped file.
- Unpublished work may be resplit during design.
- Grandfather existing published issues and roadmaps; do not migrate them for template consistency.
- Replace or substantively revise an existing issue only when it is not implementation-ready or new evidence invalidates its strategy.
- For a major change during execution, stop the executor according to project policy and redesign the work; do not build a Studio restart lifecycle.
