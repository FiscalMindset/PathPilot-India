# Backend Generation Playbook

## Purpose
Guide runtime generation of a backend that can support live multi-agent execution, persistence, and explainability.

## Service Priorities
- deterministic state transitions
- queryable run history
- artifact versioning
- visible repairs
- streaming updates
- final synthesis lineage

## Required Service Boundaries
- run lifecycle service
- orchestration service
- agent execution coordinator
- artifact store
- trace event store
- validation and repair service
- synthesis service
- API and streaming surface

## Persistence Expectations
- runs, phases, agents, and steps must be queryable
- artifacts must be versioned
- evidence references must persist with artifacts
- repairs must retain before and after relationships

## Backend Guardrails
- do not generate a backend that cannot replay or inspect completed runs
- do not hide orchestration state in transient-only memory
- do not reduce final outputs to a single opaque recommendation blob
