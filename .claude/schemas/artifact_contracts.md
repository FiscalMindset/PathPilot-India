# Artifact Contracts

## Purpose
Define the exact outputs each agent must produce, who consumes them, and what quality checks apply before handoff.

## Contract Format
Each artifact contract includes:
- owner
- required inputs
- required fields
- downstream consumers
- validation checks

## `prompt_interpretation`
- Owner: Orchestrator Agent through the prompt interpretation workflow
- Required inputs: initial prompt, hackathon constraints, policies
- Required fields:
  - mission statement
  - explicit requirements
  - implicit requirements
  - exclusions
  - target user segments
  - success criteria
  - observability obligations
  - runtime-generation constraint
- Downstream consumers: all agents
- Validation checks:
  - captures all requested capabilities
  - contains no missing critical constraint

## `user_profile`
- Owner: Self-Discovery Agent
- Required inputs: `prompt_interpretation`
- Required fields:
  - motivations
  - strengths
  - constraints
  - geography assumptions
  - language comfort
  - finance sensitivity
  - preferred path modes
  - support needs
- Downstream consumers: market, skill, mentor, finance, roadmap, wellness, entrepreneurship
- Validation checks:
  - clearly separates assumptions from facts
  - includes barriers, not just ambitions

## `opportunity_map`
- Owner: Market & Opportunities Agent
- Required inputs: `user_profile`
- Required fields:
  - shortlisted paths
  - fit rationale
  - India relevance
  - accessibility notes
  - evidence references
  - rejected alternatives
- Downstream consumers: skill, mentor, finance, roadmap, entrepreneurship, reviewer
- Validation checks:
  - each path has evidence
  - at least one near-term feasible path exists

## `skill_gap_matrix`
- Owner: Skill-Gap Analysis Agent
- Required inputs: `user_profile`, `opportunity_map`
- Required fields:
  - target competencies
  - matched strengths
  - gaps
  - priority order
  - low-cost learning options
  - proof-of-work requirements
- Downstream consumers: roadmap, reviewer
- Validation checks:
  - dependencies are ordered
  - timelines are plausible

## `mentor_network_plan`
- Owner: Mentor & Network Agent
- Required inputs: `user_profile`, `opportunity_map`, `skill_gap_matrix`
- Required fields:
  - mentor archetypes
  - community recommendations
  - outreach steps
  - networking milestones
  - access barriers
- Downstream consumers: roadmap, wellness, reviewer
- Validation checks:
  - does not invent people
  - includes accessible alternatives

## `finance_support_plan`
- Owner: Financial & Scholarship Agent
- Required inputs: `user_profile`, `opportunity_map`, `skill_gap_matrix`
- Required fields:
  - cost categories
  - funding options
  - eligibility notes
  - application timing
  - fallback low-cost path
- Downstream consumers: roadmap, entrepreneurship, reviewer
- Validation checks:
  - verified versus inferred support is clearly separated
  - no fabricated deadlines or amounts

## `roadmap_plan`
- Owner: Roadmap Planner Agent
- Required inputs: `user_profile`, `opportunity_map`, `skill_gap_matrix`, `mentor_network_plan`, `finance_support_plan`, `wellness_plan`, `entrepreneurship_plan`
- Required fields:
  - next 7 days
  - next 30 days
  - next 60 days
  - next 90 days
  - 6 to 12 month view
  - milestone rationale
  - contingency branches
- Downstream consumers: frontend, observability, reviewer, final synthesis
- Validation checks:
  - milestones are sequenced
  - roadmap is sustainable

## `wellness_plan`
- Owner: Wellness & Resilience Agent
- Required inputs: `user_profile`, `skill_gap_matrix`, draft `roadmap_plan`
- Required fields:
  - burnout risks
  - pacing adjustments
  - check-in rhythm
  - recovery buffers
  - support escalation cues
- Downstream consumers: roadmap, frontend, reviewer
- Validation checks:
  - supportive but non-clinical
  - materially changes pacing where needed

## `entrepreneurship_plan`
- Owner: Entrepreneurship Agent
- Required inputs: `user_profile`, `opportunity_map`, `finance_support_plan`
- Required fields:
  - activation reason
  - venture hypotheses
  - validation actions
  - support ecosystem map
  - first revenue or proof milestones
- Downstream consumers: roadmap, frontend, backend, reviewer
- Validation checks:
  - entrepreneurship is justified
  - path is lean and accessible

## `frontend_spec`
- Owner: Frontend Agent
- Required inputs: all user-facing domain artifacts and `observability_spec`
- Required fields:
  - screen map
  - component map
  - breakpoint rules
  - trace surfaces
  - data-binding requirements
  - streaming-state UX
- Downstream consumers: backend, final assembly, reviewer
- Validation checks:
  - not chat-only
  - observability is visible at every breakpoint

## `backend_spec`
- Owner: Backend Agent
- Required inputs: `execution_plan`, `frontend_spec`, `observability_spec`
- Required fields:
  - service map
  - APIs
  - orchestration runtime
  - persistence model
  - streaming model
  - lineage model
- Downstream consumers: frontend, observability, final assembly, reviewer
- Validation checks:
  - supports replay and live execution
  - models retries and validations

## `observability_spec`
- Owner: Observability Agent
- Required inputs: `execution_plan`, `frontend_spec`, `backend_spec`
- Required fields:
  - event taxonomy
  - trace entity schema
  - trust indicators
  - retry and fallback display rules
  - final synthesis lineage rules
- Downstream consumers: frontend, backend, reviewer, final assembly
- Validation checks:
  - covers run, agent, step, evidence, validation, and repair visibility

## `validation_report`
- Owner: Reviewer Agent
- Required inputs: all major artifacts
- Required fields:
  - blocking findings
  - non-blocking findings
  - artifact-by-artifact status
  - repair requests
  - approval decision
- Downstream consumers: orchestrator, final assembly
- Validation checks:
  - every blocking issue names a target artifact and acceptance rule

## `final_synthesis`
- Owner: Orchestrator Agent with synthesis skill
- Required inputs: validated upstream artifacts
- Required fields:
  - recommendation narrative
  - roadmap rationale
  - evidence lineage
  - assumption list
  - alternative paths
  - why-chosen explanations
- Downstream consumers: final assembly, frontend
- Validation checks:
  - traceable to validated artifacts only
