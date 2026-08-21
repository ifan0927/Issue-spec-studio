# Project Onboarding

## Purpose

Onboarding equips a target repository to route design work without moving project context into Studio. The result is an approved Project Profile owned by the target repository and a thin root router that preserves the repository's existing implementation authority.

## Inspect before adopting

Before adding files, inspect:

- Existing root and nested agent instructions.
- Documentation and architecture conventions.
- Build, test, lint, and verification commands.
- CI, branch, pull-request, review, and Definition of Done rules.
- Security, migration, compatibility, observability, deployment, and rollback guidance.
- Existing issue and roadmap authorities.
- Any established convention that would make a canonical `.issue-spec/` path incompatible.

Use `.issue-spec/project-profile.md` and `.issue-spec/active.md` by default. Override either path only when an established repository convention requires it, and declare the exact override in the target root `AGENTS.md`. Do not search heuristically for an alternative. If the root router declares no override, the canonical path applies.

## Root routing contract

The target repository's root `AGENTS.md` should distinguish:

- Implementation requests: route to the repository's existing implementation instructions and authoritative engineering documents.
- Design, specification, decomposition, and ambiguity-resolution requests: route to Studio's `START_HERE.md`, `.issue-spec/project-profile.md`, relevant project authorities, and `.issue-spec/active.md` only when it exists.
- Implementation requests with an implementation-ready issue: route to the issue and relevant project authorities without automatically loading Studio or creating a checkpoint.

Use [the target router template](../templates/target-agents-router.md) as a semantic starting point, not as a command to replace existing instructions.

## Minimum governed context

As appropriate for the project, the Profile must be able to locate:

- Project identity, goal, and domain.
- Repository structure and major modules.
- Agent instructions.
- Coding and architecture boundaries.
- Build, test, lint, and verification commands.
- Delivery and review conventions.
- Project-wide Definition of Done.
- Applicable security, migration, compatibility, observability, deployment, and rollback rules.
- Issue and roadmap authorities.

Do not create empty governance documents for categories that do not apply.

## New project path

1. Confirm the project goal, domain, and boundaries.
2. Establish the minimum necessary governance and implementation instructions.
3. Add risk-specific rules only where real risk exists.
4. Add the thin root router.
5. Create a concise Profile at `.issue-spec/project-profile.md` containing stable facts, references, and load triggers.
6. Obtain human approval before using the Profile to author implementation issues.

## Existing project path

1. Perform one bounded repository discovery.
2. Locate explicit and implicit authority in agent instructions, README files, CI, configuration, tests, architecture documents, and established conventions.
3. Identify the existing issue and roadmap authorities.
4. Propose routing and Profile mappings, including gaps, duplication, and conflicts.
5. Obtain human approval.
6. Land only the necessary router, governance additions, and `.issue-spec/project-profile.md` in the target repository.
7. Use the Profile for future targeted loading instead of repeating full discovery for every issue.

Discovery evidence is a proposal until approved. It does not automatically become policy.

## Configuration depth

- **Zero configuration:** For a simple or experimental project, use repository evidence and general engineering principles without pretending that undefined project policy exists.
- **Low configuration:** Recommended default. Use a concise Profile pointing to existing instructions, README files, commands, CI, architecture guidance, and planning authorities.
- **Full configuration:** For long-lived or high-risk projects, add explicit architecture, security, migration, compatibility, operations, and delivery references.

Risk determines depth; template completeness does not.

## Profile maintenance

```text
detect relevant change -> propose mapping or policy update -> human approval -> land in target repo -> targeted rescan
```

- Batch-approve simple path, command, or mapping maintenance when appropriate.
- Explicitly approve behavior, architecture, Definition of Done, or safety-policy changes.
- Land new policy before publishing an issue that depends on it.
- Rescan only affected areas.

The absence of `.issue-spec/active.md` means there is no active checkpoint. Do not create one during onboarding and do not reconstruct one from old conversations or repository history.

## Conflict precedence

1. Approved target-repository governance.
2. Canonical sources referenced by the approved Profile.
3. Approved issue-level requirements and plan.
4. Active assumptions and suggestions.

The project's issue and roadmap authorities govern publication and status, but their content cannot override repository governance. A conflict blocks readiness and requires a separate project-level policy decision.
