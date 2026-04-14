# Explainability Policy

## Purpose
Ensure the generated application can clearly explain why it recommended each path, roadmap step, mentor support route, finance option, or entrepreneurship branch.

## Mandatory Rules
- Every major recommendation must link to contributing artifacts and evidence.
- Assumptions must be visible and labeled as assumptions.
- Confidence must be displayed alongside final outputs and intermediate artifacts.
- Rejected alternatives should be inspectable when they materially affected the final answer.
- Source freshness and authority must influence trust indicators.

## Frontend Requirement
The user must be able to answer the following from the interface alone:
- which agents ran
- what they produced
- what evidence they used
- what failed or retried
- why the final roadmap was chosen

## Prohibited
- black-box recommendations
- hidden heuristics that materially change outcomes
- silent synthesis steps with no provenance
