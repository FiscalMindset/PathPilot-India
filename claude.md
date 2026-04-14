# PathPilot India Agentic Blueprint

## 1. Identity
This repository is a blueprint-only autonomous application factory for the CBC Hackathon: Agentic Development Challenge.

It is intentionally not a product repository. It contains no prebuilt application code. Its only job is to define how Claude should interpret one high-level prompt, activate a coordinated multi-agent system, and generate the full PathPilot India application at runtime in a separate target workspace.

Top-level repository rule:
- allowed top-level items are exactly `.claude/` and `claude.md`
- no other top-level files or folders are permitted

## 2. Mission
When given a single high-level prompt, this system must autonomously generate a complete modern full-stack application called PathPilot India.

The generated application must help Indian students and young entrepreneurs with:
- multilingual onboarding
- self-discovery and aptitude mapping
- career pathway discovery
- opportunity and market analysis
- skill-gap analysis
- mentor, alumni, and peer-network guidance
- scholarship, grant, and affordability support
- roadmap planning
- optional entrepreneurship pathways
- wellness-aware pacing
- full observability of the agentic process

## 3. Hackathon Positioning
This blueprint is optimized for the published scoring criteria:
- Prompt Interpretation
- Agent Coordination
- Architecture Quality
- Automation Depth

The blueprint must therefore behave like a factory, not a polished but static app concept.

To score well, the system must visibly demonstrate:
- a faithful translation from the initial prompt to a structured build plan
- clear multi-agent ownership and handoffs
- modular frontend, backend, state, and observability architecture
- genuine automation across planning, research, synthesis, validation, repair, and final code generation

## 4. Non-Negotiable Constraints
The following constraints override all other preferences:

1. No prebuilt app code may exist inside this repository.
2. All frontend and backend code must be generated at runtime by the agent workflows.
3. The repository must remain limited to `.claude/` and `claude.md` at the top level.
4. Generated application code must be written to a separate runtime target workspace.
5. The generated app must expose the multi-agent process visibly in the frontend.
6. Every major output must emerge from agent execution, not from hidden manual content.

## 5. What This Blueprint Contains
This blueprint is composed of seven operational layers plus the master document:

### Agents
Defined in `.claude/agents/`.
These files describe role ownership, I/O contracts, handoffs, guardrails, and observability obligations for each specialist agent.

### Skills
Defined in `.claude/skills/`.
These files provide reusable execution methods such as planning, research, synthesis, UI generation, backend design, validation, and repair.

### Workflows
Defined in `.claude/workflows/`.
These files define named, repeatable paths from prompt intake through final application assembly.

### Tools
Defined in `.claude/tools/`.
These files define how browser, filesystem, GitHub, and tracing integrations should be used by the runtime system.

### Policies
Defined in `.claude/policies/`.
These files define coordination rules, explainability, no-hardcoding constraints, retry policy, observability obligations, completion gates, hackathon compliance, and scoring alignment.

### Operational Specifications
Defined in `.claude/schemas/` and `.claude/manifests/`.
These files make the system concrete through state schemas, artifact contracts, event models, workflow dependency maps, build contracts, and a registry-level view of the agent graph.

### Execution Protocols
Defined in `.claude/protocols/`.
These files define how autonomy, handoffs, repair loops, runtime generation, and tool selection behave at execution time.

### Competitive Rigor And Domain Models
Defined in `.claude/rubrics/`, `.claude/domain/`, and `.claude/generation/`.
These files strengthen judge-facing scoring performance, India-specific grounding, and the realism of runtime-generated file and module planning.

## 6. Problem Context
PathPilot India is designed to address a real guidance gap in the Indian context:
- many users lack personalized career support
- reliable information is fragmented across jobs, courses, scholarships, schemes, communities, and local ecosystems
- users often face barriers of money, language, location, confidence, family expectations, and bandwidth
- users need not just advice, but explainable pathways, visible reasoning, and step-by-step execution support

The generated application must feel like an opportunity navigator with traceable intelligence, not a generic chatbot dressed up with career wording.

## 6A. India-Specific Domain Modeling
This blueprint must reason about Indian users through structured domain models rather than superficial localization.

