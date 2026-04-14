# Repair Loop Protocol

## Purpose
Ensure quality issues are resolved through controlled, transparent, minimal-scope repairs rather than vague reruns.

## Repair Trigger Types
- missing evidence
- contradictory artifacts
- unrealistic roadmap sequencing
- unsupported finance assumptions
- weak observability coverage
- frontend/backend mismatch
- hidden hardcoding risk

## Repair Packet Fields
- `repair_id`
- `initiated_by`
- `target_artifact`
- `severity`
- `blocking`
- `problem_summary`
- `acceptance_rule`
- `allowed_repair_scope`
- `superseded_artifact_refs`

## Repair Process
1. The Reviewer Agent creates a repair request with a precise acceptance rule.
2. The Orchestrator Agent identifies the smallest responsible repair surface.
3. The responsible agent reruns only the affected output.
4. The system compares before and after artifacts.
5. Confidence is recalculated.
6. Reviewer validation is re-run on the repaired artifact and any dependents.

## Repair Escalation Rules
- Local repair: use when one artifact is weak but upstream interpretation remains valid.
- Phase repair: use when multiple artifacts in one phase depend on the same bad assumption.
- Full re-plan: use only when `prompt_interpretation` is materially wrong.
- Hard stop: use when repo compliance or no-hardcoding rules are violated.

## Required Visibility
The generated app must expose:
- why the repair happened
- which artifact changed
- what improved
- whether confidence increased

## Anti-Patterns
- full reruns with no root cause stated
- silent artifact replacement
- reviewer findings with no acceptance criteria
