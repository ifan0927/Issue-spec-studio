# Target Repository Router Pattern

> Adapt this semantic pattern to the target repository's existing root `AGENTS.md`. Do not overwrite established instructions or assume universal paths. Replace every placeholder with the repository's actual authority.

## Request routing

- For implementation, bug-fix, test, review, or delivery requests, follow `<existing implementation instructions>` and load only the authoritative engineering documents triggered by the task.
- For design, specification, decomposition, or ambiguity-resolution requests, use `<Issue Spec Studio/START_HERE.md>` and the project-owned Profile at `<actual Project Profile path>`.
- Load `<actual active checkpoint path>` only when it exists for the same unfinished design objective. Do not create a checkpoint unless later resumption is necessary.

## Authority

- Approved project governance outranks the Project Profile, checkpoint, and issue.
- Published issues belong to `<issue authority>`.
- Durable roadmap and planning state belongs to `<roadmap authority>`.
- Do not copy issue or roadmap state into the Profile or checkpoint.

## Design cleanup

- Keep a checkpoint limited to objective, confirmed decisions, active assumptions, blocking questions, current decomposition, and next focus.
- Compact at phase boundaries.
- Remove completed or published design state from the checkpoint.
