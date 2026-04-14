# Handoff Packet Protocol

## Purpose
Standardize how agents transfer work products so the system demonstrates strong coordination rather than ad hoc prompt chaining.

## Required Packet Fields
- `handoff_id`
- `from_agent`
- `to_agent`
- `phase_id`
- `artifact_refs`
- `input_summary`
- `critical_constraints`
- `assumptions`
- `open_questions`
- `confidence`
- `expected_output`
- `return_condition`

## Packet Assembly Rules
1. The upstream agent must summarize the artifact in language a downstream specialist can act on immediately.
2. Constraints that materially affect feasibility must be listed separately from general context.
3. Assumptions must never be buried inside the summary.
4. Confidence must reflect the current artifact quality, not optimism about the next agent.
5. The packet must include the exact output expected from the downstream agent.

## Example Use
- Self-Discovery Agent -> Market & Opportunities Agent:
  - user motivations
  - hard constraints
  - location and language assumptions
  - confidence in profile completeness

- Market & Opportunities Agent -> Skill-Gap Analysis Agent:
  - shortlisted paths
  - pathway rationale
  - evidence references
  - rejected alternatives

## Reviewer Use
The Reviewer Agent must inspect handoff quality when judging coordination depth.

## Anti-Patterns
- sending raw upstream text without summarization
- omitting assumptions
- sending work to a downstream agent with no declared expected output
- overwriting a prior handoff with no trace record
