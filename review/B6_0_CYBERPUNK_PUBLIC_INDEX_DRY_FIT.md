# B6.0 Cyberpunk Public Index Dry-Fit

## B6.0 Purpose
B6.0 validates the external public frontend shell against the B5.10 public module contract. It is a dry-fit preview file only and does not modify production display files.

## Contract Source
- Contract file: data/preview/b5_10_public_module_contract.json
- Contract version: v2.9B5.10
- Sealed from: display-v2.9B5.9-front-copy-translation-lock-preview
- Public modules: 7
- Standalone HTML dependency: False
- Production write allowed: False

## Data Source
- data/preview/g40b_lifecycle_display_enriched.json
- data/preview/g40g_awarded_vendor_reviewer_clique_support.json
- Rows: 4446
- Date pair valid: 4309
- Computable preparation days: 4269
- Min / Avg / Max preparation days: 0 / 15.1 / 199

## B6.0.1 Visual + Interaction Repair
- Typography stack repaired for Traditional Chinese, English, and terminal numeric text.
- Low power canvas particle background added with reduced-motion handling.
- Interaction state split into activeModuleId, activeSampleFilter, and searchQuery.
- Module chips and sample tags are visually and behaviorally separated.
- Default sort repaired to announce_date descending.
- Summary cards use bilingual labels.
- Empty module handling added for contract locked and preview payload pending states.
- 李雨蓁 sample tag added.

## B6.0.2 Search Truth + Module State Repair
- 李雨蓁 correction completed.
- Active filter bar added for module, sample filter, search query, and result count.
- Search and sample filter collision handling added.
- No-result diagnostic message and Clear sample filter action added.
- Contract-only module state card added.
- Preview payload pending card added.
- Footer added.

## B6.0.3 Company Identity Copy Repair
- Correct English company name locked as 4Force Lab CO., LTD.
- Removed Wan He Tian Yi Ltd. from frontend/footer English copy.

## B6.0.4 Visual Readability + Logo Slot + Field Mapping Repair
- Footer readability repaired with larger type, looser line-height, more vertical padding, and separated content blocks.
- Insight Strategy Creativity Execution split into four neon spans with cyan, violet, magenta, and lime accents.
- Logo slot strategy added with brand-logo-slot and footer-logo-slot. Existing repo asset assets/4force-logo.png is referenced through a relative path with text fallback; no new logo file is committed by this dry-fit.
- case_name and entity mapping repaired using inspected source keys. case_name uses case_name with fallback sample metadata. entity uses procuring_entity_name with fallback sample metadata.
- Public field count explanation added so contract-only cards are not mistaken for connected datasets.
- Reviewer Matrix payload note added: source candidate g40g_awarded_vendor_reviewer_clique_support.json; next payload task reviewer_matrix_preview_payload.

## Logo Inspection
- Provided logo path: /Users/juantingwei/Downloads/萬合天宜logo小.png
- Format: PNG RGBA
- Size: 3544 x 3508
- Transparent background: yes
- Repo asset used in preview: assets/4force-logo.png

## Field Mapping
- case_name source key: case_name
- entity source key: procuring_entity_name
- missing / empty / colon-only values display as —
- 李雨蓁 searchable rows: 12
- 屏東縣政府 sample rows: 1042

## Public Modules
- bid_preparation_module | 標案準備時間範例模組 | preview_ready
- reviewer_matrix | 委員組成矩陣 | contract_only
- custom_supplier_management | 客戶訂製供應商管理系統 | preview_ready
- supplier_case_management_example | 供應商案件管理範例 | contract_only
- custom_information_example | 客戶訂製訊息範例 | contract_only
- entity_data_management_example | 機關資料管理範例 | contract_only
- timeline_field_calculator | 時間欄位計算器 | contract_only

## Blank / Unavailable Policy
- Missing, empty, null, undefined, and NaN display as —.
- Negative date order and unavailable preparation_days are excluded from preparation summaries.
- Raw standalone embedded HTML is not used as the B6 source.

## Data Boundary
- B-Review remains preview, dry-fit, and contract lab work.
- B-Prod remains the production display pack.
- B6 public frontend must not directly reference review standalone HTML as a data source.
- B6 public frontend should consume contract-shaped payloads.

