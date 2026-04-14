# Filesystem MCP Guidance

## Purpose
Control how runtime artifacts and generated application code are written so the blueprint repository remains clean and compliant.

## Allowed Actions Inside This Repository
- read blueprint files
- update blueprint files when the system architecture evolves

## Prohibited Actions Inside This Repository
- creating application source code
- storing generated frontend or backend implementation
- persisting build outputs, assets, compiled artifacts, or demo code

## Runtime Generation Rule
When the system is asked to build the application, it must create output in a separate runtime target selected for generation. The blueprint repository remains limited to `.claude/` and `claude.md`.

## Required Metadata For Runtime Output
- generation timestamp
- blueprint version reference
- run identifier
- build manifest
- validation snapshot
