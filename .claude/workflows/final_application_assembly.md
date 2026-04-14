# Workflow: Final Application Assembly

## Goal
Generate the actual PathPilot India application at runtime in a target workspace outside the blueprint repository, using the approved architecture, trace model, and domain artifacts.

## Entry Conditions
- Reviewer Agent has approved the plan
- `frontend_spec`, `backend_spec`, `observability_spec`, and `final_synthesis` exist

## Steps
1. Freeze the approved shared state snapshot and record the version used for generation.
2. Emit a `build_manifest` that lists application modules, services, screens, data models, trace surfaces, and acceptance checks to be created.
3. Partition generation work into:
   - frontend generation scope
   - backend generation scope
   - observability generation scope
   - testing generation scope
4. Generate the full application code in the runtime target, not in this blueprint repository.
5. Preserve provenance by embedding trace-aware schemas, event models, visible handoff UX, and final synthesis lineage into the generated app.
6. Run acceptance checks against the generated application contract.
7. Validate the produced app against `.claude/generation/runtime_acceptance_matrix.md`.
8. Validate that the produced app reflects the approved artifacts rather than ad hoc drift.
9. Reject the build if the generated application summary indicates placeholder-heavy implementation or minimal-stack downgrade.

## Exit Criteria
- runtime application includes required user features
- frontend observability matches policy requirements
- backend supports orchestration, trace capture, and recommendation delivery
- build output is consistent with approved blueprint artifacts
- generated app includes visible multi-agent execution proof
- build manifest is stored with run ID and blueprint version reference

## Failure Conditions
- code generation occurs inside the blueprint repository
- the final app omits agent visibility, retries, or synthesis explainability
- generated build diverges from validated specs without repair approval
