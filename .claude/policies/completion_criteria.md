# Completion Criteria

## Purpose
Define the minimum standard for declaring the blueprint-driven generation run complete.

## Required Conditions
- the original prompt has been interpreted into a structured mission model
- all required agents have run or been explicitly skipped with justification
- observability requirements are fully specified and user-visible
- frontend and backend architectures are coherent and aligned
- validation has passed with no blocking findings
- repair history is recorded
- final synthesis is traceable to evidence and artifacts
- no generated product code exists inside this blueprint repository
- a runtime build manifest can be emitted without missing scopes
- shared state satisfies the schema and artifact contract rules
- the generated app contract is satisfied in architecture scope

## The Generated Application Must Be Able To Deliver
- multilingual onboarding
- self-discovery and aptitude mapping
- career path guidance
- market and opportunity analysis
- skill-gap analysis
- mentor and community recommendations
- scholarship, grant, or affordability discovery
- roadmap planning
- optional entrepreneurship pathway
- wellness-aware pacing
- observability-first execution visibility

## Failure To Complete
If any required capability, validation gate, or observability surface is missing, the run is incomplete.

## Minimum Evidence Of Completion
- reviewer approval decision equals `approved`
- `validation_report.payload.blocking_findings` is empty
- `frontend_spec`, `backend_spec`, and `observability_spec` reference each other consistently
- `final_synthesis` references validated upstream artifact IDs
- runtime generation is directed to an external target workspace