The authoritative domain references live in:
- `.claude/domain/india_user_personas.md`
- `.claude/domain/india_opportunity_taxonomy.md`
- `.claude/domain/affordability_and_access_model.md`
- `.claude/domain/multilingual_and_inclusion_model.md`

These files must shape:
- user profiling
- pathway prioritization
- affordability checks
- multilingual readiness
- entrepreneurship activation

## 7. Target Users
The generated application must be capable of serving:
- school students evaluating future options
- college students comparing careers and internships
- graduates entering the job market
- learners in tier-2 and tier-3 ecosystems seeking accessible pathways
- users balancing affordability and ambition
- aspiring founders, freelancers, and small-business starters
- users needing sustainable pacing and support accountability

## 8. Single Prompt Initiation Contract
The system must start from a single high-level prompt without requiring a human to break the problem down manually.

The prompt may be broad. The system must still:
- infer missing but necessary structure
- label assumptions clearly
- maintain confidence scores
- trigger repairs when uncertain assumptions create downstream risk

The first artifact created in any run is `prompt_interpretation`.

This artifact must capture:
- mission
- target users
- must-have capabilities
- non-goals
- quality expectations
- observability expectations
- runtime-generation constraints
- acceptance criteria

## 9. Required Registry
The following agents are mandatory and must always be available to the orchestrator:
- Orchestrator Agent
- Self-Discovery Agent
- Market & Opportunities Agent
- Skill-Gap Analysis Agent
- Mentor & Network Agent
- Financial & Scholarship Agent
- Roadmap Planner Agent
- Wellness & Resilience Agent
- Entrepreneurship Agent
- Frontend Agent
- Backend Agent
- Observability Agent
- Reviewer / Critic Agent

The authoritative execution registry lives in:
- `.claude/agents/`
- `.claude/manifests/agent_registry.md`

## 10. Shared State Model
All runtime behavior centers on a shared state object.

The authoritative schema lives in:
- `.claude/schemas/shared_state_schema.md`

Required top-level state keys:
- `run_meta`
- `prompt_interpretation`
- `user_profile`
- `market_landscape`
- `opportunity_map`
- `skill_gap_matrix`
- `mentor_network_plan`
- `finance_support_plan`
- `roadmap_plan`
- `wellness_plan`
- `entrepreneurship_plan`
- `frontend_spec`
- `backend_spec`
- `observability_spec`
- `validation_report`
- `repair_history`
- `final_synthesis`
- `state_journal`

State rules:
1. Each artifact must be versioned and owned by one responsible agent.
2. The Orchestrator Agent controls sequencing and global status but does not silently rewrite domain payloads.
3. The Reviewer Agent can reject or request repair but cannot silently patch another agent’s artifact.
4. Every mutation must be journaled with timestamp, actor, target key, and reason.
5. Repairs must append superseding artifacts instead of erasing lineage.

## 11. Artifact Contract Model
Every major output must obey the contract in `.claude/schemas/artifact_contracts.md`.

At minimum, every artifact must include:
- `artifact_id`
- `owner_agent`
- `status`
- `version`
- `confidence`
- `summary`
- `inputs`
- `evidence_refs`
- `assumptions`
- `open_questions`
- `updated_at`
- `payload`

No handoff is valid unless the receiving agent can inspect:
- what was produced
- how confident it is
- which upstream artifacts informed it
- which uncertainties remain

## 12. Orchestration Engine
The Orchestrator Agent is the control plane for the system.

Its responsibilities are to:
- load policies, workflows, schemas, and registry manifests
- create `run_meta`
- generate `prompt_interpretation`
- construct the execution graph
- dispatch agents in the correct order
- track phase status
- trigger partial reviews at phase boundaries
- schedule repairs
- freeze approved artifacts for final assembly

The authoritative workflow graph lives in:
- `.claude/workflows/`
- `.claude/manifests/workflow_dependency_matrix.md`
- `.claude/protocols/autonomous_execution_protocol.md`
- `.claude/protocols/handoff_packet_protocol.md`
- `.claude/protocols/repair_loop_protocol.md`

## 13. Execution Phases
Every run must follow these phases.

### Phase 0: Bootstrap
- load blueprint files
- initialize run metadata
- validate top-level compliance constraints

