# Project Profile Template

> Reusable Studio template, not a live project artifact. Copy and adapt it as `<project-root>/.issue-spec/project-profile.md`, then remove the word `Template` from the copied heading. This target-project-owned file records stable project facts and routes topics to authoritative sources. It does not copy governance, issues, roadmaps, live status, session history, active questions, temporary assumptions, transcripts, or detailed architecture documents. Initial creation and substantive policy changes require human approval.

## Project identity

- Project:
- Goal:
- Domain:
- Repository:
- Profile path: `.issue-spec/project-profile.md`
- Profile status: Draft / Approved
- Last approved:

## Project boundaries

- In scope:
- Out of scope:

## Stable constraints and invariants

Record only approved, repository-wide constraints that are not better owned by a referenced authority.

- None.

## Development workflow

- Primary development flow:
- Verification entry point:
- Delivery authority:

## Design routing

- Studio bootstrap: `<resolvable path or reference to Issue Spec Studio/START_HERE.md>`
- Active checkpoint: `.issue-spec/active.md` (optional; missing means none)
- Issue authority: `<system and project/repository reference>`
- Roadmap authority: `<system and project/reference, or same as issue authority>`

The authority entries are pointers only. Do not copy issues, milestones, status, priority, or roadmap content into this Profile.

If an established repository convention requires a different Profile or checkpoint path, the target root `AGENTS.md` must declare the exact override. Otherwise retain the canonical paths above. Never search heuristically for an alternative.

## Repository map

| Area | Ref | Purpose | Load when | Authority |
|---|---|---|---|---|
| Agent instructions |  |  | Every coding task | Canonical |
| Architecture |  |  | Changing module boundaries or integrations | Canonical |
| Build |  |  | Planning or verifying code changes | Canonical |
| Test |  |  | Planning acceptance and verification | Canonical |
| Lint / static analysis |  |  | Preparing verification | Canonical |
| Coding style |  |  | Changing implementation code | Canonical |
| Branch / delivery |  |  | Preparing publication or delivery | Canonical |
| Definition of Done |  |  | Running the ready gate | Canonical |

## Domain and architecture routing

| Topic | Ref | Purpose | Load when | Authority |
|---|---|---|---|---|
|  |  |  |  |  |

## Risk governance routing

| Topic | Ref | Purpose | Load when | Authority |
|---|---|---|---|---|
| Security |  |  | Authentication, authorization, secrets, or sensitive data |  |
| Migration |  |  | Persistent schema or data changes |  |
| Compatibility |  |  | Public API, schema, or behavioral contract changes |  |
| Observability |  |  | Production behavior or operational signals change |  |
| Deployment / rollback |  |  | Release sequencing or recovery matters |  |

## Stable project facts

Record only concise facts that are durable, approved, and not better owned by another canonical document.

- None.

## Stable terminology

| Term | Meaning | Authority, if defined elsewhere |
|---|---|---|
|  |  |  |

## Known governance gaps

List only confirmed gaps that affect issue authoring. Do not create a general wish list.

- None.

## Approval

- Approved by:
- Approved at:
- Notes:
