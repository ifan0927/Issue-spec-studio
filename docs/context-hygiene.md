# Context Hygiene Contract

## Principle

Context uses pull-based progressive disclosure. The target repository's root router selects the workflow, the Project Profile maps topics to authorities, and the discussion AI loads only what the task requires.

A reference is not an instruction to recursively read all of its references.

## Context layers

### L0 — Target root router

Always available and intentionally thin. It distinguishes implementation from design intent and points to the correct project-native instructions.

### L1 — Project Profile

Loaded for a design session. It records stable facts and maps topics to canonical sources with load triggers.

### L2 — Task-relevant governance

Loaded only when triggered, such as authentication, API compatibility, migration, testing, deployment, or delivery rules.

### L3 — Repository evidence

Read source, tests, configuration, or CI only to verify current behavior, validate an assumption, or make the implementation plan concrete.

An existing project's first onboarding may use broad discovery. Routine authoring must not rescan the whole repository without a task-specific reason.

## Reference contract

Each important reference identifies:

- `Ref`: a resolvable document, source location, command authority, issue system, or roadmap system.
- `Purpose`: the decision information it provides.
- `Load when`: the condition that makes it relevant.
- `Authority`: canonical, supporting evidence, or working-only.

Point to the closest authoritative source instead of copying it. Keep leaf documents focused and independently understandable.

## Prohibited patterns

- A root router that copies all Studio rules or all project governance.
- A Project Profile that duplicates a coding guide, issues, or a roadmap.
- A local file that copies live status from Linear, GitHub, or another project system.
- An issue that repeats project-wide Definition of Done or generic test commands.
- Recursive loading of every reference.
- Redirect chains retained only to preserve obsolete paths.
- A final issue that references an active checkpoint, scratch note, or validation report.
- Project-specific working state stored in the Studio repository.

## Active checkpoint

An active checkpoint is optional. Create it only to preserve the minimum recoverable state of an unfinished discussion:

- Current objective.
- Confirmed decisions.
- Active assumptions.
- Blocking questions.
- Current decomposition.
- Next discussion focus.

It must not become:

- A conversation transcript.
- A chronological activity log.
- A complete brainstorm archive.
- A collection of rejected alternatives.
- A permanent decision archive.
- A duplicate project dashboard.
- A mirror of published issues or the project roadmap.

## Compaction rules

### After clarification

- Remove answered questions.
- Keep only effective confirmed decisions needed for resumption.
- Delete rejected alternatives and invalid assumptions.

### After decomposition

- Keep only unresolved issue boundaries and dependencies.
- Publish approved issue boundaries to the existing project authority.
- Do not copy the full contents or status of other issues.

### After candidate drafting

- Do not duplicate content already present in the candidate.
- Keep only unresolved blockers, decisions awaiting approval, and the candidate reference.

### After approval or publication

- Remove completed or published state from the checkpoint.
- Move stable project facts to governance or the Profile only through normal approval.
- Leave published issues, roadmap state, and execution status in their existing authorities.
- Do not create an active-state archive by default.

Version control, published issues, decision records, and project authorities provide history. The active checkpoint does not.

## Workspace rule

Target-project checkpoints live in the target project at a path chosen after inspecting its conventions. They may be tracked or ignored according to that project's collaboration and retention needs.

The Studio repository's `work/` directory is only disposable scratch space for maintaining the Studio methodology. It never contains target-project Profiles, checkpoints, decompositions, issue drafts, or roadmap copies.

## Deterministic maintenance checks

Add scripts only after repeated evidence shows that a deterministic check is useful, for example:

- Broken local references.
- Profile references without purpose or load triggers.
- Final issues that reference working-only artifacts.
- Checkpoints containing transcript or history sections.
- Profiles that copy large governance blocks.
- CJK text in an English-only Studio release.

Scripts validate structure; they do not decide which semantic context to load.
