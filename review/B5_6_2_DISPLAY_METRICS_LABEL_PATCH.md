# B5.6.2 Display Metrics Label Patch

## Goal
Improve the clarity of Top Cards in the B5.6 Awarded Vendor Reviewer Clique Preview by distinguishing between filtered metrics and displayed metrics for reviewer groups.

## Target Files
- `review/v2-9-b5-6-awarded-vendor-reviewer-clique-preview-standalone.html`

## Implementations
- Replaced "Unique Groups" card with two separate cards: "Filtered Groups" and "Displayed Groups".
- "Filtered Groups" calculates deduplicated group keys based on all current filters (`filteredRows`).
- "Displayed Groups" calculates deduplicated group keys based on the subset rendered on screen (`displayedRows`).
- Updated "Unique Vendors" to properly reflect the deduplicated vendor count from `filteredRows` rather than `displayedRows`, as per design intent.

## Semantic Compliance
- The UI maintains neutral labels.
- The terms "特徵廠商", "重點廠商", "高頻廠商", "可疑廠商", "risk", "danger", "critical", "黑箱", "護航", "異常" are strictly prohibited and avoided.
