# Browser MCP Guidance

## Purpose
Use browser-capable tools to gather current, attributable information required for India-specific opportunities, scholarships, schemes, incubators, and market signals.

## When To Use
- current information affects recommendation quality
- an official page, policy, or program must be verified
- source freshness materially changes confidence

## Required Behavior
- prefer official sources, institutional pages, and primary references
- capture URL, title, access timestamp, and freshness notes
- store source references in the evidence register
- summarize findings in structured form for frontend display

## Do Not
- scrape indiscriminately
- rely on unverifiable summaries when primary sources exist
- hide source uncertainty from the trace

## Output Shape
- `source_id`
- `url`
- `title`
- `source_type`
- `freshness`
- `claim_summary`
- `confidence_impact`
