# Coordination Rules

## Purpose
Define how agents collaborate without duplicating work, overwriting each other, or collapsing into an unstructured sequence.

## Rules
1. The Orchestrator Agent owns sequencing, phase transitions, and global shared state.
2. Specialist agents may only write to their assigned artifact namespaces.
3. Cross-agent changes must happen through synthesis or explicit repair, not silent overwrite.
4. The Reviewer Agent can block completion and request targeted repairs.
5. Observability artifacts are mandatory deliverables, not optional documentation.
6. Parallel execution is allowed only when write ownership is disjoint or conflict-safe.
7. Every major handoff must include input summary, output summary, and confidence.
8. Every artifact must declare downstream consumers before handoff.
9. Any direct jump from mission framing to final assembly is invalid.
10. Final assembly may consume only validated artifacts.

## Required Handoff Packet
- upstream artifact IDs
- concise summary
- assumptions
- unresolved questions
- confidence score
- target acceptance rule

## Conflict Resolution
- If two artifacts contradict each other, the orchestrator must suspend dependent steps and route the contradiction to review or repair.
- If a lower-confidence artifact conflicts with a higher-confidence validated artifact, the lower-confidence artifact is repaired first.
- If conflict originates from mission framing, dependent artifacts must be marked stale.

## Completion Gate
No phase may close until required artifacts and observability events have both been produced.
