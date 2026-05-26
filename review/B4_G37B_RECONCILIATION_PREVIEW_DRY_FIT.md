# B4 G37B RECONCILIATION PREVIEW DRY FIT

## Purpose
The B4 preview demonstrates the G37B reconciliation dry run observations. It isolates and normalizes the conflict logic (API vs HTML, API Nested lists) into a human-readable table, enforcing strict neutral doctrine regarding risk and legal judgments.

## Inputs
- `v2_9_G37B_tri_source_reconciliation_dryrun.json`

## Summary Metrics
- **Total Rows**: 126
- **Total Cases**: 9
- **Canonical Fields**: 14

**Conflict Type Counts:**
- `HTML_ONLY`: 16
- `HTML_AMBIGUOUS_MATCH`: 33
- `API_HTML_VALUE_MISMATCH`: 13
- `OBSERVED_ONLY_NO_RECONCILIATION`: 36
- `UNKNOWN_VALUE`: 8
- `API_ONLY`: 20

**Reconciliation Status Counts:**
- `SOURCE_ONLY_OBSERVED`: 36
- `CONFLICT_OBSERVED`: 46
- `OBSERVED_ONLY`: 36
- `UNKNOWN_ONLY`: 8

**Allowed Next Action Counts:**
- `KEEP_OBSERVED`: 72
- `MAPPING_REPAIR`: 33
- `MANUAL_REVIEW`: 13
- `WAIT_FOR_ADDITIONAL_SOURCE`: 8

## Safety Boundary
- Core datasets and `index.html` were explicitly bypassed.
- This is an isolated review layer script only.
- Strict wording filters are enforced across UI logic.

## Strict Doctrine Notes
- G37B Reconciliation Preview consumes reconciliation dry run only.
- Conflict type is observation routing, not legal judgment.
- MATCH does not mean correctness.
- MISMATCH does not mean violation.
- `legal_conclusion = NOT_GENERATED`.
- No score / no index / no production frontend.
- Preview does not produce risk conclusion.
- Preview does not produce legal conclusion.

## B4.1 Table Render Repair
- KPI / filters were loading data, but table body rows were not rendering.
- Render pipeline was repaired with stable tbody selector and default All filters.
- Safe formatters were added for list/object/UNKNOWN values.
- Displayed Rows counter was added.
- This remains preview-only.
- No data JSON was modified.
- No score / no index / no production frontend.
- `legal_conclusion = NOT_GENERATED`.

## B4.2 Value Containment Repair
- Table was rendering rows but long HTML extracted values stretched the layout.
- HTML verified values, evidence paths, source refs, and confidence notes are now summarized by default.
- Full values are available through expandable details.
- Dense / Expanded display mode was added.
- No data JSON was modified.
- This remains preview-only.
- No score / no index / no production frontend.
- `legal_conclusion = NOT_GENERATED`.
