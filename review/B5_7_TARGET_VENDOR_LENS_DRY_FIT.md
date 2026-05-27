# B5.7 Target Vendor Lens Dry-Fit Report

## Goal
Establish a standalone preview UI specifically dedicated to **Target Vendor Lens / 指定廠商透視**. This UI focuses on Awarded Vendor Co-presence (Computed Arrangement) without making inferences regarding motives or legal judgments.

## Target Files
- `review/v2-9-b5-7-target-vendor-lens-standalone.html`

## Implementations
- Created a fresh HTML file directly embedding the `g40g_awarded_vendor_reviewer_clique_support.json` payload.
- Added explicit UI labels strictly utilizing terms like "Target Vendor", "Awarded Vendor Co-presence", and "Computed Arrangement".
- Implemented Target Vendor input with handy `ex: [三恆一樹] [協昌] [reset]` shortcut tags.
- Built **Vendor Summary Cards**:
  - Matched Rows
  - Matched Groups
  - Total Awarded Vendor Support
  - Avg Awarded Vendor Share
  - Top Entity in Sample Cases
  - Top Method in Sample Cases
- Built **Top Reviewer Groups Table**:
  - Displays Reviewer Group members (badges) alongside the Target vendor name.
  - Shows Awarded Vendor Support, Awarded Vendor Share, Group Attended Support, and Case Support.
  - Lists inline sample cases with fields: `case_number`, `case_name`, `procuring_entity_name`, `procurement_method`, `budget_amount`, `award_amount`.
- Added Sort controls (Support, Share, Attended) and Display Rows limits (100, 300, All).

## Semantic Compliance & Gate Check Results
- JSON Parse successful (dataset rows: 7,653)
- Banned terms (including any references to motive, illicit intent, or scoring metrics) are strictly prohibited. The scan resulted in a legitimate false positive from a project name concerning tree inspection services in the payload data.
- "三恆一樹" yielded 8 matched rows and 8 groups.
- "協昌" yielded 175 matched rows and 175 groups.
- All `awarded_vendor_share` values are <= 1.
- Production and Core repos were untouched.
