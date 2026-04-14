# Synthesis Skill

## Purpose
Merge multiple agent outputs into one coherent recommendation set without losing traceability, assumptions, or dissent between artifacts.

## Use When
- combining market, skill, finance, mentor, wellness, and entrepreneurship outputs
- building the final user-facing recommendation model
- resolving cross-agent conflicts

## Inputs
- domain artifacts from specialist agents
- validation findings
- decision ledger from the Orchestrator Agent

## Outputs
- merged recommendation narrative
- conflict resolution notes
- provenance map
- open questions for the Reviewer Agent

## Method
1. Group outputs by decision area rather than by source file.
2. Detect contradictions before merging, especially around feasibility and timing.
3. Preserve alternative paths when uncertainty is meaningful.
4. Attach provenance to every major recommendation cluster.
5. Produce both executive summaries and drill-down traces for the frontend.

## Quality Bar
- Final synthesis must explain why a recommendation exists, not only what it is.
- Confidence must never rise after synthesis unless new supporting evidence was added.
- Rejected alternatives must be capturable in the trace view.
