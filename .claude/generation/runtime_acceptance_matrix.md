# Runtime Acceptance Matrix

## Purpose
Translate the generated PathPilot India application requirements into a crisp acceptance matrix the runtime system can validate after code generation.

## User-Facing Capability Acceptance

### Multilingual Onboarding
- Must exist as a first-run flow
- Must support language-aware onboarding structure
- Must not assume English-only usage

### Self-Discovery
- Must capture interests, strengths, motivations, and constraints
- Must produce a structured user profile view

### Opportunity Guidance
- Must present multiple opportunity pathways with rationale
- Must show why a path fits the user

### Skill-Gap Analysis
- Must connect current state to target path requirements
- Must expose prioritized skill gaps and proof-of-work needs

### Mentor And Network Guidance
- Must surface mentor or community categories and next-step outreach guidance

### Scholarship And Affordability
- Must include cost-aware support routes or lower-cost fallback paths

### Roadmap Planning
- Must include near-term milestones and longer-horizon progression
- Must expose milestone dependencies or rationale

### Entrepreneurship Branch
- Must appear only when activated by user fit or prompt fit
- Must include validation loops, not only startup ideas

### Wellness And Resilience
- Must adjust pacing or support cadence where overload risk exists

## Observability Acceptance

### Run-Level Visibility
- run status visible
- active phase visible
- retry and warning counts visible

### Agent-Level Visibility
- agent list visible
- status per agent visible
- input/output summaries visible
- confidence visible

### Step-Level Visibility
- handoffs visible
- tool activity visible
- intermediate outputs visible
- repair events visible

### Final Synthesis Visibility
- rationale visible
- assumptions visible
- source influence visible
- why-chosen explanation visible

## Architectural Acceptance

### Frontend
- responsive from mobile to desktop
- not chat-only
- observability visible without developer tools
- built with a modern component-based framework
- contains meaningful populated screens, not empty placeholders

### Backend
- run lifecycle supported
- artifact and trace persistence supported
- reviewer and repair loop supported
- lineage supported
- built with a real application framework and modular services
- not implemented as a minimal stdlib-only server by default

### Runtime Integrity
- generated code lives outside the blueprint repo
- build manifest references approved artifacts
- generated app reflects validated specs rather than ad hoc drift
- generated app includes dependency manifests and runnable project structure
- generated app includes demo-ready seeded data or meaningful local fixtures when live integrations are absent

### Implementation Depth
- core user flows are implemented, not stubbed
- observability surfaces render meaningful trace content
- roadmap, finance, mentor, and opportunity sections all contain structured content
- summary text does not describe the system as “placeholder-heavy” or “for future enhancement”

## Pass Rule
The runtime-generated application is acceptable only when every category above is satisfied or explicitly marked out-of-scope by the original prompt and approved by the Reviewer Agent.
