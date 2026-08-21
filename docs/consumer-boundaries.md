# Consumer Boundaries

## Core output boundary

Studio's responsibility ends with one human-approved standard Markdown issue.

The current discussion AI or a human may publish it to Linear, GitHub, or another platform. Publication capability is not part of the core methodology, and Studio does not retain a synchronized published copy.

## Issue and roadmap authorities

Each target project identifies its existing issue and roadmap authorities in the Project Profile.

- The issue authority owns published issue IDs, content, status, priority, assignment, and execution progress.
- The roadmap authority owns durable goals, sequencing, milestones, schedule, and roadmap status.
- These may be the same system or different systems.
- Studio and project-local working artifacts do not mirror either system.

## GitHub and Linear

GitHub may own the target repository, governance, code, pull requests, CI, review evidence, issues, or roadmap data. Linear may own issues, IDs, projects, cycles, and execution status. The actual authority is project-specific; Studio does not assume one universal platform.

When an issue is published, the platform-specific system owns its ongoing state. Studio does not preallocate IDs or perform background synchronization.

## Coding agents

A coding agent reads:

- The final coding issue from the project's issue authority.
- Target-repository agent instructions and applicable governance.
- Task-specific sources explicitly referenced by the issue.

It does not depend on the active checkpoint, discussion transcript, validation review, or a Studio roadmap.

## ALC and other executors

ALC is one possible downstream consumer.

- Studio does not depend on its code, database, state machine, or interface.
- Executor requirements do not define Studio's canonical model.
- Studio does not manage execution, verification, review, pull requests, merge, or cleanup.
- The issue may instruct an executor to stop and report evidence when the plan is infeasible; enforcement belongs to the executor.
- A substantive change to executing work follows the target project's stop-and-redesign policy.

## Renderers and adapters

The MVP does not include a renderer framework. Standard Markdown is the portable output.

A future thin adapter may provide a consumer-specific presentation only if it:

- Preserves the meaning of Goal, Scope, Requirements, Plan, Acceptance Criteria, and Verification.
- Does not invent missing requirements.
- Does not write consumer runtime state into the core model.
- Keeps the result coding-ready.
- Removes only presentation metadata that is unnecessary for that consumer.

## User-facing skill

A future thin skill may help detect design intent, locate Studio, load the target project's Profile, and guide the workflow. It must not store project state, replace the root router, or split the method into persistent analyze, clarify, and plan state machines.