## B6 Handoff Notes
- Default active module: bid_preparation_module.
- Default sort: announce_date descending.
- Module cards always display all seven public modules.
- Contract-only modules display state cards rather than empty tables.

## B6.1 Reviewer Matrix Preview Payload
- Source file: data/preview/g40g_awarded_vendor_reviewer_clique_support.json
- Schema keys inspected: group_key, group_members, group_size, attended_support, awarded_vendor_name, awarded_vendor_case_support, awarded_vendor_share, sample_cases, sample_case_count.
- Sample case keys inspected: case_number, case_name, procuring_entity_name, procuring_entity_code.
- Enrichment source: data/preview/g40b_lifecycle_display_enriched.json for procurement_method and recent date fields.
- Compact payload fields: reviewer_matrix, awarded_vendor, entity, support, share, sample_case_numbers, sample_cases, method, recent_date.
- Matrix rows: 7653.
- Reviewer groups: 692.
- Sample cases: 662.
- Awarded vendors: 507.
- Max support: 36.
- Avg share: 0.15.
- 李雨蓁 reviewer matrix rows: 23.
- Sample tags remain data filters for both bid_preparation_module and reviewer_matrix; they do not switch modules.
- Missing, empty, null, undefined, NaN, and colon-only values display as —.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.1.1 Hero Layout Regression + Reviewer Filter Sanity Repair
- Hero layout restored: left side keeps logo, public display label, title, subtitle, slogan, neon action line, and metrics cards.
- AAI Mobile Terminal placement restored into the hero right-side information area below Source & Model.
- Search bar, sample tags, module chips, reviewer matrix payload, 李雨蓁 search behavior, and reviewer matrix summary/table logic are preserved.
- Reviewer Matrix sample tag sanity result: 屏東縣政府 7653, 協昌 175, 三恆一樹 8, 李雨蓁 23.
- 屏東縣政府 7653 reason: g40g sample_cases all use procuring_entity_name = 屏東縣政府, so this is a source scope match rather than an overly broad page filter.
- Filter Mode added to the active filter bar with All Records, Sample Filter, Search Query, Combined Filter, and Source Scope Match / 資料源範圍命中.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.1.2 Visual Regression Restore
- B6.1 technical reviewer matrix payload retained.
- Hero, deep background, grid, and particle visibility restored with content kept above the background layer.
- Logo presentation repaired using the tracked assets/4force-logo.png file; no new logo or font files added.
- Source & Model and AAI Mobile Terminal remain in the hero right-side information area.
- Search bar, sample tags, module chips, bid preparation table, reviewer matrix table, and contract-only state cards are preserved.
- No production files touched.

## B6.1.3 Hero Title Readability + Hero Action Line Removal
- Hero title contrast restored with opaque high-contrast text and subtle shadow.
- Hero action line removed.
- Footer action line retained.
- B6.1 reviewer matrix payload untouched.

## B6.1.4 Logo Slot + Hero Tone Lock
- Logo slot border/card treatment removed.
- Logo renders as transparent brand asset from assets/4force-logo.png.
- Hero title tone reduced from bright white to cyberpunk high-contrast off-white.
- Footer action line retained.
- Data payload untouched.

## B6.1.5 Logo True-Color Lock + Reviewer Matrix Wide Table Repair
- Logo true-color CSS locked with filter none, opacity 1, normal blend mode, transparent background, and no mask.
- No logo file added or replaced; preview continues to use assets/4force-logo.png.
- Reviewer matrix table widened inside its own module content area.
- Sample case column widened and sample case text separated into compact chips.
- Payload and filter logic untouched.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.1.6 Viewport Width + Filtered Summary Recompute + Table Wrapping Repair
- Operation layer widened to width min(1760px, calc(100vw - 48px)) without changing the hero layout.
- Bid preparation summary cards use filteredRows and computeBidSummary after activeSampleFilter and searchQuery are applied.
- Bid preparation table wrapping repaired with a wider table, column min-width rules, nowrap numeric/date fields, and table wrapper horizontal scroll.
- Reviewer matrix wide table preserved with min-width 1680px or greater and the sample case column at 520px or greater.
- Filtered summary sanity:
  - all_records: count 4446 / computable 4269 / min 0 / avg 15.1 / max 199.
  - 屏東縣政府: count 1042 / computable 1033 / min 0 / avg 18.1 / max 199.
  - 協昌: count 10 / computable 10 / min 11 / avg 15.9 / max 21.
  - 三恆一樹: count 6 / computable 6 / min 10 / avg 11.0 / max 12.
  - 李雨蓁: count 12 / computable 12 / min 10 / avg 12.1 / max 16.
