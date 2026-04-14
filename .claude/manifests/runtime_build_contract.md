# Runtime Build Contract

## Purpose
Specify exactly what the orchestrator must hand to the code-generation stage when assembling the final application outside the blueprint repository.

## Build Manifest Fields
- `build_id`
- `run_id`
- `blueprint_version`
- `target_workspace`
- `frontend_generation_scope`
- `backend_generation_scope`
- `observability_generation_scope`
- `data_model_scope`
- `seed_configuration_scope`
- `test_generation_scope`
- `acceptance_checks`

## Required Generation Scope

### Frontend Scope
- application shell
- onboarding flow
- dashboard and recommendation views
- trace and agent timeline panels
- roadmap interfaces
- mentor, finance, entrepreneurship, and wellness views
- responsive layouts
- loading, retry, warning, and error states

### Backend Scope
- orchestration runtime
- APIs
- streaming layer
- persistence layer
- validation loop support
- artifact lineage storage

### Observability Scope
- event taxonomy implementation
- trace persistence
- metrics aggregation
- trust indicator calculation
- final synthesis provenance rendering support

### Testing Scope
- smoke tests for run creation
- basic trace visibility checks
- frontend responsiveness checks
- synthesis lineage checks

## Assembly Rules
1. The build manifest may describe the code to be generated but may not embed the full code inside the blueprint repository.
2. The generation stage must use approved artifacts only.
3. Any divergence from `frontend_spec`, `backend_spec`, or `observability_spec` requires a repair or reviewer approval.
4. The final application must include visible proof of multi-agent execution.
