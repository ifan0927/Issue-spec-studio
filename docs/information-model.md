# Canonical Information Model

## Model shape

Studio defines a small set of Markdown contracts connected by references. It does not maintain a parallel human/machine schema and does not host project instances of those artifacts.

```text
Studio methodology, contracts, templates, and stateless examples
              |
              | applied inside
              v
Target repository root router (AGENTS.md)
       | implementation intent         | design intent
       v                               v
Ready issue and project           .issue-spec/project-profile.md
engineering authorities                    |
                                          v
                         optional .issue-spec/active.md
                                          |
                                          v
                              approved Markdown issue
                                          |
                                          v
                         project issue / roadmap authority
```

Arrows mean navigation or constraint, never content replication.

## Authority and responsibility

| Artifact or system | Owner | Responsibility | Must not contain |
|---|---|---|---|
| Studio methodology | Studio repository | Reusable method, templates, guidance, and contracts | Target-project current state |
| Project governance | Target repository | Coding, architecture, testing, security, migration, deployment, and delivery rules | Issue-specific working notes |
| Root `AGENTS.md` router | Target repository | Route implementation intent to project instructions and design intent to Studio | A full copy of Studio or project governance |
| Project Profile | Target repository | Stable project facts and topic-to-authority pointers | Copied source documents, live issue status, or a roadmap mirror |
| Active checkpoint | Target repository | Minimum recoverable state of one unfinished design discussion | History, rejected alternatives, published work, or stable project facts |
| Candidate issue | Current design session | One execution contract under ready review | Exploration history or unresolved blockers |
| Approved issue | Current design session until publication | Frozen, human-approved execution contract | Mutable execution state |
| Issue authority | Target project's existing system | Published issue content, ID, status, priority, assignment, and progress | Studio-internal working state |
| Roadmap authority | Target project's existing system | Durable priorities, sequencing, milestones, and roadmap status | A duplicate Studio roadmap |

The non-overlapping authority map is:

| Concern | Authority |
|---|---|
| Studio methodology | Issue Spec Studio repository |
| Project routing | Target project root `AGENTS.md` |
| Stable project context | `.issue-spec/project-profile.md` or its explicitly declared override |
| Architecture | Target project's architecture authority |
| Temporary design state | `.issue-spec/active.md` or its explicitly declared override |
| Published implementation work | Target project's existing issue system |
| Roadmap | Target project's existing planning authority |
| Runtime and implementation behavior | Target project's code and technical authorities |

## Canonical target-project locations

An adopting target repository uses:

```text
<project-root>/
|-- AGENTS.md
`-- .issue-spec/
    |-- project-profile.md
    `-- active.md
```

`.issue-spec/project-profile.md` is durable, project-owned stable context and a set of authority pointers. `.issue-spec/active.md` is temporary, project-owned resumable state for unresolved design work. `active.md` is optional; it must not exist permanently when no design work needs to resume.

Location resolution is deterministic:

1. Use `.issue-spec/project-profile.md` and `.issue-spec/active.md` by default.
2. Override either path only when an established repository convention requires it.
3. Declare every override explicitly in the target project's root `AGENTS.md`.
4. Never search the repository heuristically for an alternative Profile or checkpoint.
5. When no override is declared, use the canonical `.issue-spec/` path.
6. When `.issue-spec/active.md` does not exist, there is no active design checkpoint.
7. Never reconstruct a missing checkpoint from old conversations, Git history, or assumptions.

## Artifact responsibilities

### Project Profile

The Project Profile records stable project identity, durable facts that are not already better owned elsewhere, and pointers with load triggers to canonical sources. It may contain project purpose and boundaries, stable architectural constraints, repository-wide invariants, development workflow, authority mappings, links to architecture and planning authorities, subsystem instruction locations, and stable terminology.

It may point to commands or planning authorities but must not copy their contents. It must not contain live implementation status, open-issue copies, a roadmap mirror, session history, active design questions, temporary assumptions, transcripts, or duplicated detailed architecture documents.

### Active checkpoint

The active checkpoint exists only when an unfinished discussion must survive a context boundary. It contains:

- Current objective.
- Confirmed decisions still needed to resume this discussion.
- Active assumptions.
- Blocking questions.
- Current decomposition.
- Next discussion focus.

It is working-only, continuously rewritten, and removed when no unresolved resumable state remains. It is not a transcript, activity log, brainstorm archive, rejected-alternative collection, permanent decision archive, dashboard, implementation tracker, issue copy, roadmap mirror, duplicate Profile, or general notes file.

The default is one active checkpoint per project. A target project may define a bounded `.issue-spec/active/` extension only for genuinely concurrent design efforts and only when its root router declares an explicit selection mechanism. Studio never selects, coordinates, or stores those checkpoints.

### Candidate and approved issues

A candidate issue is the single execution contract under ready review. After human approval it becomes frozen output and is published to the project issue authority. Publication transfers ongoing ownership to that authority; Studio does not keep a synchronized copy.

### Design decomposition

Large-request decomposition may be maintained temporarily in the checkpoint or another project-owned working artifact. It describes proposed issue boundaries and dependencies only until they are published into the project's established planning authority. It is not a second roadmap.

### Validation review and quality event

A validation review contains blockers, advisories, and a ready decision for the human reviewer; it is not merged into the final issue or retained as a permanent artifact. A quality event is a lightweight note attached to the project's existing issue or quality system when downstream work reveals a specification defect.

## Information placement

| Information | Canonical owner |
|---|---|
| Project-wide rule | Target-repository governance |
| Stable project fact or authority pointer | Project Profile |
| Unconfirmed assumption or open question | Active checkpoint only |
| Current unresolved decomposition | Active checkpoint or project-owned temporary decomposition |
| Issue-specific requirement, decision, plan, or discretion | Approved issue |
| Published issue state | Project issue authority |
| Durable roadmap, priority, or schedule | Project roadmap/planning authority |
| Execution, PR, CI, or runtime state | The applicable project-native execution system |

One fact has one canonical owner. Other artifacts use references or a task-specific derived statement only when necessary.

## Decision scope

- A project-wide decision changes project governance.
- A stable project fact or routing decision changes the Project Profile.
- An issue-specific decision belongs in the issue.
- An unapproved or unresolved decision remains only in the active checkpoint.
- A durable priority or sequence belongs in the existing roadmap authority, not Studio.

Changes to the product boundary, canonical information model, authority hierarchy, or coding-ready gate require human approval before they become Studio methodology.

An issue cannot downgrade project policy into an issue-level exception.

## Versioning and freshness

- Issues use a low-noise `issue-spec` marker so their contract version can be identified later.
- Git versions Studio rules, templates, and target-repository Profile changes.
- Existing approved or published issues are not migrated when a template changes.
- Before ready review, reread relevant Profile references and verify assumptions that affect feasibility.
- After publication, the executor reports conflicts against current governance rather than expecting Studio to synchronize a draft.
- Project growth triggers a targeted Profile update proposal, human approval, and a targeted rescan; it does not trigger a full context mirror.

## Traceability

- A Project Profile entry points to the closest authoritative source.
- An approved issue points only to directly relevant project references.
- A published issue ID is recorded only where the project's planning authority normally records it.
- Requirements, acceptance criteria, and verification use lightweight textual or identifier-based links.

Do not create a large traceability matrix when a short issue already makes the relationships clear.
