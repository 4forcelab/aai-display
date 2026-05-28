# B5.8.2 Bid Preparation Module Data Hydration Repair Dry-Fit Report

## Goal
Repair standalone preview hydration so the initial view renders embedded rows.

## Target Files
- review/v2-9-b5-8-bid-preparation-module-standalone.html

## Data
- Primary source: data/preview/g40b_lifecycle_display_enriched.json
- Matrix support source: data/preview/g40g_awarded_vendor_reviewer_clique_support.json
- Rows count: 4,446
- Date pair valid count: 4,309
- Computable preparation days count: 4,269
- Negative date order count: 40
- Preparation days min / avg / max after repair: 0 / 15.1 / 199

## Repair
- Embedded data is now raw JSON inside application/json script content.
- Script-closing sequences are escaped only where needed.
- Browser JSON.parse reads the script textContent directly.

## First 20 Negative Date Order Sample Rows
| case number | case name | entity | announce date | deadline date | awarded vendor |
|---|---|---|---|---|---|
| 004-C1131228-1 | blank | blank | 2025-01-15 | 2025-01-13 | 沁琳營造有限公司 |
| 112-1227-143-1 | blank | blank | 2024-01-23 | 2024-01-22 | 長江龍環保工程股份有限公司 / 偉盛環境工程股份有限公司 / 元琪生化科技有限公司 |
| 113-1128-141-2 | blank | blank | 2025-01-22 | 2024-12-09 | 鴻威國際工程顧問股份有限公司 / 睿泰工程顧問有限公司 |
| 113-1128-141-2 | blank | blank | 2025-01-22 | 2024-12-16 | 鴻威國際工程顧問股份有限公司 / 睿泰工程顧問有限公司 |
| 114-073-0102P1 | blank | blank | 2025-01-22 | 2025-01-13 | blank |
| 114-073-0109A1 | blank | blank | 2025-01-22 | 2025-01-20 | blank |
| 114-073-0227P1 | blank | blank | 2025-03-19 | 2025-03-17 | 邑川營造工程有限公司 / 寶鴻旺營造股份有限公司 |
| 114-073-0826P1 | blank | blank | 2025-09-10 | 2025-09-08 | blank |
| 141-1131227P1 | blank | blank | 2025-01-22 | 2025-01-13 | blank |
| 141-1131227P2 | blank | blank | 2025-01-15 | 2025-01-13 | blank |
| 141-1131227P3 | blank | blank | 2025-01-15 | 2025-01-13 | blank |
| 141-1131227P4 | blank | blank | 2025-01-15 | 2025-01-13 | blank |
| 141-1131230A1 | blank | blank | 2025-01-15 | 2025-01-13 | blank |
| 141-1140103A1 | blank | blank | 2025-01-22 | 2025-01-20 | blank |
| 141-1140103A2 | blank | blank | 2025-01-22 | 2025-01-20 | blank |
| 141-1140103A3 | blank | blank | 2025-01-22 | 2025-01-20 | blank |
| 141-1140203 | blank | blank | 2025-02-19 | 2025-02-17 | blank |
| 142-1140103 | blank | blank | 2025-01-22 | 2025-01-20 | blank |
| 142-1140303 | blank | blank | 2025-03-19 | 2025-03-17 | blank |
| 142-E1140822-1 | blank | blank | 2025-09-10 | 2025-09-08 | blank |

## Gate
- Embedded rows parse count: 4,446
- Min preparation days is >= 0.
- Table preparation days are integer values or unavailable.
- UI file hits: []
- Report file hits: []
- Production entry and formal data files: no diff.
