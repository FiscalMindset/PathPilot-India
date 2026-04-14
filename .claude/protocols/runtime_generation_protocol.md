# Runtime Generation Protocol

## Purpose
Turn approved blueprint artifacts into a real generated application without leaking implementation into the submission repository.

## Principle
Blueprint here, product there.

The system must:
- keep this repository instruction-only
- emit a build manifest at runtime
- generate the app in a separate target workspace
- preserve lineage from approved artifacts to generated output

## Runtime Generation Stages
1. Build scope resolution
2. File-plan synthesis
3. Frontend code generation
4. Backend code generation
5. Observability layer generation
6. Test and smoke-check generation
7. Final validation against the generated app contract

## Required Inputs
- approved `frontend_spec`
- approved `backend_spec`
- approved `observability_spec`
- approved `final_synthesis`
- runtime build manifest
- target workspace path

## Required Outputs
- application source tree in external workspace
- build manifest snapshot
- generation report
- validation snapshot

## Generation Constraints
- no generated file may be written into this repository
- all generated modules must map back to approved artifact scopes
- if the generated output drifts from validated specs, trigger review or repair

## Required Runtime Metadata
- `build_id`
- `run_id`
- `blueprint_version`
- `generated_at`
- `target_workspace`
- `source_artifact_refs`
