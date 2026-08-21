# Context Hygiene Contract

## Principle

Context uses pull-based progressive disclosure. The target repository's root router selects the workflow, the Project Profile maps topics to authorities, and the discussion AI loads only what the task requires.

A reference is not an instruction to recursively read all of its references.

## Context layers

### L0 — Target root router

Always available and intentionally thin. It distinguishes implementation from design intent and points to the correct project-native instructions.

### L1 — Project Profile

Loaded for a design session from `.issue-spec/project-profile.md`, unless the target root `AGENTS.md` explicitly declares an override. It records stable facts and maps topics to canonical sources with load triggers.

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
- Heuristic searches for an alternative Profile or checkpoint.
- Reconstructing a missing checkpoint from conversations, Git history, or assumptions.

## Active checkpoint

The canonical path is `.issue-spec/active.md`. It is optional; if it does not exist and the root router declares no override, there is no active design checkpoint.

Create it only to preserve the minimum recoverable state of an unfinished discussion:

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
- A duplicate Project Profile or general notes file.

## Active-checkpoint lifecycle

### Create

Create `.issue-spec/active.md` only when genuine unresolved design work cannot be completed in the current session and important decisions, assumptions, questions, or decomposition must survive. Do not create it for every issue or any routine implementation task.

### Update

Update it when a confirmed decision, relevant assumption, blocking question, material decomposition, or next focus changes. Rewrite and compact the effective state instead of appending history.

### Complete

When design becomes implementation-ready:

1. Move durable architectural decisions to the appropriate project authority through its normal approval process.
2. Publish implementation work to the project's existing issue system.
3. Remove resolved assumptions and questions.
4. Ensure nothing important exists only in the checkpoint.
5. Remove `.issue-spec/active.md` when no resumable design state remains.

### Archive

Do not archive checkpoints by default. A target project may archive one only when it has an explicit, justified retention requirement. The archive must follow project retention rules and must not become a transcript collection or rejected-ideas repository.

### Multiple concurrent design efforts

The default is one active checkpoint per project. A target project may define a bounded `.issue-spec/active/` extension only when multiple design efforts are genuinely concurrent and its root `AGENTS.md` defines an explicit selection mechanism. Studio never coordinates or stores them.

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

## Location resolution

1. Use `.issue-spec/project-profile.md` and `.issue-spec/active.md`.
2. Override either path only when an established target-repository convention requires it.
3. Declare the exact override in the target root `AGENTS.md`.
4. Never search heuristically for alternative locations.
5. When no override is declared, the canonical path applies.

The Studio repository stores no live target-project artifact. Use an external temporary directory for disposable Studio maintenance state.

## Deterministic maintenance checks

Add scripts only after repeated evidence shows that a deterministic check is useful, for example:

- Broken local references.
- Profile references without purpose or load triggers.
- Final issues that reference working-only artifacts.
- Checkpoints containing transcript or history sections.
- Profiles that copy large governance blocks.
- CJK text in an English-only Studio release.

Scripts validate structure; they do not decide which semantic context to load.
