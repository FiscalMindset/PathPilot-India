# Retry And Fallback Policy

## Purpose
Define how the system responds when an agent produces weak output, conflicting analysis, missing evidence, or stale research.

## Rules
1. Prefer the smallest repair surface that can resolve the issue.
2. Log every retry with reason, target artifact, and expected improvement.
3. When evidence quality is low, downgrade confidence before rerunning.
4. When a full rerun is unnecessary, preserve still-valid artifacts.
5. Surface fallback branches to the frontend instead of hiding them.

## Fallback Examples
- if scholarship evidence is uncertain, show a verified low-cost alternative path
- if entrepreneurship confidence is low, preserve a career-first roadmap branch
- if market signals conflict, show the conflict and explain the chosen default

## Completion Rule
The run cannot be declared complete while unresolved blocking retries remain.
