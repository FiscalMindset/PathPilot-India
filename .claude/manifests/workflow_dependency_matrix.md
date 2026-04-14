# Workflow Dependency Matrix

## Purpose
Make the execution graph explicit so the blueprint reads like an autonomous system rather than a loose collection of roles.

## Phase Graph

### Phase 0: Bootstrap
- Input: initial prompt
- Output: run metadata, policy load, workflow registry load
- Mandatory next phase: Mission Framing

### Phase 1: Mission Framing
- Workflow: `prompt_interpretation`
- Primary owner: Orchestrator Agent
- Output: `prompt_interpretation`, initial `execution_plan`
- Gate: no critical ambiguity left untracked

### Phase 2: User Grounding
- Workflow: `user_profile_generation`
- Primary owner: Self-Discovery Agent
- Output: `user_profile`
- Gate: constraints and assumptions captured

### Phase 3A: Opportunity Research
- Workflow: `market_mapping`
- Primary owner: Market & Opportunities Agent
- Output: `market_landscape`, `opportunity_map`
- Parallel safety: may overlap with Phase 3B and 3C only after `user_profile`

### Phase 3B: Support Matching
- Workflow: `mentor_finance_matching`
- Primary owners: Mentor & Network Agent, Financial & Scholarship Agent
- Output: `mentor_network_plan`, `finance_support_plan`
- Parallel safety: can run alongside Phase 3A and 3D

### Phase 3C: Gap Modeling
- Workflow: `skill_gap_to_roadmap` step 1
- Primary owner: Skill-Gap Analysis Agent
- Output: `skill_gap_matrix`
- Parallel safety: can run after `opportunity_map` exists

### Phase 3D: Entrepreneurship Branch
- Workflow: `entrepreneurship_path`
- Primary owner: Entrepreneurship Agent
- Activation: only when the prompt or `user_profile` supports it
- Output: `entrepreneurship_plan`

### Phase 4: Planning Synthesis
- Workflow: `skill_gap_to_roadmap` completion
- Primary owners: Wellness Agent, Roadmap Planner Agent
- Output: `wellness_plan`, `roadmap_plan`
- Gate: roadmap is realistic, explainable, and sustainable

### Phase 5A: Experience Architecture
- Workflow: `frontend_observability_generation`
- Primary owners: Frontend Agent, Observability Agent
- Output: `frontend_spec`, UI observability model

### Phase 5B: Runtime Architecture
- Workflow: `backend_architecture_generation`
- Primary owners: Backend Agent, Observability Agent
- Output: `backend_spec`, backend event and lineage model

### Phase 6: Review And Repair
- Workflow: `validation_and_repair`
- Primary owner: Reviewer Agent
- Output: `validation_report`, `repair_history`
- Loop condition: any blocking finding

### Phase 7: Final Assembly
- Workflow: `final_application_assembly`
- Primary owner: Orchestrator Agent
- Output: runtime application build manifest and generation directives
- Gate: approval decision equals `approved`

## Parallel Execution Rules
- Parallelism is allowed only when target artifact ownership is disjoint.
- Frontend, backend, and observability may iterate in tandem after interface and event handshake is established.
- Reviewer may inspect partial outputs at phase boundaries, but may not close the run until phase 6.

## Kill Switch Conditions
- generated code appears inside blueprint repository
- reviewer finds hidden hardcoding
- observability surfaces are missing from the generated app spec
- single-agent fallback replaces required multi-agent flow
