# Issue Spec Studio

Issue Spec Studio is a reusable, local-first design methodology and context-routing system. It turns a natural-language design discussion into a clear, coding-ready Markdown issue without becoming the home of a target project's ongoing state.

This repository owns the methodology, templates, operating guidance, and artifact contracts. A design session runs inside the target project's repository, where project-specific context and any unfinished design checkpoint remain under that project's authority.

## What Studio provides

- A thin `AGENTS.md` routing pattern that distinguishes design work from implementation work.
- A Project Profile contract for stable project facts and pointers to authoritative sources.
- A minimal active-checkpoint contract for unfinished design discussions.
- Compact and standard issue-authoring guidance, risk overlays, decomposition rules, and a coding-ready gate.
- Consumer-neutral Markdown templates and examples.

## Authority boundaries

- The target repository owns project governance, the Project Profile, and any temporary active checkpoint.
- The target project's existing issue and roadmap system owns published work, status, priority, scheduling, and execution progress.
- Studio never mirrors issues, roadmaps, conversations, or current project state.
- Project governance outranks issue-level instructions; a design issue cannot override repository rules.

## Start here

Agents and maintainers should begin with [START_HERE.md](START_HERE.md). It is a small router to the relevant methodology reference rather than a request to load the entire repository.

See [HANDOFF.md](HANDOFF.md) for the current maturity and next validation work.
