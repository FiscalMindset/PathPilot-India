# Trace Event Schema

## Purpose
Define the event model used by the runtime-generated application to expose the full agentic process in a judge-readable and user-readable way.

## Event Categories
- run lifecycle
- phase lifecycle
- agent lifecycle
- tool activity
- artifact lifecycle
- validation lifecycle
- repair lifecycle
- synthesis lifecycle

## Core Event Shape
```json
{
  "event_id": "string",
  "event_type": "string",
  "run_id": "string",
  "phase_id": "string|null",
  "agent_id": "string|null",
  "parent_event_id": "string|null",
  "timestamp": "ISO-8601",
  "status": "queued|running|success|failure|warning|retrying|fallback",
  "title": "string",
  "summary": "string",
  "input_refs": ["artifact_ref"],
  "output_refs": ["artifact_ref"],
  "evidence_refs": ["evidence_ref"],
  "confidence": 0.0,
  "validation_state": "unreviewed|passed|failed|repaired",
  "metadata": {}
}
```

## Required Event Types
- `run.created`
- `run.started`
- `phase.started`
- `phase.completed`
- `agent.queued`
- `agent.started`
- `agent.progress`
- `agent.completed`
- `agent.failed`
- `tool.called`
- `tool.succeeded`
- `tool.failed`
- `artifact.created`
- `artifact.promoted`
- `validation.started`
- `validation.failed`
- `validation.passed`
- `repair.requested`
- `repair.started`
- `repair.completed`
- `synthesis.started`
- `synthesis.completed`
- `run.completed`

## Confidence Rules
1. Confidence is always attached to the current artifact or step, never to the entire system without explanation.
2. Confidence must fall when evidence quality drops or unresolved contradictions increase.
3. Confidence may rise only when new evidence is added or contradictions are resolved.

## UI Rollups
The frontend must derive these rollups from raw events:
- total runtime
- active phase
- number of agents used
- retry count
- warning count
- failing components
- evidence density
- unresolved assumption count

## Minimum Preservation Rules
- raw events must remain queryable after completion
- event ordering must be stable
- retries must point to the event they supersede
- reviewer comments must be linked to the affected event or artifact
