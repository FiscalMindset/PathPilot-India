# Workflow: Prompt Interpretation

## Goal
Convert one high-level prompt into a structured mission model that the entire agent system can execute consistently.

## Entry Conditions
- a new run has started
- the original prompt has not yet been normalized

## Steps
1. Extract explicit product requirements, user outcomes, exclusions, and quality expectations.
2. Identify hidden requirements such as India context, multilingual support, affordability, explainability, and observability.
3. Translate ambiguous language into actionable planning constraints.
4. Generate a structured `prompt_interpretation` artifact with:
   - mission statement
   - target users
   - required app capabilities
   - required observability surfaces
   - non-negotiable constraints
5. Hand the artifact to the Orchestrator Agent for graph planning.

## Exit Criteria
- the prompt has been converted into machine-usable objectives
- no major ambiguity remains untracked
- hackathon constraints are explicitly encoded

## Failure Conditions
- requirements are still free-form prose
- observability or runtime-generation constraints were omitted
