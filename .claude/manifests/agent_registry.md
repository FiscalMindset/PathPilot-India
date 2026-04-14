# Agent Registry Manifest

## Purpose
Provide a single operational registry for orchestration, showing ownership, dependencies, concurrency safety, and validation gates for every agent.

## Registry

### `orchestrator`
- Role: global controller
- Owns: `execution_plan`, state initialization, dispatch manifest, final synthesis
- Depends on: initial prompt, all policies, all manifests, all workflows
- Runs: first and last
- Validation gate: reviewer approval required before final assembly

### `self_discovery`
- Role: user profile modeling
- Owns: `user_profile`
- Depends on: `prompt_interpretation`
- Can run in parallel with: none
- Blocks: market, mentor, finance, skill, roadmap, wellness, entrepreneurship
- Validation gate: profile completeness and assumption labeling

### `market_opportunities`
- Role: external opportunity mapping
- Owns: `market_landscape`, `opportunity_map`
- Depends on: `user_profile`
- Can run in parallel with: mentor, finance
- Blocks: skill, roadmap, entrepreneurship
- Validation gate: evidence coverage and India relevance

### `skill_gap`
- Role: readiness and learning delta analysis
- Owns: `skill_gap_matrix`
- Depends on: `user_profile`, `opportunity_map`
- Can run in parallel with: mentor, finance, entrepreneurship
- Blocks: roadmap
- Validation gate: dependency ordering and feasibility

### `mentor_network`
- Role: social capital and guidance planning
- Owns: `mentor_network_plan`
- Depends on: `user_profile`, `opportunity_map`
- Can run in parallel with: finance, skill_gap
- Blocks: roadmap
- Validation gate: no fabricated people or inaccessible-only paths

### `finance_scholarship`
- Role: affordability and support planning
- Owns: `finance_support_plan`
- Depends on: `user_profile`, `opportunity_map`
- Can run in parallel with: mentor, skill_gap
- Blocks: roadmap, entrepreneurship
- Validation gate: verified and inferred funding paths clearly separated

### `wellness`
- Role: resilience and pacing adaptation
- Owns: `wellness_plan`
- Depends on: `user_profile`, `skill_gap_matrix`, draft `roadmap_plan`
- Can run in parallel with: none in final form; may review draft roadmap iteratively
- Blocks: roadmap finalization
- Validation gate: materially influences pacing when needed

### `entrepreneurship`
- Role: founder-path branch generation
- Owns: `entrepreneurship_plan`
- Depends on: `user_profile`, `opportunity_map`, `finance_support_plan`
- Can run in parallel with: skill_gap once activation condition is met
- Blocks: roadmap only when entrepreneurship is in-scope
- Validation gate: activation justification plus lean validation steps

### `roadmap_planner`
- Role: milestone synthesis
- Owns: `roadmap_plan`
- Depends on: `user_profile`, `opportunity_map`, `skill_gap_matrix`, `mentor_network_plan`, `finance_support_plan`, `wellness_plan`, `entrepreneurship_plan` when active
- Can run in parallel with: none
- Blocks: frontend, final synthesis
- Validation gate: realistic sequencing and contingency branches

### `frontend`
- Role: user-facing architecture
- Owns: `frontend_spec`
- Depends on: roadmap and all user-visible artifacts, `observability_spec`
- Can run in parallel with: backend after shared interfaces are agreed
- Blocks: final assembly
- Validation gate: observability-first and responsive

### `backend`
- Role: service and runtime architecture
- Owns: `backend_spec`
- Depends on: execution plan, `frontend_spec`, `observability_spec`
- Can run in parallel with: frontend after interface handshake
- Blocks: final assembly
- Validation gate: persistence, streaming, lineage, repair support

### `observability`
- Role: trace and trust model design
- Owns: `observability_spec`
- Depends on: execution plan, frontend and backend direction
- Can run in parallel with: frontend, backend
- Blocks: final assembly
- Validation gate: run, agent, step, evidence, validation, repair visibility

### `reviewer`
- Role: critical validator
- Owns: `validation_report`
- Depends on: every major artifact
- Can run in parallel with: none
- Blocks: final assembly
- Validation gate: must have zero blocking findings to approve
