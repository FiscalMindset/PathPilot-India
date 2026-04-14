# Retry & Repair Skill

## Purpose
Provide a controlled mechanism for rerunning weak or failed portions of the workflow without destabilizing the rest of the run.

## Use When
- validation fails
- a source is stale or low-confidence
- an agent output is contradictory or incomplete
- a downstream dependency is blocked by poor upstream data

## Inputs
- repair request
- failing artifact IDs
- latest shared state snapshot

## Outputs
- repair scope
- targeted rerun plan
- change summary
- updated confidence delta

## Method
1. Determine the smallest repair surface that can fix the issue.
2. Reuse valid artifacts rather than discarding the whole run.
3. Compare pre-repair and post-repair outputs explicitly.
4. Log what changed, why, and whether confidence improved.
5. Escalate to full re-planning only when structural assumptions are broken.

## Quality Bar
- Repairs must be visible in the trace and timeline.
- Confidence cannot increase unless the repair adds real evidence or removes contradiction.
- The final synthesis must reflect repaired artifacts, not stale ones.
