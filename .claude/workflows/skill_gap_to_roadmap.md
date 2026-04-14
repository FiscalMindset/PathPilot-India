# Workflow: Skill Gap To Roadmap

## Goal
Convert identified opportunity paths into a prioritized learning and execution plan.

## Entry Conditions
- `opportunity_map` exists
- `user_profile` exists

## Steps
1. Run the Skill-Gap Analysis Agent to produce `skill_gap_matrix` and `learning_priorities`.
2. Run the Wellness Agent on the draft pacing assumptions when needed.
3. Run the Roadmap Planner Agent to convert gaps into milestones.
4. Ensure every milestone links back to a skill, opportunity, finance, or support rationale.
5. Send the roadmap to the Reviewer Agent.

## Exit Criteria
- the roadmap is sequenced and realistic
- dependencies and alternatives are explicit
- pacing respects the user’s likely bandwidth

## Failure Conditions
- roadmap steps are generic or unsequenced
- milestone order cannot be explained
