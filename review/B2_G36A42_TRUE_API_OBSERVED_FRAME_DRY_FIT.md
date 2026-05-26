# B2 G36A4.2 TRUE API OBSERVED FRAME DRY FIT

## Review Questions

**1. Preview 是否成功載入 99 rows / 9 cases？**
Yes. The 99 rows across 9 cases from the `v2_9_G36A42_true_api_observed_frame.json` sample loaded perfectly via the inline embedded JSON object.

**2. Row model 13 欄是否可讀？**
Yes. All 13 columns (`case_number`, `field_name`, `field_value`, `source_layer`, `source_type`, `extraction_method`, `parse_status`, `fallback_status`, `verification_status`, `legal_status`, `claim_type`, `confidence_note`, `source_ref`) are legible and distinct.

**3. source_ref 是否不再全部 UNKNOWN？**
Yes. Unlike the summary frame, the true API payload properly extracts the direct `web.pcc.gov.tw` URL references into `source_ref`.

**4. vendor_code / agency / award_amount 是否可辨識？**
Yes. The detailed API payload successfully populates `vendor_code` and `agency` perfectly, alongside `award_amount`. 

**5. verification_status / legal_status 是否能被人眼分辨？**
Yes. Distinct visual badges (`b-veri` and `b-legal`) were added to easily distinguish these states. Specifically, `NOT_GENERATED` for `legal_status` is clearly visible and colored purple to indicate it sits above the extraction layer.

**6. 使用者是否能看懂這是 true API_OBSERVED_FRAME，不是 Hybrid？**
Yes. An explicit strict doctrine note clarifies that this supersedes G36A summary and is entirely `API_OBSERVED_FRAME` (no Hybrid reconciliation, no G37 logic).

**7. 有哪些 UI 改良需求？**
Because the row model has expanded to 13 columns, horizontal scrolling is necessary. A future UI enhancement should pin/sticky the `case_number` and `field_name` columns to the left edge to prevent users from losing context when scrolling horizontally to read `confidence_note` or `source_ref`.

## Recommendation

- **B2 Recommendation:** **PASS**
- **是否建議後續進 G36B nested parser scope？** **Yes.** The Display/Review layer has proven that the 13-column `API_OBSERVED_FRAME` row model is structurally sound and ready. Agent A (Core) is clear to proceed into the G36B nested parsing phase (e.g., committee members, item lists).

## B2.1 Readability Repair Updates
- **B2.1 修正為 readability repair:** The core data row model and JSON payload were **not** modified.
- **production 未改:** The production index and datasets remain untouched.
- **source_ref 已改為可讀連結:** URLs are now rendered as `開啟來源 / Open Source` anchor tags instead of raw overflowing text strings.
- **field_name 已加中英文 label:** The `field_name` column now renders bilingual titles (e.g., 機關 / Agency) above the raw technical keys.
- **field_group 為 display-derived，不是 core data:** Added dynamic visual grouping (e.g., `識別 / Identity`, `廠商 / Vendor`) strictly derived at display-time inside the browser, keeping the core row model clean.

## B2.2 Case Identity Band + Feature View Updates
- **Case Identity Band is display-derived:** The UI dynamically groups and renders a distinct "Case Identity Band" header for each case using frontend Javascript, making it readable.
- **Core JSON row model was not modified:** The underlying dataset `g36a42_true_api_observed_frame.json` remains exactly as the Core A Process emitted it.
- **Feature Group Filter is display-derived from field_name mapping:** Users can now filter by `Identity`, `Vendor`, `Money`, etc., strictly via display-layer logic.
- **This remains TRUE API_OBSERVED_FRAME review layer:** The strict doctrine text confirms that this layout upgrade does not imply a new schema.
- **No Hybrid, no G37, no score, no index, no production frontend:** The system strictly observes B-Process gating boundaries.
