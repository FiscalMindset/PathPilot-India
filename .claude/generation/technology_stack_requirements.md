# Technology Stack Requirements

## Purpose
Define the preferred stack ladder for the runtime-generated PathPilot India application so the system produces an advanced, modern result by default.

## Stack Philosophy
Prefer proven, modern frameworks that speed up a credible demo and make architecture quality visible.

Do not optimize for:
- zero external dependencies
- easiest possible output
- lowest-common-denominator static pages

## Preferred Frontend Stack

### Primary Preference
- React
- TypeScript
- Vite or Next.js
- componentized routing/layout architecture
- utility-first or tokenized styling system

### Strongly Preferred Additions
- typed API layer
- structured client-side state for run and trace data
- reusable UI primitives for timeline, traces, trust indicators, and recommendation cards

### Acceptable Fallback
- another modern component-based framework with routing and modular UI structure

### Unacceptable Default
- plain HTML/CSS/JavaScript with no component architecture

## Preferred Backend Stack

### Primary Preference
- FastAPI or equivalently structured framework
- typed request and response models
- modular service layer
- persistence via SQLite or stronger store
- server-sent events or websockets for live trace updates

### Acceptable Fallback
- another modern backend framework with schema validation and modular service boundaries

### Unacceptable Default
- standard-library-only HTTP server or flat script architecture

## Preferred Generated Project Artifacts
- package/dependency manifests for the chosen stack
- modular source folders by responsibility
- explicit type or schema definitions
- seed/demo data for meaningful local evaluation
- smoke tests or minimal verification scripts

## Stack Decision Rule
If the primary preferred stack cannot be generated cleanly, choose the closest modern alternative.

Do not collapse from:
- React/TypeScript to plain HTML
- FastAPI or equivalent to a stdlib server
- modular app structure to a thin static prototype
