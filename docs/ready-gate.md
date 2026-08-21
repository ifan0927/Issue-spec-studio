# Coding-ready Gate

## Gate result

Before human approval, the discussion AI returns one result:

- `BLOCKED`: A gap or conflict must be resolved first.
- `READY WITH ADVISORIES`: Execution is possible, with non-blocking risk the human should understand.
- `READY`: No known blocker remains.

The review result is approval input, not part of the final issue or a permanent artifact.

## Blocking conditions

An issue is not coding-ready if any condition holds:

- The Goal could represent different outcomes.
- Scope or out-of-scope boundaries are unclear.
- An unanswered question can change strategy or acceptance.
- The issue conflicts with target-repository governance.
- A dependency is unavailable without an explicit treatment.
- The coding agent must still choose a high-level strategy.
- A requirement lacks acceptance or verification evidence.
- Verification cannot run or produce evidence in the expected environment.
- The issue contains multiple outcomes that cannot be delivered as one reviewable and verifiable unit.
- Migration, compatibility, security, deployment, or rollback risk is untreated.
- Feasibility depends on an unverified assumption.
- The issue depends on an active checkpoint or another working-only artifact.

## Ready checklist

### Intent and boundary

- [ ] Goal describes one specific, observable outcome.
- [ ] Scope states what changes.
- [ ] Out of scope is explicit where needed.
- [ ] The issue fits one independently reviewable and verifiable delivery unit.

### Decisions and plan

- [ ] All high-impact questions are resolved.
- [ ] Confirmed issue-specific decisions appear in the issue.
- [ ] The Implementation Plan identifies strategy, boundaries, integration points, and order.
- [ ] Agent discretion cannot change requirements, safety, compatibility, or acceptance.
- [ ] The coding agent does not need to repeat product or architecture planning.

### Project consistency and routing

- [ ] The design session ran in the target repository.
- [ ] Relevant Project Profile references were loaded.
- [ ] The issue does not override or copy project governance.
- [ ] Repository evidence supports the plan, or a prerequisite issue creates the necessary foundation.
- [ ] Publication targets the project's existing issue authority.
- [ ] No issue or roadmap status is mirrored in Studio or the checkpoint.

### Acceptance and evidence

- [ ] Every important requirement is verifiable.
- [ ] Acceptance Criteria describe observable outcomes.
- [ ] Verification explains how to obtain evidence.
- [ ] Required test, lint, build, or manual checks are clear.
- [ ] Any issue-specific Definition of Done delta is explicit without repeating project-wide policy.

### Risk

- [ ] Applicable risk overlays are identified.
- [ ] Compatibility, migration, rollback, security, deployment, and observability evidence is included when needed.
- [ ] High-risk work is split into safely stoppable and verifiable steps.

### Final hygiene

- [ ] No open questions, `TBD`, `TODO`, or unresolved placeholders remain.
- [ ] No transcript, rejected alternatives, brainstorm archive, or validation report remains.
- [ ] References are directly relevant and point to project-native authorities.
- [ ] The issue is clean and independently readable Markdown.
- [ ] The active checkpoint can now be compacted or removed.

## Approval and freeze

Human approval covers the Goal, Scope, major decisions, issue split, Implementation Plan, Acceptance Criteria, and Verification.

After approval, treat the issue as frozen. A substantive semantic change before publication requires renewed approval. After publication, follow the project's existing issue-revision policy rather than silently changing a Studio draft.
