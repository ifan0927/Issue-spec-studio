# Canonical Information Model

## Model shape

Studio defines a small set of Markdown contracts connected by references. It does not maintain a parallel human/machine schema and does not host project instances of those artifacts.

```text
Studio methodology and templates
              |
              | applied inside
              v
Target repository root router (AGENTS.md)
       | implementation intent         | design intent
       v                               v
Project engineering authority     Project Profile
                                          |
                                          v
                         optional active checkpoint
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

## Required semantics and optional paths

The responsibilities above are required. Their paths are not universal.

After examining an existing repository's conventions, a project may choose locations such as:

```text
AGENTS.md
docs/project-profile.md
work/design/active.md
```

These are recommendations, not required directories. A repository may place the Profile beside existing governance, keep a local-only checkpoint in an ignored directory, or use another established convention. References and router instructions must use the actual chosen paths.

## Artifact responsibilities

### Project Profile

The Project Profile records stable project identity, durable facts that are not already better owned elsewhere, and pointers with load triggers to canonical sources. It may point to commands or planning authorities but must not copy their contents.

### Active checkpoint

The active checkpoint exists only when an unfinished discussion must survive a context boundary. It contains:

- Current objective.
- Confirmed decisions still needed to resume this discussion.
- Active assumptions.
- Blocking questions.
- Current decomposition.
- Next discussion focus.

It is working-only, continuously rewritten, and removed when no unresolved resumable state remains.

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
