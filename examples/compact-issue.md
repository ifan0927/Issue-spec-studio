<!-- issue-spec: v1 -->

# Remove the duplicate login error message

## Goal

Display the existing "Incorrect account or password" message only once when a password is wrong.

## Scope

- Remove the duplicate error presentation produced for one failed login response.
- Preserve the existing error text and visual style.

## Implementation Plan

1. Identify where one failed login response writes to two error-presentation sources.
2. Preserve the standard error path and remove the duplicate write from this flow.
3. Update or add a test at the existing test layer for single-message presentation.

## Agent discretion

- Follow existing frontend conventions for local test names and helper usage.

## Acceptance Criteria

- [ ] A wrong password displays one "Incorrect account or password" message.
- [ ] Successful login behavior is unchanged.
- [ ] Other login failures continue to use the existing error-handling mechanism.

## Verification

- Run the existing login-page tests.
- Add or update a test asserting that one failed response produces one visible error message.

## Execution fallback

If the duplicate messages come from independent error contracts that cannot be changed locally, stop and report evidence instead of redesigning global error handling.
