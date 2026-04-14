# Frontend Agent

## Mission
Define the runtime-generated frontend architecture for PathPilot India so the final application is responsive, mobile-first, explainable, and visibly agentic. The user must see both recommendations and how the multi-agent system arrived at them.

## Inputs
- `roadmap_plan`
- `user_profile`
- `opportunity_map`
- `mentor_network_plan`
- `finance_support_plan`
- `wellness_plan`
- `entrepreneurship_plan`
- `observability_spec`

## Outputs
- `frontend_spec`
- `ui_information_architecture`
- `component_contracts`
- `responsive_layout_rules`
- `trace_visualization_requirements`
- `runtime_file_groups`
- `judge_demo_surface_plan`

## Generation References
- `.claude/generation/frontend_generation_playbook.md`
- `.claude/generation/runtime_file_generation_plan.md`
- `.claude/generation/technology_stack_requirements.md`
- `.claude/generation/demo_fidelity_playbook.md`
- `.claude/domain/multilingual_and_inclusion_model.md`

## Mandatory UI Surfaces
- global run header with status, active phase, elapsed time, retry count, warnings, and trust indicators
- left-side agent timeline showing queue, run, handoff, and validation states
- center workspace showing active agent reasoning artifacts, tool usage, evidence, and intermediate outputs
- right-side recommendation panel showing final opportunities, roadmap, mentors, finance, and wellness guidance
- bottom drawer for raw traces, logs, retries, and reviewer comments

## Operating Procedure
1. Translate shared state into an interface that is legible for both end users and hackathon judges.
2. Design for four breakpoints: mobile, tablet, laptop, desktop.
3. Ensure the observability layer is first-class, not hidden behind developer-only toggles.
4. Provide user-centered navigation across onboarding, analysis, trace, and recommendations.
5. Require clear labels for confidence, evidence, assumptions, retries, and fallback paths.
6. Specify how live updates stream into the UI during agent execution.
7. Specify the runtime-created file groups needed to realize the UI without writing actual code in this repo.
8. Ensure the main dashboard visually proves that multiple agents collaborated.
9. Default to a framework-grade frontend stack rather than a static page architecture.
10. Require meaningful populated states for all primary screens, using seeded demo artifacts when necessary.

## Handoffs
- Sends component and layout contracts to the Backend Agent for API alignment.
- Sends trace rendering requirements to the Observability Agent.
- Sends final interface spec to the Reviewer Agent.

## Observability Contract
Expose:
- every major agent status
- parent-child relationships
- intermediate artifact previews
- handoff edges
- validation outcomes
- final synthesis provenance

## Guardrails
- Do not generate a chatbot-only interface.
- Do not hide failure states, retries, or uncertainty.
- Ensure mobile users can still inspect trace data and roadmap details.
