# Workflow: Frontend Observability Generation

## Goal
Define the full user interface for the runtime-generated application with first-class visibility into agent activity and final guidance.

## Entry Conditions
- roadmap and domain artifacts exist
- observability requirements have been defined

## Steps
1. Run the Frontend Agent to create `frontend_spec`.
2. Run the Observability Agent in parallel or immediate sequence to define trace-driven UI requirements.
3. Reconcile component contracts, event displays, confidence indicators, and breakpoint behavior.
4. Validate that mobile, tablet, laptop, and desktop experiences all preserve agent visibility.

## Exit Criteria
- the UI exposes run-level, agent-level, step-level, and final synthesis views
- responsive behavior is fully specified
- the design clearly communicates explainability and trust

## Failure Conditions
- observability is tucked behind hidden panels
- the interface collapses into a standard chat screen
