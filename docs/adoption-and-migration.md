# Adoption and Migration

## Prospective policy

Adopt Issue Spec Studio prospectively:

- Existing published issues and roadmaps are grandfathered.
- Do not rewrite existing issues merely to match a new template.
- Do not copy an existing roadmap into Studio or into a Studio-shaped project file.
- Apply the methodology to new design work.
- Apply it to existing work only when that work undergoes substantive redesign.
- Revise or replace an old issue only when it is not implementation-ready or new evidence invalidates its strategy.
- Leave published issue and roadmap status in the project's existing authority.

If an old issue remains clear, feasible, and verifiable, implement it as written. A newer template is not evidence of a defect.

## Initial adoption

1. Inspect the target repository's existing instructions, documentation layout, issue authority, roadmap authority, and ignored working paths.
2. Add or refine a thin root `AGENTS.md` router without replacing established implementation guidance.
3. Place a Project Profile where stable project guidance naturally belongs; use the actual repository convention rather than imposing a universal directory.
4. Record only stable facts and pointers to authoritative sources.
5. Identify where an optional temporary checkpoint can live if a discussion must be resumed.
6. Use the Studio method for the next new design request.

## Active-checkpoint lifecycle

### Create

Create a checkpoint only when a design discussion is unfinished and must survive a context break, handoff, or later session. Do not create one for work that can be completed in the current discussion.

### Update

Update it when the current objective, a confirmed decision, an active assumption, a blocking question, the current decomposition, or the next focus changes. Rewrite the current state; do not append an activity entry.

### Compact

Compact it after clarification, decomposition, candidate drafting, and any other phase boundary. Remove answered questions, invalid assumptions, rejected alternatives, duplicated draft content, and state that has moved to an authority.

### Archive

Archiving is exceptional. Use it only when target-project policy requires an audit or historical record and no existing issue, decision record, or version control history serves that need. An archive is not active context and must follow the project's own retention rules.

### Remove

Remove the checkpoint when the issue is approved or published, the design is abandoned with no reusable decision, or no unresolved state is required for resumption. Stable project facts move to the Project Profile or governance only through normal approval; published work moves to the issue or roadmap authority.

## Substantive redesign triggers

Reopen design for existing work when, for example:

- The outcome or scope is ambiguous enough to block implementation.
- The implementation strategy is no longer feasible in the current repository.
- New product, security, migration, compatibility, or operational evidence changes the approach.
- The issue contains multiple outcomes that cannot be safely implemented and verified together.
- Acceptance criteria or verification cannot demonstrate completion.

Do not reopen design solely because wording, headings, or template versions have changed.
