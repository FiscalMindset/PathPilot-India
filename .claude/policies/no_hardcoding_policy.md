# No Hardcoding Policy

## Purpose
Prevent the blueprint repository from containing prebuilt application code or static recommendation content that should be generated at runtime.

## Rules
- This repository may contain only orchestration instructions, policies, workflows, and agent definitions.
- Do not prewrite frontend pages, backend services, or database models for the generated app inside this repo.
- Do not hardcode scholarships, jobs, sectors, mentors, incubators, or government schemes as if they are timeless facts.
- When examples are useful, mark them as examples, not fixed truth.
- Runtime-generated code must be created in a separate target workspace.

## Review Standard
If a file in this repository looks like deliverable product code rather than blueprint logic, it violates this policy.
