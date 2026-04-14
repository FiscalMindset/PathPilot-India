# Agent Coordination Rubric

## Purpose
Give the Reviewer Agent a concrete way to judge whether the system truly behaves like a multi-agent architecture.

## Scoring Dimensions

### 5 - Excellent
- roles are clearly distinct
- handoffs are explicit and high quality
- conflicts are routed through review or repair
- parallelism is used thoughtfully
- downstream agents clearly build on upstream artifacts

### 4 - Strong
- roles are mostly distinct
- handoffs are visible
- minor overlaps exist but do not damage clarity

### 3 - Adequate
- multiple agents exist, but collaboration feels linear and shallow
- some handoffs are thin or redundant

### 2 - Weak
- role overlap is common
- the system mostly behaves like a single agent with labels

### 1 - Failing
- no meaningful division of labor
- no visible handoffs or repair loops

## Mandatory Checks
- every major artifact has a single owner
- handoff packets include assumptions and confidence
- reviewer-triggered repair loops are functional
