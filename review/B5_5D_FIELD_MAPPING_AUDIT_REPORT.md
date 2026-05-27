# B5.5D Field Mapping Audit Report

## Gate Result

PASS with Metadata Partial.

## Scope

This audit checks whether B5.5 Reviewer Clique Mining preview can hydrate case metadata from:

- data/preview/g40b_lifecycle_display_enriched.json
- data/preview/g40c_reviewer_records.json
- data/preview/g40c_reviewer_clique_size3_preview.json

## Findings

- Reviewer case numbers can be matched against lifecycle display data.
- Reviewer cases are joinable by `case_number`.
- `procurement_method` is largely available and usable.
- `procuring_entity_code` / `procuring_entity` are available.
- Chinese `case_name` / tender title fields are not available for most reviewer-case intersections.
- Chinese `procuring_entity_name` is not available for most reviewer-case intersections.

## Display Decision

B5.5 Display should proceed as a preview with metadata coverage marked as partial.

UI fallback terms:

- `案名未補`
- `機關未補`
- `Metadata partial`
- `機關資料未補齊`

## Semantic Layer

This remains a Computed Arrangement layer.

The preview provides reviewer group support, attended support, single bidder case count, budget equality case count, and procurement method distribution.

It does not produce legal conclusions, motive inference, or subjective classification.

## Core Backlog

If full case names and Chinese procuring entity names are required, the next repair belongs in Core enrichment, not Display UI.

Potential Core follow-up:

- enrich reviewer-case intersections with tender title / case name
- enrich procuring entity display name from entity code or source payload
- preserve lifecycle row merge priority for non-empty metadata fields