- 屏東縣政府 max preparation days remains 199 as a filtered data result, not a summary bug.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.1.7 Design Token Lock + Table Hierarchy + Logo True-Color Enforcement
- Design tokens locked for operation width, readable width, summary number color, summary label color, table header color, table body color, muted table text, panel background, and panel border.
- Operation container width stabilized with the shared min(1760px, calc(100vw - 48px)) token for the search area, module block, active preview block, summary cards, and table blocks.
- Summary card hierarchy repaired with stronger cyan numbers, smaller bilingual labels, and stable label line-height.
- Table header hierarchy repaired with sticky neon cyan headers, stronger header weight, clearer header background, and readable body values.
- Logo true-color CSS enforced on brand and footer logo images with no filter, full opacity, normal blend mode, transparent background, and no mask.
- Payload and filter logic untouched.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.1.8 Official Logo Asset Replacement + Logo Provenance Lock
- Official logo copied from /Users/juantingwei/Downloads/萬合天宜logo小.png to assets/4force-logo.png.
- Source file: PNG image data, 3544 x 3508, 8-bit/color RGBA, non-interlaced.
- Target file: assets/4force-logo.png, PNG image data, 3544 x 3508, 8-bit/color RGBA, non-interlaced.
- Alpha channel / transparent background: present.
- True-color brand asset locked in CSS; no recolor, no filter, no base64 embedding, and no SVG conversion.
- Module payload logic untouched.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.1.9 Apply Logo Proof Rendering To Main Page
- Logo Proof Gate confirmed the tracked brand asset renders normally on black at 24, 32, 40, 48, 64, 96, and 128 px.
- Main page now uses proof-style direct img rendering for the hero and footer logos.
- Top logo size increased to 64 px target height to preserve true-color detail on black.
- Footer logo size increased to 32 px target height.
- Logo parent contamination removed: wrapper slots keep only layout sizing and alignment, with no frame, card treatment, filter, blend, mask, or background overlay.
- Diagnostic review/logo-proof.html removed from the working tree.
- Data payload untouched.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.1.10 Hero Logo Inline Hard Lock
- Previous class-based logo sizing did not match visual render in the main page context.
- Hero logo inline locked to 72 x 72 with fixed width, height, min/max dimensions, contain fit, no filter, full opacity, normal blend mode, transparent background, and no mask.
- Footer logo inline locked to 36 x 36 with the same true-color rendering constraints.
- No recolor, no filter, and no wrapper frame added.
- Runtime computed logo check added with console.table for hero and footer logo rendered size, natural size, filter, opacity, and mixBlendMode.
- Data payload untouched.

## Gate Result
- Production untouched check: no production diff expected.
- Banned terms scan expected: html_hits [] and md_hits_before_forbidden_section [].
- Preview URL: file:///Users/juantingwei/Documents/4Force-AI-Lab/aai-display-review-codex-b/review/v2-9-b6-0-cyberpunk-public-index-dry-fit.html

## Forbidden Copy Boundary
Forbidden terms remain sourced from B5.10. They may appear in this section only when listed for scanning context.

- risk
- risk score
- danger
- critical
- illegal
- corruption
- fraud
- win rate
- win-rate
- win_rate
- affinity
- 勝率
- 中標率
- 風險
- 黑箱
- 護航
- 派系
- 違法
- 弊案
- 貪腐
- 勾結
- 圖利
- 異常
- 可疑
- 可疑廠商
- 重點廠商
- 高頻廠商
- 特徵廠商
- 預算完全命中
- 代工小組
- 壟斷
