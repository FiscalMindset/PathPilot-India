# Research Skill

## Purpose
Standardize how agents gather up-to-date evidence for opportunities, scholarships, schemes, learning paths, or ecosystem support relevant to Indian users.

## Use When
- a claim depends on current market or policy information
- the system needs source-backed recommendations
- the confidence score depends on source quality or freshness

## Research Rules
- Prefer official government, institutional, or primary ecosystem sources.
- Prefer sources that are current, attributable, and relevant to the user’s geography or path.
- Record freshness, authority, and scope for each source.
- Distinguish verified facts from inferred implications.

## Outputs
- evidence register
- freshness notes
- source quality score
- assumption list where data is incomplete

## Method
1. Start with the user’s profile and goal, not generic internet search terms.
2. Gather only the evidence necessary to support or reject a recommendation.
3. Store sources as structured references so the frontend can cite them.
4. If a source is incomplete or outdated, downgrade confidence and seek corroboration.
5. Keep evidence collection visible to the observability layer.

## Quality Bar
- No silent sourcing.
- No fabricated programs, mentors, institutions, or deadlines.
- No recommendation may appear final if the evidence is weak.
