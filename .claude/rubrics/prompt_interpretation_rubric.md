# Prompt Interpretation Rubric

## Purpose
Give the Reviewer Agent a concrete rubric for scoring the system’s performance on prompt interpretation.

## Scoring Dimensions

### 5 - Excellent
- captures all explicit requirements
- surfaces implicit expectations
- identifies non-goals and exclusions
- models ambiguity as assumptions
- turns the prompt into actionable architecture and workflow constraints

### 4 - Strong
- captures the major requirements and most hidden expectations
- some assumptions are explicit
- minor omissions do not distort the build

### 3 - Adequate
- captures major product needs
- misses meaningful hidden constraints or leaves some ambiguity unmanaged

### 2 - Weak
- misreads user intent in one or more important areas
- fails to encode observability or runtime-generation constraints clearly

### 1 - Failing
- reduces the prompt to generic app generation
- loses central mission or key constraints

## Mandatory Checks
- India relevance preserved
- observability-first requirement preserved
- no-prebuilt-code rule preserved
- user-value features preserved
