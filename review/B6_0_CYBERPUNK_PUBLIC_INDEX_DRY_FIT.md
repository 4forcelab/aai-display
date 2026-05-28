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
