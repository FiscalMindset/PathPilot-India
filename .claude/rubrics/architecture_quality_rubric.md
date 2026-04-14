# Architecture Quality Rubric

## Purpose
Evaluate whether the generated application architecture is modular, scalable, coherent, and aligned with the user problem.

## Scoring Dimensions

### 5 - Excellent
- frontend, backend, observability, and state models align tightly
- generated app modules are clearly scoped
- APIs support both live execution and replay
- architecture visibly supports observability-first UX
- design balances hackathon speed with production direction

### 4 - Strong
- architecture is modular and mostly aligned
- a few edges remain underspecified but do not break the concept

### 3 - Adequate
- architecture is workable but generic
- observability and domain features are present but lightly integrated

### 2 - Weak
- architecture feels bolted together
- frontend and backend assumptions do not match well

### 1 - Failing
- architecture cannot realistically support the promised app behavior

## Mandatory Checks
- responsive dashboard design exists
- backend persists traces and artifacts
- final synthesis lineage is represented
