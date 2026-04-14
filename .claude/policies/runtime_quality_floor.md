# Runtime Quality Floor Policy

## Purpose
Prevent the runtime generator from taking the easiest possible path, such as a placeholder-heavy scaffold, a vanilla static frontend, or a minimal standard-library backend, when the goal is a serious hackathon-quality application.

## Core Rule
Optimize for implementation depth, judge impact, and product credibility over zero-dependency portability.

## Required Quality Floor
The generated application must be:
- framework-based, not a raw static fallback
- modular, not a single-file or near-single-file scaffold
- implemented enough to demonstrate real flows, not placeholder screens
- demo-ready, with seeded or generated sample data when live integrations are unavailable
- observability-rich, with trace panels that actually render meaningful run information

## Frontend Floor
- Use a modern component-based frontend framework.
- Prefer TypeScript for UI code and typed contracts.
- Use modular views/components for onboarding, dashboard, trace explorer, recommendations, and roadmap surfaces.
- Do not fall back to plain HTML plus loose JavaScript unless the prompt explicitly requests zero-framework output.

## Backend Floor
- Use an application framework with routed APIs, schema validation, and modular services.
- Do not use a standard-library-only HTTP server as the default architecture.
- Include a persistence strategy and a real orchestration service layer.
- Support streaming or incremental run updates for the observability dashboard.

## Demo Fidelity Floor
- If external APIs, keys, or fresh data are unavailable, generate realistic seeded demo data and simulated agent runs.
- Demo data must illuminate the product, not act as placeholders with “TODO” semantics.
- Trace panels must render real seeded or live event structures, not empty boxes.

## Disallowed Low-Depth Patterns
- “stubbed out with placeholders for future enhancement”
- “vanilla HTML/JS/CSS to avoid dependencies” as the main stack rationale
- “backend built only with Python standard library for portability” as the default choice
- a thin UI over a largely empty backend
- empty observability views that only show status labels without artifacts or lineage

## Reviewer Enforcement
The Reviewer Agent must reject any runtime output that:
- describes itself as stubbed-out for core product flows
- downgrades stack quality without strong justification
- uses low-dependency minimalism as a substitute for architecture quality
