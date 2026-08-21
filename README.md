# Issue Spec Studio

Issue Spec Studio is a reusable, local-first design methodology and artifact-contract repository. It turns a natural-language design discussion into a clear, coding-ready Markdown issue without becoming the home of a target project's ongoing state.

This repository owns the methodology, templates, operating guidance, and artifact contracts. A design session runs inside the target project's repository, where project-specific context and any unfinished design checkpoint remain under that project's authority.

## What Studio provides

- A thin `AGENTS.md` routing pattern that distinguishes design work from implementation work.
- A Project Profile contract for stable project facts and pointers to authoritative sources.
- A minimal active-checkpoint contract for unfinished design discussions.
- Compact and standard issue-authoring guidance, risk overlays, decomposition rules, and a coding-ready gate.
- Consumer-neutral Markdown templates and examples.

## Project-native operating model

```text
Target project
    |
    v
Root AGENTS.md detects request intent
    |
    +-- Design request --> load Project Profile, Studio methodology,
    |                     relevant project authorities, and active checkpoint if present
    |
    +-- Implementation request --> load the implementation-ready issue
                                  and relevant project authorities
```

A design session starts and remains in the target repository. Studio supplies the method and reusable templates; it never asks a user to enter Studio, select a workspace, register a project, or create project state here.

An adopting target repository uses these default locations:

```text
<project-root>/
|-- AGENTS.md
`-- .issue-spec/
    |-- project-profile.md
    `-- active.md             # optional; exists only during unresolved design work
```

A target repository may override either `.issue-spec/` artifact path only when an established repository convention requires it, and the override must be explicit in the root `AGENTS.md`. Agents never search heuristically for an alternative. If no override is declared, the canonical paths apply. A missing `.issue-spec/active.md` means that no active design checkpoint exists.

## Authority boundaries

- The target repository owns project governance, the Project Profile, and any temporary active checkpoint.
- The target project's existing issue and roadmap system owns published work, status, priority, scheduling, and execution progress.
- Studio never mirrors issues, roadmaps, conversations, or current project state.
- Studio never stores live Project Profile instances or active checkpoints.
- Project governance outranks issue-level instructions; a design issue cannot override repository rules.

## Start here

Agents and maintainers should begin with [START_HERE.md](START_HERE.md). It is a small router to the relevant methodology reference rather than a request to load the entire repository.

See [HANDOFF.md](HANDOFF.md) for the current maturity and next validation work.