### Phase 1: Mission Framing
- execute prompt interpretation
- establish mission, exclusions, and success criteria
- create the initial plan

### Phase 2: User Grounding
- run Self-Discovery Agent
- produce `user_profile`
- expose assumptions and unknowns

### Phase 3: Opportunity Intelligence
- run Market & Opportunities Agent
- run Mentor & Network Agent
- run Financial & Scholarship Agent
- run Entrepreneurship Agent only if activated
- research and evidence gathering occur here where required

### Phase 4: Capability Planning
- run Skill-Gap Analysis Agent
- run Wellness Agent
- run Roadmap Planner Agent

### Phase 5: Application Architecture
- run Frontend Agent
- run Backend Agent
- run Observability Agent
- align user experience, service model, event model, and lineage model

### Phase 6: Review And Repair
- run Reviewer Agent
- schedule targeted repairs
- rerun validation for impacted artifacts

### Phase 7: Final Assembly
- create build manifest
- generate the application in a separate runtime target
- ensure the app implements the approved architecture and observability contract

## 14. Parallelism Rules
Parallel execution is allowed, but only with explicit ownership boundaries.

Allowed concurrency examples:
- mentor and finance may run after `user_profile` and initial opportunity direction exist
- frontend, backend, and observability may iterate in tandem after interface and event handshake begins
- entrepreneurship may run in parallel with some analysis once activation is justified

Disallowed concurrency examples:
- two agents writing the same artifact namespace
- roadmap finalization before finance and skill gaps are available
- final assembly before reviewer approval

## 15. Prompt Interpretation Rules
Prompt interpretation is the foundation of scoring well on Prompt Interpretation.

Required behavior:
1. Translate user intent into explicit scope, implicit expectations, and non-goals.
2. Preserve all stated constraints and quality signals.
3. Capture hidden requirements such as India relevance, multilingual onboarding, affordability, explainability, and observability.
4. Never let the system “forget” the original user goal during later architecture phases.
5. Record ambiguity as assumptions instead of pretending certainty.

## 16. Agent Responsibility Rules
Every agent must have:
- a clearly bounded output namespace
- explicit inputs
- explicit downstream consumers
- observability obligations
- repair eligibility conditions

These rules are defined across:
- `.claude/agents/`
- `.claude/manifests/agent_registry.md`
- `.claude/policies/coordination_rules.md`

Role overlap is not allowed unless explicitly mediated through synthesis.

## 17. Skill Usage Rules
Skills are reusable execution methods, not decorative documentation.

Required skills include:
- planning
- research
- synthesis
- UI generation
- backend design
- observability design
- validation
- retry and repair

The orchestrator or specialist agents must invoke the relevant skill whenever the phase requires it. Skills exist to prevent agent drift and to keep outputs structurally consistent.

## 18. Workflow Rules
Every workflow must be named, repeatable, and auditable.

The system must rely on the workflows in `.claude/workflows/` to move from:
- prompt intake
- to user modeling
- to opportunity and support analysis
- to roadmap planning
- to frontend, backend, and observability architecture
- to validation and repair
- to final assembly

No critical stage may be skipped through ad hoc direct generation.

## 18A. Runtime Generation Playbooks
To maximize automation depth and architecture quality, final assembly must use generation playbooks instead of generic code synthesis.

The authoritative playbooks live in:
- `.claude/generation/runtime_file_generation_plan.md`
- `.claude/generation/frontend_generation_playbook.md`
- `.claude/generation/backend_generation_playbook.md`
- `.claude/generation/observability_generation_playbook.md`
- `.claude/generation/validation_and_demo_playbook.md`

These playbooks define:
- what file groups the runtime system must create
- how the UI should differentiate itself from a generic chat app
- how the backend must preserve lineage and replay
- how observability must be rendered
- how the generated app should be validated for judging

## 19. MCP And Tool Integration Rules
The blueprint must actively encourage real tool use where it improves quality.

Tool behavior is defined in:
- `.claude/tools/browser_mcp.md`
- `.claude/tools/filesystem_mcp.md`
- `.claude/tools/github_mcp.md`
- `.claude/tools/tracing_mcp.md`

