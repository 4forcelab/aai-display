# B5.10 Public Module Contract

## B5.10 Purpose
Create the public frontend module contract for B6. This file locks module ids, public display names, routes, data sources, field allowlists, field display rules, and public data boundaries.

## Contract Scope
| Field | Value |
|---|---|
| version | v2.9B5.10 |
| sealed_from | display-v2.9B5.9-front-copy-translation-lock-preview |
| purpose | B6 public frontend module contract |
| output_layer | public_display_contract |
| standalone_html_dependency | false |
| production_write_allowed | false |

## Public Modules
| Public id | Front zh | Front en | Route | Status |
|---|---|---|---|---|
| bid_preparation_module | 標案準備時間範例模組 | Bid Preparation Module | /modules/bid-preparation | preview_ready |
| reviewer_matrix | 委員組成矩陣 | Reviewer Composition Matrix | /modules/reviewer-matrix | contract_only |
| custom_supplier_management | 客戶訂製供應商管理系統 | Custom Supplier Management Module | /modules/supplier-management | preview_ready |
| supplier_case_management_example | 供應商案件管理範例 | Supplier Case Management Example | /modules/supplier-cases | contract_only |
| custom_information_example | 客戶訂製訊息範例 | Custom Information Example | /modules/custom-information | contract_only |
| entity_data_management_example | 機關資料管理範例 | Entity Data Management Example | /modules/entity-data | contract_only |
| timeline_field_calculator | 時間欄位計算器 | Timeline Field Calculator | /modules/timeline-calculator | contract_only |

## Field Allowlist
B6 may expose only contract-defined fields for each module payload. The B5.8 bid preparation module exposes this field set:

| Field | Display label | Type | Source layer | Transform rule |
|---|---|---|---|---|
| case_number | 案號 | string | source_observation | pass_through_string |
| case_name | 案名 | string | source_observation | pass_through_string |
| entity | 機關 | string | source_observation | pass_through_string |
| method | 採購方式 | string | source_observation | pass_through_string |
| budget_amount | 預算金額 | currency | source_observation | normalize_number_then_format_for_display |
| award_amount | 決標金額 | currency | source_observation | normalize_number_then_format_for_display |
| announce_date | 公告日期 | date | source_observation | normalize_to_YYYY-MM-DD |
| bid_deadline | 截止投標日期 | date | source_observation | normalize_to_YYYY-MM-DD |
| preparation_days | 標案準備時間 | integer | computed_arrangement | calendar_date_diff(bid_deadline, announce_date) |
| awarded_vendor | 得標廠商 | string | computed_arrangement | top_public_vendor_name_joined_for_display |
| reviewer_matrix | 委員組成矩陣 | string_list | computed_arrangement | top_public_reviewer_group_joined_for_display |

Computed field lock:
- preparation_days uses calendar_date_diff(bid_deadline, announce_date).
- Invalid when a date is missing or bid_deadline is earlier than announce_date.
- Invalid display value: unavailable.
- Invalid rows are excluded from summary day statistics.

## Source Layer Boundary
| Source layer | Public rule |
|---|---|
| source_observation | allowed only through field allowlist |
| computed_arrangement | allowed for computed result and rule display only |
| operator_annotation | not allowed for public frontend display |
| public_copy | allowed |

## Blank / Unavailable Policy
- null / empty / missing values display as `—`.
- Do not display raw `blank`.
- Do not display raw `undefined`, `null`, or `NaN`.
- Date display format is `YYYY-MM-DD`.
- Numeric display uses localized thousands separators where appropriate.

## Data Boundary
- B-Review is preview / dry-fit / contract lab.
- B-Prod is production display pack.
- B6 frontend must not directly reference review standalone HTML.
- B6 frontend must not consume large embedded JSON from standalone previews.
- B6 frontend should consume contract-shaped JSON payloads.

## B6 Handoff Notes
- Build B6 public index from `data/preview/b5_10_public_module_contract.json` plus future contract-shaped module payloads.
- Keep standalone previews as review artifacts only.
- Use B5.9 naming lock for public copy.
- Use this contract for field exposure, route naming, invalid value handling, and source-layer boundaries.

## Gate Result
- Expected module count: 7.
- Expected blocked-term count: 31.
- Production files touched: false.
- Standalone HTML dependency: false.

## Forbidden Copy Boundary
Forbidden terms are blocked from UI shell, public copy, report headings, module names, tags, and summary labels. The following list is the canonical boundary and may appear here only.

```text
risk
risk score
danger
critical
illegal
corruption
fraud
win rate
win-rate
win_rate
affinity
勝率
中標率
風險
黑箱
護航
派系
違法
弊案
貪腐
勾結
圖利
異常
可疑
可疑廠商
重點廠商
高頻廠商
特徵廠商
預算完全命中
代工小組
壟斷
```
