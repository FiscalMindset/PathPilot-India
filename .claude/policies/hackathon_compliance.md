# Hackathon Compliance Policy

## Purpose
Translate the CBC Agentic Development Challenge rulebook into enforceable blueprint rules.

## Rule Mapping

### Allowed Files Only
- This repository may contain only `.claude/` and `claude.md` at the top level.
- No other top-level file or directory is permitted.
- Additional blueprint content is allowed only inside `.claude/`.

### No Pre-Built Code
- No pre-written frontend code, backend code, database code, assets, or compiled output may exist in this repository.
- Application code must be produced only when the runtime generation workflow executes in a separate target workspace.

### Agentic Outputs Only
- Every meaningful output must originate from an agent workflow.
- No manual “final app spec” may bypass agent ownership, validation, or handoffs.

### Single Prompt Initiation
- The orchestrator must be able to start the full system from one high-level prompt without human clarification loops.
- Missing details must be handled through structured assumptions, confidence scoring, and repair-safe defaults.

### Multi-Agent Collaboration
- At least the required specialist agents must exist and collaborate through artifact handoffs.
- Each agent must have a distinct ownership boundary.

### Skill-Based Configuration
- Agent capability and behavior must be decomposed into reusable skills under `.claude/skills/`.

### MCP Tool Integrations
- Tool usage expectations for browser, filesystem, GitHub, and tracing must be defined under `.claude/tools/`.
- Tool use must influence the runtime system in observable ways.

### Structured Workflows
- The repository must define repeatable, named workflows connecting prompt interpretation through final assembly.

### Autonomous Code Generation
- The final application must be generated from the approved blueprint artifacts at runtime.
- The blueprint repository itself must never contain the generated application implementation.

## Submission-Time Audit
Before submission, verify:
- top-level contents are exactly `.claude/` and `claude.md`
- no app code exists anywhere in the repository
- all required agents, workflows, skills, and tool policies are present
- the orchestrator can explain how one prompt turns into a full application build

## Disqualification Triggers
- extra top-level files or folders
- hardcoded application code
- non-agentic outputs disguised as generated content
- plagiarism or copied workflow content