Tool rules:
1. Use browser-capable tools when current facts materially affect recommendations.
2. Use filesystem tools only to read the blueprint here or write generated output outside this repo.
3. Use tracing tools to persist structured run, agent, step, validation, and repair events.
4. Use GitHub tools only for publishing or collaborating on the generated application in a separate repository if needed.
5. Tool calls must be represented in the trace model.

Tool selection behavior is governed by:
- `.claude/protocols/tool_selection_protocol.md`

## 20. Research Rules
When a recommendation depends on external facts, the system must:
- prefer official or primary sources
- record source freshness
- attach source references to artifacts
- separate verified facts from inference
- lower confidence when source quality is weak

Research rules are implemented through:
- `.claude/skills/research_skill.md`
- `.claude/agents/market_opportunity_agent.md`
- `.claude/agents/finance_scholarship_agent.md`
- `.claude/tools/browser_mcp.md`
- `.claude/domain/india_opportunity_taxonomy.md`
- `.claude/domain/affordability_and_access_model.md`

## 21. Frontend Generation Requirements
The runtime-generated frontend must use a modern React-based architecture and must be observability-first.

The UI must visibly include:
- top metrics and trust bar
- left agent timeline
- center active workspace and trace details
- right final recommendations and roadmap
- bottom raw trace and log drawer

The frontend must include views or modules for:
- onboarding
- self-discovery
- opportunities
- mentors and communities
- scholarships and affordability
- roadmap
- entrepreneurship branch when active
- wellness pacing
- synthesis explanation
- trace inspection

Design requirements:
1. Mobile-first responsive behavior across mobile, tablet, laptop, and desktop.
2. Confidence, assumptions, source influence, retries, and validation outcomes must be visible.
3. A user must be able to understand both the final guidance and the path used to create it.
4. The app must not degrade into a normal chat-only interface.

The output contract for the generated app is defined in:
- `.claude/agents/frontend_agent.md`
- `.claude/skills/ui_generation_skill.md`
- `.claude/schemas/generated_app_contract.md`
- `.claude/generation/frontend_generation_playbook.md`
- `.claude/generation/runtime_file_generation_plan.md`

## 22. Backend Generation Requirements
The runtime-generated backend must support:
- run creation
- stateful graph orchestration
- artifact persistence
- evidence and lineage capture
- trace event persistence
- validation and repair loops
- streaming updates to the frontend
- final recommendation delivery

Preferred implementation direction:
- LangGraph-style orchestration logic
- LangSmith-style tracing concepts
- modular service boundaries
- explicit data models for runs, agents, steps, artifacts, evidence, validations, and repairs

The backend must be capable of supporting replay, debugging, live demo flow, and final recommendation provenance.

The output contract for the generated app is defined in:
- `.claude/agents/backend_agent.md`
- `.claude/skills/backend_design_skill.md`
- `.claude/schemas/generated_app_contract.md`
- `.claude/generation/backend_generation_playbook.md`
- `.claude/generation/runtime_file_generation_plan.md`

## 23. Observability Requirements
Observability is a first-class user feature and a judging feature.

The generated application must expose:

### Global Run View
- run status
- total time
- active phase
- number of agents involved
- success or failure state
- retry count
- warning count

### Agent View
- agent name
- role
- queued, running, success, or failure state
- start and end times
- parent and child relationships
- input summary
- output summary
- confidence
- validation status

### Step View
- execution timeline
- handoffs
- tool calls
- intermediate outputs
- retries
- fallback actions
- reviewer comments

### Final Synthesis View
- how recommendations were assembled
- what assumptions were made
- what sources influenced the output
- why the chosen roadmap and opportunities were selected

The authoritative event model lives in:
- `.claude/schemas/trace_event_schema.md`
- `.claude/agents/observability_agent.md`
- `.claude/skills/observability_skill.md`
- `.claude/generation/observability_generation_playbook.md`

## 24. Explainability Rules
The system must be able to answer, from the frontend alone:
- which agents ran
- in what order they ran
- what each agent produced
- what evidence informed each output
- what failed or retried
- why the final guidance was synthesized as shown

No hidden black-box decision may materially affect the final output.

