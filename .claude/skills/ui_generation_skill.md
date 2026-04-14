# UI Generation Skill

## Purpose
Guide the creation of a modern, responsive, observability-first React interface for the runtime-generated PathPilot India application.

## Use When
- the Frontend Agent defines screens, components, and layout behavior
- the final assembly phase generates frontend code

## Design Principles
- mobile-first and low-friction
- visually clear multi-agent activity
- visible trust indicators
- accessible and multilingual-ready
- designed for both end users and judges

## Required UI Regions
- top run metrics and trust bar
- left agent timeline
- center trace workspace
- right recommendation canvas
- bottom raw event drawer

## Method
1. Start from the observability and information architecture, not decorative chrome.
2. Design the live run state before designing the static final view.
3. Ensure the layout gracefully stacks or tabs on smaller screens.
4. Use clear hierarchy for confidence, sources, and validation.
5. Make every important system state visible within two taps on mobile.

## Quality Bar
- No chat-only shell.
- No hidden “developer mode” for trace data.
- The UI must feel like an agent operations console and a guidance product at the same time.
