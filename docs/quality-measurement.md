# Quality Measurement

## Objective

Measure whether a specification reduces uncertainty and rework during implementation, not whether a template is full, long, or aesthetically complete.

## Measurement policy

Use an exception-driven, low-maintenance approach. Successful issues need no detailed Studio record. Record a lightweight quality event in the target project's existing issue or quality system only when a specification causes a downstream failure.

## Quality event triggers

- A coding agent stops because the requirement is ambiguous.
- Execution reveals a project-rule conflict.
- The Implementation Plan is infeasible in the current repository.
- Missing scope causes material expansion or a replacement issue.
- Acceptance cannot determine completion.
- Verification cannot run or produce the needed evidence.
- An oversized issue requires late splitting, cancellation, or significant rework.
- A missing risk overlay causes a migration, compatibility, security, deployment, or rollback problem.
- Studio or a checkpoint has drifted into a duplicate issue or roadmap authority.

## Minimal event information

- Affected published issue reference.
- Failure category.
- Discovery phase.
- Whether execution was blocked.
- Whether clarification, replacement, redesign, or a project-policy update was needed.
- One-sentence root-cause summary.

The project may record this in an issue comment, label, or existing quality system. Studio defines the information but does not own a telemetry database.

## Useful measures

- Share of completed standardized issues requiring material clarification after execution starts.
- Share stopped or reopened because of a specification defect.
- Share split or cancelled because they were too large.
- Rate of acceptance or verification defects.
- Rate of project-governance conflicts.
- Human effort from discussion to approval.
- Rate of checkpoint cleanup failures or authority duplication.

## Anti-metrics

Do not use section count, word count, template completion, model self-score, question count, or issue count as quality proxies.

## Improvement rule

Change Studio guidance, templates, or deterministic checks only for repeated failures that the method can prevent. A one-time edge case does not automatically justify more process or schema.
