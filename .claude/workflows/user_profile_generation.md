# Workflow: User Profile Generation

## Goal
Create a structured user profile that downstream agents can use as the source of truth for personalization.

## Entry Conditions
- `prompt_interpretation` exists
- the Self-Discovery Agent is queued

## Steps
1. Read the original prompt and identify user signals.
2. Extract interests, strengths, motivations, barriers, access constraints, and possible ambitions.
3. Mark hard facts versus inferred assumptions.
4. Generate the `user_profile` artifact and `uncertainty_flags`.
5. Send both artifacts to dependent agents and the Reviewer Agent.

## Exit Criteria
- the user profile is structured and reusable
- uncertainty is visible instead of hidden
- downstream agents can consume profile data without reinterpretation

## Failure Conditions
- profile lacks constraints or support needs
- assumptions are mixed with confirmed facts without labels
