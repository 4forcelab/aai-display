# B5.4 Reviewer Lens & Entity Trace Dry-Fit Report

1. **Source G40B enriched rows:** 4446
2. **Source vendor rows:** 7156
3. **Source G40C reviewer records:** 7717
4. **Source G40C case summary rows:** 1233
5. **Reviewer lens rows:** 753
6. **李雨蓁 reviewer records:** 47
7. **李雨蓁 hit cases:** 47
8. **Entity trace implemented:** YES
9. **Quick trace chips implemented:** YES
10. **Reviewer lens implemented:** YES
11. **Reviewer case summary implemented:** YES
12. **B5.3.1 display rules retained:** YES
13. **Preview path:** `review/v2-9-b5-4-reviewer-lens-entity-trace-standalone.html`

## UI Hotfix
- Fixed sticky table header drift by anchoring table header to table wrapper.
- Added Apply Trace button for Entity Trace.
- Added Enter key handling for Entity Trace input.
- Current View now reports active Entity Trace value.

UI 修補：
- 修正表頭飄移，將表頭固定於表格容器上緣。
- 新增 Entity Trace 套用追蹤按鈕。
- 新增 Entity Trace 輸入框 Enter 觸發。
- Current View 顯示目前追蹤值。

## B5.4.1 Trace Builder Hotfix
- Fixed Apply Trace button binding.
- Added Enter/Escape handling for Entity Trace input.
- Added dynamic trace panel.
- Added AND-based Trace Conditions.
- Quick Trace chips now either set trace target or toggle trace conditions.
- Entity Trace now updates Trace Target and matched counts dynamically.

B5.4.1 追蹤器修補：
- 修正 Apply Trace 按鈕綁定。
- 新增 Entity Trace 輸入框 Enter / Escape 操作。
- 新增動態追蹤面板。
- 新增 AND 條件式 Trace Conditions。
- Quick Trace chips 可設定追蹤目標或切換追蹤條件。
- Entity Trace 會即時更新追蹤目標與命中數。

## B5.4.2 Trace Runtime Repair
- Added global runTraceApply().
- Added inline onclick fallback for Apply Trace.
- Added inline Enter/Escape handler for Entity Trace input.
- Added runtime Trace Debug panel.
- Added runTraceSelfTest() for 李雨蓁 = 47 cases.
- Ensured non-empty trace with zero matches returns zero rows, not all rows.

B5.4.2 追蹤器 runtime 修補：
- 新增全域 runTraceApply()。
- Apply Trace 加入 inline onclick 防線。
- Entity Trace 輸入框加入 Enter / Escape inline handler。
- 新增 runtime Trace Debug 顯示。
- 新增 runTraceSelfTest()，驗證李雨蓁 = 47 cases。
- 確保 trace 有值但無命中時顯示 0 rows，不回退成全資料。

## B5.4.3 Entity Trace Hard Patch
- Replaced trace matching with buildTraceContextHard().
- Added TRACE_RUNTIME global state.
- Added runtime debug fields for trace term and matched case set.
- applyFilters now consumes the hard matchedCaseSet.
- Entity Trace input updates runtime debug on input.
- Apply / Enter / Quick Trace all route through runTraceApply().

B5.4.3 Entity Trace 硬修：
- 以 buildTraceContextHard() 重建追蹤配對。
- 新增 TRACE_RUNTIME 全域狀態。
- 新增 trace term 與 matched case set runtime debug。
- applyFilters 改用 hard matchedCaseSet。
- Entity Trace 輸入時即時更新 debug。
- Apply / Enter / Quick Trace 統一走 runTraceApply()。

## B5.4.4 Stats Truth Patch
- Removed hardcoded 李雨蓁 trace card.
- Implemented caseMetaMap for canonical case resolving.
- Event rows now use resolved case names to fix UNKNOWNs.
- Fixed Case Summary flags render error.
- Implemented aggregateUniqueCaseStats() to correctly aggregate case-level metrics across all modes avoiding lifecycle duplication.

