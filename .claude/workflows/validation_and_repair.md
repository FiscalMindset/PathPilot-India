# Workflow: Validation And Repair

## Goal
Apply rigorous review to the assembled architecture and trigger targeted repairs until the quality bar is satisfied.

## Entry Conditions
- specialist artifacts, frontend spec, backend spec, and observability spec exist

## Steps
1. Run the Reviewer Agent using the `validation_skill`.
2. Classify findings as blocking or non-blocking.
3. For each blocking finding, invoke the `retry_repair_skill` with the smallest repair surface.
4. Re-run validation only for impacted artifacts unless the core mission model changed.
5. Record repair history and confidence deltas for trace visibility.

## Exit Criteria
- no blocking findings remain
- repairs are documented and reflected in final synthesis
- the run meets hackathon compliance and observability requirements

## Failure Conditions
- unresolved contradictions remain
- repair loops are invisible or undocumented
