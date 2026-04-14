# Workflow: Backend Architecture Generation

## Goal
Define the service architecture, data models, orchestration runtime, and APIs required to power the generated frontend and multi-agent system.

## Entry Conditions
- execution plan exists
- frontend and observability requirements are available

## Steps
1. Run the Backend Agent to define the service map and APIs.
2. Ensure state models support runs, agents, steps, evidence, validations, and repairs.
3. Align streaming and retrieval endpoints with the frontend trace experience.
4. Confirm the backend can produce the final synthesis lineage demanded by the observability policy.

## Exit Criteria
- APIs are sufficient for both live execution and replay
- storage models preserve lineage and traceability
- repair loops are supported in architecture

## Failure Conditions
- backend cannot explain final outputs
- agent state or trace events are not persistable
