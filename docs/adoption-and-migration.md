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

1. Inspect the target repository's existing instructions, documentation layout, issue authority, roadmap authority, and established path conventions.
2. Add or refine a thin root `AGENTS.md` router without replacing established implementation guidance.
3. Create `.issue-spec/project-profile.md`; use another path only when an established convention requires it and declare that override in the root router.
4. Record only stable facts and pointers to authoritative sources.
5. Reserve `.issue-spec/active.md` as the optional temporary checkpoint path. Do not create it until unresolved design work genuinely needs resumption.
6. Use the Studio method for the next new design request.

Agents do not search for alternative artifact locations. If the root router declares no override, the canonical `.issue-spec/` paths apply. A missing `active.md` means there is no active checkpoint and must not be reconstructed from old conversations, Git history, or assumptions.

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

When design becomes implementation-ready, move durable architectural decisions to the appropriate authority, publish implementation work to the existing issue system, remove resolved assumptions and questions, and ensure nothing important remains only in the checkpoint. Remove the checkpoint when no unresolved state is required for resumption. Stable project facts move to the Project Profile or governance only through normal approval; published work moves to the issue or roadmap authority.

### Multiple concurrent design efforts

The default is one `.issue-spec/active.md` per project. A target project may define a bounded `.issue-spec/active/` extension only for genuinely concurrent efforts and only when its root `AGENTS.md` declares an explicit selection mechanism. Studio does not coordinate or store those checkpoints.

## Substantive redesign triggers

Reopen design for existing work when, for example:

- The outcome or scope is ambiguous enough to block implementation.
- The implementation strategy is no longer feasible in the current repository.
- New product, security, migration, compatibility, or operational evidence changes the approach.
- The issue contains multiple outcomes that cannot be safely implemented and verified together.
- Acceptance criteria or verification cannot demonstrate completion.

Do not reopen design solely because wording, headings, or template versions have changed.
