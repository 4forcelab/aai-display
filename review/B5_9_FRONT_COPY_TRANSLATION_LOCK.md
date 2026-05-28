# B5.9 Front Copy Translation Lock

## Seal
- Version: v2.9B5.9
- Sealed from: display-v2.9B5.8-bid-preparation-module-preview
- Purpose: provide B6 with locked front-facing names, homepage copy, table labels, card labels, and copy boundary rules.

## Module Naming Lock
| Internal name | Front zh | Front en | UI display area | Public safe |
|---|---|---|---|---|
| Bid Preparation Window | 標案準備時間範例模組 | Bid Preparation Module | module title, navigation, preview header | true |
| Reviewer Matrix | 委員組成矩陣 | Reviewer Composition Matrix | table column, detail panel, module section | true |
| Target Vendor Lens | 客戶訂製供應商管理系統 | Custom Supplier Management Module | module title, navigation, preview header | true |
| Vendor Case Drilldown | 供應商案件管理範例 | Supplier Case Management Example | module title, detail panel, table section | true |
| Case Evidence Card | 客戶訂製訊息範例 | Custom Information Example | detail card, case panel, preview block | true |
| Entity Lens | 機關資料管理範例 | Entity Data Management Example | module title, navigation, entity panel | true |
| Timeline Compression | 時間欄位計算器 | Timeline Field Calculator | module title, table card, timeline section | true |

## Homepage Copy Lock
| Field | Locked copy |
|---|---|
| title | 4Force Active Audit Intelligence |
| subtitle | CAIRN in the DARKPOOL |
| slogan | What's already there, arranged. |
| source_model_title | Source & Model |
| source_model_body_zh | 4Force Active Audit Intelligence 由萬合天宜有限公司 4Force Lab 團隊開發。<br>系統可依合法授權資料、客戶提供資料或其他可使用資料源，進行欄位解析、關聯排列與情報顯示。 |
| model_lead | Wesley Juan |
| contact | 0900-489-893 |
| manifesto | For those who refuse to lose to the absurd.<br>獻給不想輸給荒唐的人。 |

## UI Label Lock
### B5.8 Table Labels
| Key | Locked label |
|---|---|
| case_number | 案號 |
| case_name | 案名 |
| entity | 機關 |
| method | 採購方式 |
| budget_amount | 預算金額 |
| award_amount | 決標金額 |
| announce_date | 公告日期 |
| bid_deadline | 截止投標日期 |
| preparation_days | 標案準備時間 |
| awarded_vendor | 得標廠商 |
| reviewer_matrix | 委員組成矩陣 |

### B5.8 Card Labels
| Key | Locked label |
|---|---|
| matched_cases | Matched Cases |
| cases_with_date_pair | Cases With Date Pair |
| cases_with_computable_preparation_days | Cases With Computable Preparation Days |
| avg_preparation_days | Avg Preparation Days |
| min_preparation_days | Min Preparation Days |
| max_preparation_days | Max Preparation Days |
| top_entity_in_matched_cases | Top Entity in Matched Cases |

## Rules
- Use locked names for B6 front-facing module names, navigation labels, preview titles, card labels, and table labels.
- Do not promote raw payload wording into UI copy unless it passes this lock.
- If future raw payload text includes blocked wording, mark it as payload only and keep it out of UI copy.
- Front copy should describe arrangement, field calculation, data management, and information display without judgment language.

## Forbidden Copy Boundary
Forbidden terms are blocked from:
- UI shell
- public copy
- report headings
- module names
- tags
- summary labels

Forbidden terms may appear in this section as the canonical blocked list. If future raw payload text contains these terms, mark it as payload only and do not promote it into UI copy.

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