B5.4.4 統計正確性修補：
- 移除寫死的李雨蓁追蹤卡。
- 實作 caseMetaMap 來從跨表單資料修補 case_name 等 metadata。
- 事件列現在會解析正確的 case_name，修正 UNKNOWN 顯示問題。
- 修正 CASE 模式中 flags 的陣列操作錯誤。
- 實作 aggregateUniqueCaseStats() 以 unique case_number 去重複加總預算與決標金額。

## B5.4.5 Sortable Header + Duplicate Semantics Patch
- Implemented sortable table headers for EVENT, CASE, VENDOR, REVIEWER, and REVIEWER_SUMMARY modes.
- Added visual asc/desc indicators (▲ / ▼) on active sorting headers.
- Added explicit duplicate semantics alert explaining why Event Rows contains duplicate case_number.
- Appended raw/deduped budget/award discrepancy metrics to Trace Debug for transparent diagnostics.

B5.4.5 表頭排序與重複語意修補：
- 實作所有視圖模式的表頭點擊排序。
- 在作用中表頭加入排序方向箭頭提示。
- 新增醒目提示說明事件列可能包含重複案號以及總額去重計算邏輯。
- 將原始事件加總與去重加總金額的差異量輸出於除錯區，確保除錯透明。

## B5.4.6 Case Summary Resolver Propagation Patch
- Propagated resolveCaseName to CASE mode search, sort, and render.
- Propagated resolveCaseName to REVIEWER_SUMMARY mode search, sort, and render.
- Hydrated missing metadata (case_name, budget, award) in buildCaseSummary using getCaseMeta.
- Added countUnknownCaseNames and a debug indicator in Trace Debug.

B5.4.6 案件摘要解析傳遞修補：
- 將 resolveCaseName 傳遞至 CASE 模式的搜尋、排序與渲染中。
- 將 resolveCaseName 傳遞至 REVIEWER_SUMMARY 模式中。
- 在 buildCaseSummary 建立時透過 getCaseMeta 自動補齊遺失的 metadata。
- 新增 CaseName UNKNOWN 的除錯追蹤計數，確保解析完全。

## B5.4.7 Reviewer Co-occurrence Network Patch
- Fixed a typo (`c.casenumber` -> `c.case_number`) in `caseMatchesTraceConditions`.
- Added `CO_OCCURRENCE` View Mode to display a reviewer co-occurrence network table based on target trace context.
- Added `coBaseMode` control to toggle between Target Attended Cases and Target All Cases.
- Added `coTopN` control to adjust Matrix rendering density.
- Implemented `buildReviewerCaseIndex` for quick lookup mapping of reviewer relations.
- Implemented `buildCooccurrenceNetwork` to compute shared cases, overlap rates, and a real-time matrix grid.
- Implemented real-time matrix rendering via `renderCooccurrenceMatrix()`.

B5.4.7 委員共現網絡修補：
- 修正 `casenumber` 錯字，使首長出席等條件能正確判斷。
- 實作委員共現網絡模式（CO_OCCURRENCE），能以目前目標委員為核心擴展共現名單與同案資料。
- 支援動態共現矩陣（Matrix Panel），自動繪製 Top N 共現委員之間的出席重疊熱區。

## B5.4.8 Debug Hygiene + Co-occurrence UI Gate Patch
- Gated the `CaseName UNKNOWN` debug indicator so it only counts on `EVENT`, `CASE`, and `REVIEWER_SUMMARY` modes.
- Blanked out (set to `N/A`) the UI Budget and Award stats in `CO_OCCURRENCE` mode.
- Augmented the Co-occurrence Matrix panel meta descriptions to clearly explain target, base case methodology, and expected baseline values (e.g. 41 cases for 李雨蓁).
- Improved Empty Target UX on `CO_OCCURRENCE` mode with explicit guidance.

B5.4.8 除錯衛生與共現網絡 UI 修補：
- 修正 `CaseName UNKNOWN` 追蹤在委員視圖中報錯的誤判問題。
- 隱藏共現網絡模式下無意義的預算與決標總額，改顯示 N/A。
- 在共現矩陣面板新增詳盡的分析基準說明。
- 新增未輸入 Entity Trace 時的空狀態引導訊息。