Explainability rules are enforced through:
- `.claude/policies/explainability_policy.md`
- `.claude/policies/observability_requirements.md`
- `.claude/schemas/artifact_contracts.md`
- `.claude/schemas/trace_event_schema.md`

## 25. Validation Rules
The Reviewer Agent is the internal quality gatekeeper.

The Reviewer Agent must validate:
- prompt fidelity
- India-specific relevance
- agent coordination depth
- architecture quality
- frontend observability visibility
- backend support for traces and repairs
- realism of roadmap and finance pathways
- entrepreneurship activation quality
- transparency of assumptions and confidence
- hackathon compliance

Validation cannot be superficial. It must yield:
- blocking findings
- non-blocking findings
- target artifact for each blocking finding
- acceptance rule for each repair
- final approval decision

The Reviewer Agent must score outputs against:
- `.claude/rubrics/prompt_interpretation_rubric.md`
- `.claude/rubrics/agent_coordination_rubric.md`
- `.claude/rubrics/architecture_quality_rubric.md`
- `.claude/rubrics/automation_depth_rubric.md`

## 26. Retry And Repair Rules
Repairs must be:
- narrow
- justified
- visible
- versioned
- revalidated

Rules:
1. Prefer targeted reruns over full regeneration.
2. Preserve valid upstream work whenever possible.
3. Log what changed, why it changed, and whether confidence improved.
4. Surface repair history in the trace.
5. Do not complete the run while blocking findings remain.

Repair behavior is defined in:
- `.claude/skills/retry_repair_skill.md`
- `.claude/workflows/validation_and_repair.md`
- `.claude/policies/retry_and_fallback_policy.md`

## 27. Runtime Assembly Rules
The generated application must be assembled only after the reviewer approves the artifact set.

The final assembly stage must:
- freeze the approved shared state snapshot
- emit a build manifest
- generate frontend, backend, observability, and test code in a separate target workspace
- preserve provenance from blueprint artifact to generated output
- ensure no code is written into this repository
- follow the runtime generation and file-group playbooks for coherent output

The runtime build contract is defined in:
- `.claude/workflows/final_application_assembly.md`
- `.claude/manifests/runtime_build_contract.md`
- `.claude/schemas/generated_app_contract.md`

## 28. Required Generated Application Capabilities
The runtime-generated PathPilot India application must be able to provide:
- personalized onboarding and profile capture
- explainable opportunity discovery
- comparative career and entrepreneurship pathways
- skill-gap analysis linked to target roles or ventures
- affordable learning and support routes
- mentor and peer-network suggestions
- scholarship and finance support discovery
- milestone-based roadmaps
- wellness-aware pacing adjustments
- visible multi-agent execution traces
- final synthesis with assumptions, evidence, and rationale

## 29. Disallowed Behaviors
The following are disallowed:
- extra top-level files or folders
- prewritten app code inside the blueprint repository
- generic chatbot-only UX as the generated app
- hidden retries or silent repairs
- fabricated mentors, scholarships, or institutional details
- hardcoded market truth presented as current fact
- manual outputs that bypass agent workflows
- collapsing the system into a single monolithic prompt with decorative sub-agent labels

## 30. Compliance References
The formal compliance interpretation for the CBC rulebook is defined in:
- `.claude/policies/hackathon_compliance.md`
- `.claude/policies/no_hardcoding_policy.md`
- `.claude/policies/completion_criteria.md`
- `.claude/policies/judge_alignment.md`

## 31. Completion Criteria
The run is complete only if:
- prompt interpretation is structurally sound
- all required agents have run or been explicitly skipped with justification
- all required artifact namespaces exist and validate
- frontend, backend, and observability specs are aligned
- zero blocking reviewer findings remain
- repair history is preserved
- final synthesis is traceable to validated upstream artifacts
- the final assembly stage can generate the full application outside this repository

Completion rules are operationalized in:
- `.claude/policies/completion_criteria.md`

## 32. Blueprint Integrity Rule
If a choice improves aesthetics but weakens explainability, coordination clarity, runtime generation purity, or hackathon compliance, reject that choice.

This blueprint wins by being:
- explicit
- modular
- repairable
- observable
- autonomous
- domain-grounded
- judge-readable
- fully aligned with the challenge rules
