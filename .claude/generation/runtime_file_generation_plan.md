# Runtime File Generation Plan

## Purpose
Show how the generated PathPilot India application should be decomposed into runtime-created file groups without placing any application code in this repository.

## Generation Philosophy
The system should generate a modular full-stack app with code grouped by responsibility rather than dumping everything into a few coarse files.

## Required Frontend File Groups
- app shell and routing
- onboarding flow components
- dashboard layout and responsive containers
- agent timeline components
- active trace workspace components
- recommendation and roadmap components
- mentor, finance, entrepreneurship, and wellness panels
- trust indicator and confidence components
- raw event drawer components
- state and data hooks for live updates

## Required Backend File Groups
- orchestration engine
- agent dispatch and state transition services
- artifact persistence services
- trace event persistence services
- evidence ingestion or source adapters
- reviewer and repair services
- synthesis service
- API route or controller layer
- streaming gateway layer

## Required Shared File Groups
- trace entity types
- artifact and state types
- run and phase constants
- validation status types
- trust indicator calculations

## Required Test File Groups
- run bootstrapping smoke tests
- trace visibility tests
- artifact lineage tests
- roadmap response shape tests
- responsive frontend smoke coverage

## Output Rule
This file defines generation scope only. It must never contain the generated code itself.
