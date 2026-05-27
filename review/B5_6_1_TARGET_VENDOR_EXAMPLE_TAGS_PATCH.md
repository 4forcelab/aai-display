# B5.6.1 Target Vendor Example Tags Patch

## Goal
Provide convenient shortcut tags for exploring specific awarded vendors in the UI, without attributing subjective or inferential labels.

## Target Files
- `review/v2-9-b5-6-awarded-vendor-reviewer-clique-preview-standalone.html`

## Implementations
- Added small pill-shaped tags (`.example-tag`) below the Vendor Search input.
- Added shortcuts for `三恆一樹`, `協昌`, and a `reset` button.
- Clicking a tag programmatically sets the input value and triggers a reactive `render()` filter update.

## Semantic Compliance
- The UI labels them as `ex:` and does not attribute terms like "risk", "danger", or "focus vendor".
- The patch acts strictly as a UI convenience for string matching.
