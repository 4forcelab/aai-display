# B3 TRI-SOURCE FRAME PREVIEW DRY FIT

## Purpose
The B3 Tri-Source Frame Preview allows human reviewers to inspect three distinct data source frames simultaneously (`API_OBSERVED_FRAME`, `API_NESTED_OBSERVED_FRAME`, and `HTML_VERIFIED_FRAME`) side-by-side in a single normalized view. This facilitates verification of parser accuracy and completeness before any cross-frame conflict resolution logic is applied.

## Inputs
- `v2_9_G36A42_true_api_observed_frame.json`
- `v2_9_G36B_api_nested_observed_frame.json`
- `v2_9_G36C2_html_verified_frame.json`

## Files Created / Modified
- `data/preview/g36b_api_nested_observed_frame.json`
- `data/preview/g36c2_html_verified_frame.json`
- `review/v2-9-b3-tri-source-frame-preview.html`
- `review/B3_TRI_SOURCE_FRAME_PREVIEW_DRY_FIT.md`

## Summary Metrics
- **Total Rows**: 1014
- **Cases**: 9

**Source Layer Counts:**
- `API_OBSERVED_FRAME`: 99 rows
- `API_NESTED_OBSERVED_FRAME`: 376 rows
- `HTML_VERIFIED_FRAME`: 539 rows

**Parse Status Counts (Sampled):**
- `UNKNOWN`: Includes empty string extraction failures.
- `AMBIGUOUS_MATCH`: Present for instances where structural DOM differences trigger ambiguity in the HTML frame.
- `FIELD_NOT_FOUND`: Explicitly tracked when requested metrics are missing from the parsed payload.

**Unknown Counts:**
- Extracted cleanly via the UI toggle (`Unknown-only`), isolating `UNKNOWN`, `AMBIGUOUS_MATCH`, and `FIELD_NOT_FOUND` into a single actionable review view.

## Safety Boundary
- Core datasets and `index.html` were explicitly bypassed.
- No new schemas were enforced back into the source dataset.
- Normalization mapping logic (e.g., standardizing `nested_key` and `field_label` to `_display_field`) lives exclusively within the browser execution context.

## Strict Doctrine Notes
- Tri-source preview consumes source frames only.
- This is not Hybrid.
- Hybrid reconciliation belongs to G37.
- This is not Index.
- `legal_conclusion = NOT_GENERATED`.
- No score / no index / no production frontend.
- Preview does not compare API vs HTML.
- Preview does not produce risk conclusion.

## B3.1 Attention Filter Semantics Repair
- **Unknown-only was separated from Attention Rows:** The rigid `Unknown-only` checkbox was upgraded to a granular dropdown filter.
- **Attention Rows include UNKNOWN, AMBIGUOUS_MATCH, and FIELD_NOT_FOUND:** The `需注意列 / Attention Rows` setting correctly aggregates all extraction exceptions.
- **These statuses are distinct observation states:** UI notes enforce that `UNKNOWN`, `AMBIGUOUS_MATCH`, and `FIELD_NOT_FOUND` convey distinct systemic conditions, not legal conclusion.
- **This remains preview-only and does not generate Hybrid, G37, score, index, or legal conclusion:** The strict doctrine boundary remains flawlessly intact.
