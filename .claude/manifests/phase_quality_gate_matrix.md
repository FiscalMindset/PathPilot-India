# Phase Quality Gate Matrix

## Purpose
Define the minimum acceptable output quality for each phase so the orchestrator and reviewer can enforce hard gates instead of relying on narrative judgment alone.

## Phase 0: Bootstrap
- Required outputs:
  - policy bundle loaded
  - workflow registry loaded
  - schema registry loaded
  - run metadata initialized
- Blocking conditions:
  - top-level repo shape is not blueprint-safe
  - required blueprint files are missing
- Pass condition:
  - run can proceed with full blueprint context

## Phase 1: Mission Framing
- Required outputs:
  - `prompt_interpretation`
  - initial `execution_plan`
- Minimum quality:
  - explicit requirements captured
  - implicit requirements captured
  - exclusions recorded
  - observability obligation recorded
  - runtime-generation constraint recorded
- Blocking conditions:
  - user goal is still ambiguous in a way that breaks downstream architecture
  - observability-first requirement missing
  - no-prebuilt-code rule omitted
- Pass condition:
  - prompt interpretation rubric score is at least 4/5

## Phase 2: User Grounding
- Required outputs:
  - `user_profile`
  - `uncertainty_flags`
- Minimum quality:
  - motivations, strengths, and barriers modeled
  - affordability and language comfort considered
  - assumptions separated from facts
- Blocking conditions:
  - profile ignores constraints
  - profile uses generic student stereotypes with no explicit assumption labeling
- Pass condition:
  - downstream agents can act without re-interpreting the user prompt

## Phase 3: Opportunity Intelligence
- Required outputs:
  - `market_landscape`
  - `opportunity_map`
  - `mentor_network_plan`
  - `finance_support_plan`
  - `entrepreneurship_plan` when active
- Minimum quality:
  - opportunities are evidence-backed
  - mentor guidance is actionable
  - finance guidance includes fallback routes
  - entrepreneurship is optional and justified
- Blocking conditions:
  - fabricated or weakly justified opportunities
  - inaccessible recommendations with no fallback
  - entrepreneurship forced without user fit
- Pass condition:
  - recommendation clusters are India-relevant and feasible

## Phase 4: Capability Planning
- Required outputs:
  - `skill_gap_matrix`
  - `wellness_plan`
  - `roadmap_plan`
- Minimum quality:
  - skill dependencies ordered
  - roadmap milestones are sequenced
  - pacing is sustainable
  - contingency branches exist
- Blocking conditions:
  - roadmap cannot explain step order
  - wellness has no effect on pacing
  - affordability ignored in milestones
- Pass condition:
  - roadmap can be surfaced as a credible 30/60/90-day plan

## Phase 5: Application Architecture
- Required outputs:
  - `frontend_spec`
  - `backend_spec`
  - `observability_spec`
- Minimum quality:
  - frontend visibly exposes the agentic process
  - backend supports persistence, streaming, and lineage
  - observability covers runs, agents, steps, evidence, validation, and repairs
- Blocking conditions:
  - generated app would appear chat-only
  - backend cannot support the designed trace experience
  - observability is decorative rather than structural
- Pass condition:
  - architecture quality rubric score is at least 4/5

## Phase 6: Review And Repair
- Required outputs:
  - `validation_report`
  - `repair_history`
- Minimum quality:
  - blocking findings are specific
  - repair requests include acceptance rules
  - repaired artifacts are revalidated
- Blocking conditions:
  - reviewer approval with unresolved blocking findings
  - repairs are invisible or unversioned
- Pass condition:
  - all blocking findings resolved

## Phase 7: Final Assembly
- Required outputs:
  - runtime build manifest
  - generation directives
  - validated final synthesis lineage
- Minimum quality:
  - file groups are scoped
  - generated app contract is satisfied
  - runtime target is external to the blueprint repo
- Blocking conditions:
  - build would write code into this repository
  - generated app contract is not satisfiable from current artifacts
- Pass condition:
  - automation depth rubric score is at least 4/5
