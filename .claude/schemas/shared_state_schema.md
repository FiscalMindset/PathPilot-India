# Shared State Schema

## Purpose
Define the canonical runtime memory contract used by all agents during autonomous generation of the PathPilot India application.

## State Versioning
- `state_version`: monotonically increasing integer
- `schema_version`: semantic version for the shared-state contract
- every mutation appends an immutable history entry to `state_journal`
- no agent may rewrite history; repairs create new versions with references to replaced artifact IDs

## Top-Level Shape
```json
{
  "schema_version": "1.0.0",
  "state_version": 0,
  "run_meta": {},
  "prompt_interpretation": {},
  "user_profile": {},
  "market_landscape": {},
  "opportunity_map": {},
  "skill_gap_matrix": {},
  "mentor_network_plan": {},
  "finance_support_plan": {},
  "roadmap_plan": {},
  "wellness_plan": {},
  "entrepreneurship_plan": {},
  "frontend_spec": {},
  "backend_spec": {},
  "observability_spec": {},
  "validation_report": {},
  "repair_history": [],
  "final_synthesis": {},
  "state_journal": []
}
```

## Required `run_meta` Fields
- `run_id`
- `run_label`
- `created_at`
- `last_updated_at`
- `status`
- `active_phase`
- `initial_prompt`
- `prompt_hash`
- `target_runtime_workspace`
- `target_language_preferences`
- `judge_mode_enabled`
- `retry_count`
- `warning_count`

## Artifact Envelope Contract
Every major artifact stored in shared state must use this envelope:
```json
{
  "artifact_id": "string",
  "owner_agent": "string",
  "status": "draft|validated|repaired|rejected",
  "version": 1,
  "confidence": 0.0,
  "summary": "string",
  "inputs": ["artifact_ref"],
  "evidence_refs": ["evidence_ref"],
  "assumptions": ["string"],
  "open_questions": ["string"],
  "updated_at": "ISO-8601",
  "payload": {}
}
```

## Mutation Rules
1. Only the owning agent may author the `payload` for its namespace.
2. The Orchestrator Agent may add lifecycle metadata but may not rewrite domain payloads.
3. The Reviewer Agent may mark an artifact `rejected` or `needs_repair`, but must not rewrite it.
4. Repair outputs must include `supersedes_artifact_id`.
5. Any mutation without `owner_agent`, `updated_at`, `confidence`, and `summary` is invalid.

## Journal Entry Shape
```json
{
  "journal_id": "string",
  "timestamp": "ISO-8601",
  "actor": "agent_id",
  "mutation_type": "create|update|repair|status_change",
  "target_key": "shared_state_key",
  "artifact_id": "string",
  "previous_version": 0,
  "new_version": 1,
  "reason": "string"
}
```

## Minimum Validation
Before the final assembly workflow begins:
- all required artifact namespaces must be present
- all required artifacts must have `summary`, `confidence`, and `payload`
- `validation_report.payload.blocking_findings` must be empty
- `final_synthesis.payload.lineage` must reference upstream artifact IDs
