# Workflow: Mentor And Finance Matching

## Goal
Pair the user’s pathway with support systems that improve access, accountability, and affordability.

## Entry Conditions
- `user_profile` exists
- `opportunity_map` exists

## Steps
1. Run the Mentor & Network Agent to build the `mentor_network_plan`.
2. Run the Financial & Scholarship Agent to build the `finance_support_plan`.
3. Cross-check the two outputs for timing dependencies, such as references, applications, or community access.
4. Package both artifacts for the Roadmap Planner and Reviewer Agents.

## Exit Criteria
- the user has both network and affordability support options
- recommendations are path-specific and actionable
- dependencies are visible for later roadmap assembly

## Failure Conditions
- support outputs are generic advice with no concrete next steps
- costs are identified without mitigation paths
