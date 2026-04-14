# Observability Skill

## Purpose
Standardize trace, metric, event, and explanation design so the generated application can visibly prove agent coordination quality.

## Use When
- defining event schemas
- designing trace panels
- setting confidence and validation rules
- creating retry and fallback displays

## Required Trace Entities
- run
- phase
- agent
- step
- tool call
- artifact
- evidence
- validation
- repair

## Method
1. Give every entity a stable ID and human-readable summary.
2. Separate raw events from derived summaries, but preserve the mapping.
3. Record start time, end time, status, parent, children, and confidence changes.
4. Attach evidence and assumptions directly to artifacts.
5. Provide rollups for run-level and agent-level trust indicators.

## Quality Bar
- Observability must serve explanation, debugging, and judging.
- Every retry must explain why it happened and what changed.
- Final synthesis must be inspectable back to source artifacts.
