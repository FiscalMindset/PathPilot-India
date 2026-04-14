# Observability Requirements

## Purpose
Set the minimum visibility standard for the runtime-generated PathPilot India application.

## Required Global Run View
- run status
- total time
- active phase
- number of agents involved
- success or failure state
- retry count
- warning count

## Required Agent View
- agent name and role
- queued, running, success, or failure status
- start and end time
- parent and child relationships
- input summary
- output summary
- confidence
- validation status

## Required Step View
- execution timeline
- handoffs
- tool calls
- intermediate outputs
- retries
- fallback actions
- reviewer comments

## Required Final Synthesis View
- explanation of how recommendations were assembled
- assumptions made
- sources that influenced the output
- rationale for chosen opportunities and roadmap

## Layout Requirement
- left: agent timeline
- center: active workspace and trace details
- right: final recommendations and roadmap
- top: run metrics and trust indicators
- bottom drawer: raw trace, logs, and handoff events

## Responsive Requirement
All observability surfaces must remain accessible on mobile, tablet, laptop, and desktop.
