# Observability Generation Playbook

## Purpose
Guide generation of the trace and trust layer that makes the application demonstrably agentic.

## Required Output Categories
- raw events
- agent summaries
- phase summaries
- trust indicators
- final synthesis lineage
- reviewer findings and repairs

## Required Derived Metrics
- elapsed time
- active phase
- agents run
- retries
- warnings
- failed steps
- evidence-backed recommendation count
- unresolved assumption count

## Required UI Exposure
- top trust and status bar
- timeline and graph-like handoff visibility
- intermediate artifact previews
- repair history view
- why-this-recommendation explanation view

## Observability Guardrails
- no silent retries
- no missing timestamps
- no final recommendation without lineage
- no reviewer finding hidden from the run view when it affected outcome
