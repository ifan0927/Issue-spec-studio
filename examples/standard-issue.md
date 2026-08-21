<!-- issue-spec: v1 -->

> Stateless fictional example. It demonstrates the standard issue contract and does not describe active project work.

# Add an administrative user-suspension API

## Goal

Allow an authorized administrator to suspend a user, invalidate that user's existing sessions, and leave an audit record of the operation.

## Context

The system can prevent new login attempts but has no single administrative operation that updates user state, revokes existing sessions, and records the actor. This issue adds backend behavior only; an administrative UI is outside scope.

## Scope

- Add a suspension endpoint following existing administrative API conventions.
- Change the target user's state to `suspended`.
- Invalidate the target user's existing sessions.
- Record actor, target, timestamp, and action result.
- Add authorization, domain, API, session-invalidation, and audit tests.

## Out of scope

- Administrative UI.
- Automatic notification to the suspended user.
- User-data deletion or anonymization.
- A new global session infrastructure.

## Requirements

- Only an actor accepted by the existing administrative authorization policy can perform the operation.
- Results for a missing or already-suspended user follow existing API error and idempotency conventions.
- Before reporting success, user-state persistence and session invalidation meet the project's existing consistency requirement.
- Successful and rejected sensitive operations create the records required by the existing audit policy.

## Applicable project references

- `<project-profile: admin-api>`: Administrative endpoint and authorization conventions.
- `<project-profile: error-handling>`: Public error mapping.
- `<project-profile: session-management>`: Session-revocation method.
- `<project-profile: audit>`: Sensitive-operation recording requirements.
- `<project-profile: verification>`: Backend test commands.

## Implementation Plan

1. Add the suspension operation at the existing administrative API boundary and reuse its authorization middleware.
2. Validate the state transition and persist `suspended` through the existing user domain or service boundary.
3. Revoke active sessions through the existing session-revocation abstraction; do not create a parallel mechanism.
4. Record actor, target, result, and required request context according to audit policy.
5. Return missing, unauthorized, and invalid-state results through the existing public error mapping.
6. Add coverage at the domain, authorization, endpoint, session-revocation, and audit boundaries.

## Agent discretion

- Follow existing module conventions for local handler, service-method, and fixture names.
- Choose the test-data setup without changing an existing public contract.

## Acceptance Criteria

- [ ] An authorized administrative request changes an active user to `suspended`.
- [ ] Existing active sessions for that user no longer authenticate after suspension succeeds.
- [ ] A non-administrator cannot suspend a user, and user state and sessions remain unchanged.
- [ ] Missing and already-suspended users follow existing error and idempotency conventions.
- [ ] Audit policy records actor, target, timestamp, and result.
- [ ] Suspension does not delete the user's domain data.

## Verification

- Run backend test and lint commands referenced by the Project Profile.
- Domain tests cover allowed and rejected state transitions.
- Authorization tests cover administrative and non-administrative callers.
- An integration test proves an existing session is rejected after successful suspension.
- Audit tests cover successful and rejected paths.

## Risks and safeguards

- If session invalidation and state persistence cannot meet the project consistency rule, do not degrade to eventual best effort; stop and report the required architecture decision.
- Audit records must not contain credentials, tokens, or other sensitive data prohibited by policy.

## Issue-specific Definition of Done

- Endpoint, session-invalidation, and audit evidence are traceable in the same verification results.

## Execution fallback

If the existing session abstraction cannot revoke sessions by user, stop, provide repository evidence, and report the need for a prerequisite issue. Do not design a new session architecture inside this issue.
