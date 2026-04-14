# Demo Fidelity Playbook

## Purpose
Ensure the generated application feels complete and impressive during evaluation, even when real external integrations are limited.

## Core Principle
If live external systems are unavailable, generate realistic local demo depth rather than placeholder emptiness.

## Required Demo Assets In The Generated App
- seeded user profiles representing likely Indian user journeys
- seeded opportunity, roadmap, mentor, finance, and wellness artifacts
- seeded or simulatable agent run traces
- a complete happy-path experience from onboarding to final synthesis

## Required Demo Behaviors
- the dashboard should render immediately with meaningful state
- observability panels should show real example events and artifacts
- the roadmap should display concrete milestones, not blank shells
- the finance and mentor surfaces should contain realistic structured examples

## Acceptable Simulation
- deterministic seeded agent traces
- local fixtures representing research or evidence snapshots
- mock streaming of agent events using the real event schema

## Unacceptable Simulation
- empty cards labeled “coming soon”
- major screens with lorem ipsum or TODO placeholders
- observability shells with no meaningful event content

## Reviewer Rule
If the generated app would look unfinished during a local demo, it does not meet this playbook.
