# Backend Design Skill

## Purpose
Guide the design of a runtime backend that supports orchestration, persistence, evidence storage, trace streaming, and recommendation delivery.

## Use When
- the Backend Agent defines services and APIs
- the final assembly phase generates backend code

## Required Concerns
- stateful graph execution
- artifact persistence
- evidence lineage
- repair loop management
- streaming updates
- queryable history

## Method
1. Model the backend around domain entities first: runs, agents, steps, artifacts, evidence, validations, repairs.
2. Define APIs that mirror how the frontend needs to inspect the system.
3. Make retries and fallbacks first-class records in storage.
4. Ensure final recommendations are linked back to contributing artifacts.
5. Prefer architecture that is realistic to build during a hackathon while still scalable in concept.

## Quality Bar
- No opaque backend jobs with no trace exposure.
- No final recommendation endpoint without provenance support.
- Storage and APIs must support both live demos and post-run inspection.
