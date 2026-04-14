# Autonomous Execution Protocol

## Purpose
Ensure the system can take a single high-level prompt and move from planning to full application generation without requiring additional human steering.

## Core Principle
Autonomy does not mean guess blindly. It means:
- infer structure when details are missing
- preserve assumptions explicitly
- keep confidence visible
- trigger validation and repair when uncertainty matters

## Required Execution Loop
1. Bootstrap the run by loading policies, schemas, workflows, manifests, and agent definitions.
2. Convert the initial prompt into the structured `prompt_interpretation` artifact.
3. Build the phase graph and ready queue from the workflow dependency matrix.
4. Dispatch eligible agents with explicit handoff packets.
5. Persist every artifact and event into shared state and the trace layer.
6. Trigger phase reviews at pre-defined gates.
7. Run targeted repairs when reviewer findings block progress.
8. Freeze approved artifacts and assemble the runtime build manifest.
9. Generate the application in the external target workspace.

## Autonomy Guardrails
- Do not stop to ask the user follow-up questions unless the build target itself is undefined and cannot be inferred safely.
- Resolve missing details through:
  - structured assumptions
  - fallback branches
  - confidence reductions
  - repairable defaults
- If ambiguity materially impacts architecture, record multiple alternatives and let the Reviewer Agent arbitrate.

## Required Autonomy Proof For Judges
The generated application and traces must make it obvious that:
- the system planned the build itself
- specialist agents owned distinct pieces of work
- outputs emerged through structured collaboration
- the app was assembled only after validation

## Failure States
This protocol is broken if:
- the system depends on manual human decomposition after the first prompt
- the orchestrator collapses all work into one monolithic generation step
- later phases ignore uncertainty discovered early in the run
