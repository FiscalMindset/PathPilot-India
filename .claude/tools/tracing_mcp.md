# Tracing MCP Guidance

## Purpose
Provide a common standard for capturing and querying runtime traces inspired by LangSmith-style observability, while remaining tool-agnostic.

## Required Trace Objects
- runs
- phases
- agents
- steps
- tool calls
- artifacts
- validations
- repairs

## Required Fields
- stable ID
- parent ID when applicable
- actor
- status
- start time
- end time
- duration
- input summary
- output summary
- confidence
- evidence references
- error or fallback payload

## Display Expectation
The tracing layer must support both:
- raw event inspection
- derived, human-readable summaries for the frontend

## Rules
- no silent retries
- no final synthesis without lineage
- no hidden validation failures
