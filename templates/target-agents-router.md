# Target Repository Router Template

> Reusable Studio template, not a live router. Adapt this semantic pattern in the target repository's root `AGENTS.md` without replacing established instructions. The canonical artifact paths are `.issue-spec/project-profile.md` and `.issue-spec/active.md`.

## Request routing

- For implementation, bug-fix, test, review, or delivery requests with an implementation-ready issue, follow `<existing implementation instructions>`, read the issue, and load only the authoritative engineering documents triggered by the task. Do not automatically invoke Studio or create a checkpoint.
- For unclear requirements, undecided product behavior, architectural choices, cross-cutting decomposition, competing approaches, blockers, unverified assumptions, issue creation, or substantive redesign, use `<Issue Spec Studio/START_HERE.md>` and `.issue-spec/project-profile.md`.
- For design, load only relevant project authorities and then `.issue-spec/active.md` if it exists for the same unfinished objective.
- If `.issue-spec/active.md` is missing, there is no active checkpoint. Do not reconstruct one from conversations, Git history, or assumptions.
- Override either canonical path only when an established repository convention requires it; declare the exact override here and never search heuristically for alternatives.

## Authority

- Approved project governance outranks the Project Profile, checkpoint, and issue.
- Published issues belong to `<issue authority>`.
- Durable roadmap and planning state belongs to `<roadmap authority>`.
- Do not copy issue or roadmap state into the Profile or checkpoint.

## Design cleanup

- Keep a checkpoint limited to objective, confirmed decisions, active assumptions, blocking questions, current decomposition, and next focus.
- Compact at phase boundaries.
- Remove completed or published design state from the checkpoint.
- Remove the checkpoint when no unresolved resumable state remains.
