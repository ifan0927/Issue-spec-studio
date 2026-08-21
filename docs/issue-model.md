# Canonical Issue Model

## Representation

The canonical output is one standard Markdown issue.

- Humans can read and edit it directly.
- Coding agents can interpret stable headings.
- A low-noise version marker, such as an HTML comment, avoids a second YAML or JSON source of meaning.
- The MVP does not maintain parallel human-readable and machine-readable artifacts.
- Composable sections share stable semantics; not every task fills a large template.

## Semantic categories

### User requirement

An externally observable behavior, capability, or constraint that must be delivered. It contains no unconfirmed speculation.

### Confirmed decision

A human-approved choice that constrains scope or implementation strategy. The final issue states the effective result, not its decision history.

### Assumption

A premise that is temporarily used but not fully verified. Any assumption affecting feasibility or acceptance must be verified or converted into an explicit requirement before readiness. A blocking assumption cannot remain in the final issue.

### Implementation guidance

The decided strategy, architecture boundary, sequence, and integration approach. It guides the coding agent without becoming line-by-line design.

### Agent discretion

Low-level choices that do not affect external behavior, project rules, strategy, safety, compatibility, or verification. State important discretion boundaries; do not enumerate trivial choices.

## Required core

Every coding issue contains at least:

- Goal.
- Scope.
- Implementation Plan.
- Acceptance Criteria.
- Verification.

## Composable sections

Add only when relevant:

- Context or Problem.
- Out of scope.
- Requirements.
- Applicable project references.
- Constraints.
- Agent discretion.
- Dependencies.
- Risks and safeguards.
- Migration, compatibility, or rollback.
- Observability or deployment.
- Issue-specific Definition of Done delta.

Project-wide Definition of Done, coding style, generic test commands, and governance remain in target-repository authorities. An issue includes only a task-specific delta or a directly relevant reference.

## Authoring depth

### Compact

Use for a local, clear, low-risk change with no cross-boundary effect and direct verification, such as copy, a small bug, one setting, or a local refactor.

Goal, Scope, Implementation Plan, Acceptance Criteria, and Verification remain required but may be short. The discussion AI chooses this path from the request; no fixed classifier is required.

Escalate naturally to standard depth when clarification reveals cross-module impact, compatibility, migration, security, deployment, rollback, unknown dependencies, or indirect verification.

### Standard

Use for a normal feature, important bug fix, cross-boundary change, or work requiring several explicit decisions.

A standard issue normally describes context, requirements, out of scope, implementation strategy, agent discretion, acceptance, verification, dependencies, and relevant risk.

### Risk overlays

High risk is not a third template. Add appropriate sections and evidence to compact or standard core when work involves:

- Data migration.
- API, schema, or behavioral compatibility.
- Authentication, authorization, or security.
- Deployment sequencing.
- Rollback or recovery.
- Multi-repository or cross-system integration.
- Observability or production-data correctness.

An overlay may require separate preparation, change, cutover, verification, or cleanup issues.

## Issue size

One issue represents one outcome, one implementation plan, one reviewable delivery boundary, and one set of verification evidence.

Prefer several small and explicit issues over one uncertain multi-stage issue. A coding agent must be able to execute safely without making high-level strategy decisions.

## Requirements, acceptance, and verification

- A requirement states behavior or a constraint that must hold.
- An acceptance criterion states how that behavior can be observed; it does not merely repeat the requirement.
- Every important requirement has acceptance or explicit verification evidence.
- Evidence may come from a test, command, observable state, API behavior, or focused manual check.
- Lightweight identifiers or prose relationships are enough; a complex traceability matrix is not required.

## Implementation plan

The plan must decide the core strategy, architecture boundary, important order, integration approach, and safety or compatibility method.

It should not prescribe inconsequential function decomposition, local naming, normal language idioms, or behavior already governed by the repository.

If the plan proves infeasible, the issue tells the coding agent to stop, provide evidence, and report a specification defect rather than silently changing the strategy.
