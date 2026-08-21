# Start Here

This file is the minimum bootstrap for Issue Spec Studio. It routes work; it does not contain the complete methodology or any target-project state.

## Where a session runs

A design session runs in the target project's repository. Begin with that repository's thin root `AGENTS.md` router:

- Implementation requests follow the project's existing implementation instructions and authoritative engineering documents.
- Design, specification, decomposition, or ambiguity-resolution requests use the Studio methodology.

The Studio repository supplies the method and templates. It is not a workspace for target projects.

## Basic design loop

1. Confirm the target project and current design objective.
2. Read the target project's approved Project Profile.
3. Follow its load triggers to read only the required governance and repository evidence.
4. Analyze, clarify, decompose, and plan in the current discussion.
5. Create an active checkpoint only if the discussion must be resumed later; keep it minimal and compact it at every phase boundary.
6. Produce a candidate Markdown issue and run the coding-ready review.
7. Freeze the output after human approval, publish it to the project's existing issue authority, and remove completed state from the active checkpoint.

## Methodology routing

Read a reference only when its trigger applies. Do not recursively expand references merely because they exist.

| Current task | Required reference |
|---|---|
| Understand product boundaries, responsibilities, or non-goals | `docs/product-boundary.md` |
| Understand artifacts, ownership, authority, versioning, or freshness | `docs/information-model.md` |
| Understand the end-to-end design session and artifact lifecycle | `docs/operating-model.md` |
| Design or review a canonical issue | `docs/issue-model.md`, `docs/ready-gate.md` |
| Decompose a large request or coordinate with a project roadmap | `docs/roadmap-and-decomposition.md` |
| Onboard a new or existing target repository | `docs/project-onboarding.md` |
| Route context or maintain an active checkpoint | `docs/context-hygiene.md` |
| Adopt the methodology or migrate existing work prospectively | `docs/adoption-and-migration.md` |
| Understand publication, consumers, ALC, or adapter boundaries | `docs/consumer-boundaries.md` |
| Measure specification quality | `docs/quality-measurement.md` |
| Decide MVP scope or subsequent work | `docs/mvp.md`, `HANDOFF.md` |

## Authority rule

Approved target-repository governance outranks a Project Profile, active checkpoint, decomposition, and issue. If a conflict appears, stop the ready decision and propose a project-level change; never encode an exception in an issue.

## Output rule

The final output is one clean, independently readable Markdown issue. It contains no unresolved questions, discussion transcript, validation report, rejected alternatives, or duplicated project-wide guidance.
