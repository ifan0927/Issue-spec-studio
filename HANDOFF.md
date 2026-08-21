# Handoff

## Current state

This repository contains the approved Issue Spec Studio design baseline. It stores reusable methodology, templates, operating guidance, and artifact contracts only. It contains no target-project Profile, checkpoint, issue draft, roadmap copy, or other current project state.

The repository has not entered product implementation. It has no production CLI, service, database, renderer, skill, or platform-publishing integration.

## Confirmed product shape

- A single-user, local-first design methodology and context-routing system.
- Design sessions run in target repositories.
- A target repository's thin root `AGENTS.md` routes implementation intent to project instructions and design intent to Studio.
- The target repository owns its governance, Project Profile, and any temporary active checkpoint.
- Markdown is the canonical human-readable issue output.
- The Profile maps stable facts and authoritative references without copying their contents.
- An active checkpoint preserves only unresolved state needed to resume one unfinished design discussion.
- Published issues and roadmaps remain in the target project's existing authorities.
- ALC is one downstream consumer and does not shape the core model.
- Small deterministic checks may be added after repeated evidence, but no product CLI is assumed.

## Recommended next validation session

Continue with design validation before building a complete tool:

1. Apply the router and Profile templates to a real target repository using its existing layout.
2. Walk through a compact change, standard feature, large-request decomposition, and high-risk change.
3. Test whether a new discussion can resume from only the minimal active checkpoint.
4. Confirm that publication and cleanup leave no issue or roadmap mirror behind.
5. Record only repeated specification-quality failures, then revise guidance or templates.
6. Decide which deterministic checks are justified after the MVP acceptance scenarios pass.

## Handoff constraints

- Do not turn durable Studio documents into a discussion log.
- Do not store target-project state in this repository.
- Do not create a second issue, roadmap, dashboard, or execution authority.
- Do not add a framework for hypothetical edge cases.
- Do not bring the ALC execution lifecycle into the product.
- Do not let the root router or Project Profile become a copied knowledge base.

## Pending validation

- Validate project-native onboarding against a real repository.
- Test compact and standard issue templates with real requests.
- Verify that decomposition stays bounded and publishes into an existing planning authority.
- Verify checkpoint creation, compaction, removal, and exceptional archival policy.
- Gather evidence for or against deterministic validation scripts.
