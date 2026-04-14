# Judge Alignment Policy

## Purpose
Bias blueprint decisions toward the four published scoring dimensions without sacrificing rule compliance.

## Prompt Interpretation: 25%
To score well:
- convert the initial prompt into structured requirements and constraints
- show how ambiguity is resolved
- keep user intent visible through every phase

System requirement:
- `prompt_interpretation` must be rich enough for a judge to see the mapping from prompt to plan.

## Agent Coordination: 25%
To score well:
- define clear role separation
- make handoffs explicit
- show conflict resolution and repair loops

System requirement:
- every major artifact must name its owner, inputs, and downstream consumers.

## Architecture Quality: 25%
To score well:
- produce modular frontend, backend, state, and observability architecture
- make scalability and maintainability visible
- align data flow with UX and traceability

System requirement:
- frontend, backend, observability, and shared-state schemas must fit together cleanly.

## Automation Depth: 25%
To score well:
- automate planning, research, architecture, synthesis, validation, and repair
- avoid hidden manual curation
- prove the application emerges from the workflow

System requirement:
- final assembly must consume validated artifacts and generate the app in a separate runtime workspace.

## Design Biases
- prefer explicit contracts over inspirational prose
- prefer repairable systems over brittle one-shot flows
- prefer judge-visible traceability over silent sophistication
