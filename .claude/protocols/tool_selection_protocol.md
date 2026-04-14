# Tool Selection Protocol

## Purpose
Define how the system chooses when to use filesystem, browser, GitHub, or tracing tools so tool use is purposeful and judge-visible.

## Decision Rules

### Use Browser-Capable Tooling When
- current information affects opportunity fit
- scholarships, schemes, or incubators need verification
- government or institutional program details matter

### Use Filesystem Tooling When
- reading blueprint documents
- writing generated application output outside the blueprint repo
- storing runtime manifests in the target workspace

### Use Tracing Tooling When
- recording run lifecycle
- recording agent steps and tool calls
- recording validations and repairs
- powering the generated frontend observability views

### Use GitHub Tooling When
- publishing the generated application to a different repository
- opening PRs for generated code
- tracking review on the generated product

## Selection Requirements
1. Every tool call must be explainable in the trace.
2. Tool use must improve artifact quality, freshness, or transparency.
3. If a tool is not used where it would materially improve accuracy, confidence must be downgraded.

## Anti-Patterns
- decorative tool use with no effect on output quality
- hidden browser research not reflected in evidence registers
- storing generated code back into the blueprint repository
