# Planning Skill

## Purpose
Provide a repeatable method for turning one high-level prompt into a structured execution plan with phases, dependencies, validation points, and completion gates.

## Use When
- the run begins
- a major scope change appears
- the Reviewer Agent requests re-planning

## Inputs
- original prompt
- policy bundle
- available agents and workflows

## Outputs
- phase graph
- dependency map
- parallelization opportunities
- risk register
- success rubric

## Method
1. Convert the prompt into explicit objectives, implicit objectives, exclusions, and risk zones.
2. Break the run into phases with clean ownership boundaries.
3. Decide which agents can operate in parallel without conflicting state writes.
4. Define required artifacts for each phase exit.
5. Pre-register validation checkpoints before execution starts.
6. Identify where retries should be surgical instead of global.

## Quality Bar
- Plans must reflect hackathon judging priorities: prompt interpretation, agent coordination, architecture quality, automation depth.
- Plans must include observability milestones, not only product milestones.
- Plans must preserve the rule that application code is generated only at runtime outside this blueprint repository.
