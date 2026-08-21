# Product Boundary

## Product statement

Issue Spec Studio is a reusable design methodology and artifact-contract repository. It turns natural-language intent, approved project context, and current repository evidence into a standard Markdown issue that a coding agent or developer can execute.

Studio owns the method up to the coding-ready decision. It does not own a long-lived workspace for any target project and does not control execution after publication.

## Primary user

The primary user is an individual developer who discusses a request with ChatGPT, Codex, or another discussion AI, then hands the approved result to a coding agent, an issue system, or a human implementation workflow.

The design does not add complexity for unproven multi-user, enterprise-governance, hosted, or large-scale platform needs.

## Studio owns

- The design methodology and terminology.
- Artifact semantics and ownership contracts.
- Project Profile, active-checkpoint, decomposition, and issue templates.
- Context-routing and project-onboarding guidance.
- Compact and standard authoring depths and risk overlays.
- Semantic review and the coding-ready gate.
- Consumer-neutral Markdown output conventions.
- Stateless, explicitly labeled examples that clarify the method.
- Prospective adoption and migration guidance.

## The target project owns

- Project governance and authoritative engineering documents.
- A thin root `AGENTS.md` that routes design and implementation intent.
- Its Project Profile and any resumable active checkpoint.
- Repository evidence and project-specific decisions.
- Its existing issue, roadmap, planning, and execution authorities.
- Every project-specific design decision and all resumable design state.

## In scope

- Structure a request and identify missing, ambiguous, conflicting, or unverifiable statements.
- Ask a small number of high-information clarifying questions.
- Distinguish requirements, confirmed decisions, active assumptions, implementation guidance, and agent discretion.
- Decompose large requests into independently implementable and verifiable issues.
- Produce a bounded decomposition without copying the project roadmap.
- Route to project-native authority through a durable Project Profile.
- Preserve only the minimum recoverable state of an unfinished discussion.
- Run semantic review, the coding-ready gate, and human approval before output.

## Out of scope

- Owning permanent per-project workspaces or current project state.
- Storing live Project Profile instances or active checkpoints.
- Acting as a project registry, selected-project workspace, multi-project manager, or dashboard.
- Acting as a planning authority, roadmap mirror, issue tracker, or transcript archive.
- Receiving, scheduling, or running coding agents.
- Managing worktrees, branches, commits, pull requests, CI, merges, or cleanup.
- Tracking ALC or other executor runtime state.
- Mirroring or automatically synchronizing Linear, GitHub, another issue manager, or a project roadmap.
- Becoming a second project-management system.
- Keeping a conversation transcript, chronological activity log, complete brainstorm archive, rejected alternatives, or permanent decision ledger.
- Creating a database, service, TUI, workflow engine, or renderer framework in the MVP.
- Repeating project governance in every issue or allowing an issue to override project rules.
- Applying heavyweight product-document rituals to every request.

## Independence

The core model does not depend on ChatGPT, Codex, Linear, GitHub, ALC, or spec-kit. Platform capabilities are entry points or downstream consumers.

## Success conditions

- Similar requests produce issues with consistent structure and quality.
- A coding agent does not need to repeat high-level product or implementation-strategy decisions.
- The issue is verifiable without overconstraining low-level implementation.
- Small changes cost less to specify than to implement.
- High-risk changes require appropriate evidence, safeguards, and decomposition.
- A new discussion can resume from a clean project-owned checkpoint.
- Project context loads through references instead of repeated full-repository scans.
- Published issues, roadmaps, and execution status exist only in their project-native authorities.
- The Studio repository remains stateless with respect to every target project.
