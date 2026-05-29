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
- No-result diagnostic message and Clear filter action added.
- Contract-only module state card added.
- Preview payload pending card added.
- Footer added.

## B6.0.3 Company Identity Copy Repair
- Correct English company name locked as 4Force Lab CO., LTD.
- Removed the previous English-facing company-name variant from frontend/footer English copy.

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
- bid_preparation_module | 標案準備時間範例模組 | preview_connected
- reviewer_matrix | 委員組成矩陣 | preview_connected
- custom_supplier_management | 客戶訂製供應商管理系統 | preview_ready
- supplier_case_management_example | 供應商案件管理範例 | contract_only
- custom_information_example | 客戶訂製訊息範例 | contract_only
- entity_data_management_example | 機關資料管理範例 | contract_only
- timeline_field_calculator | 時間欄位計算器 | preview_ready

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
- Runtime logo verification was later replaced by a compact DevTools brand message to keep console output product-facing.
- Data payload untouched.

## B6.2.0 Gate Noise Cleanup + Continue Visual Stability Lock
- Gate noise cleanup completed: review markdown no longer duplicates raw blocked vocabulary; execution gates remain the source of scan patterns.
- Hero title readability locked with high-contrast title color, full opacity, and foreground stacking above haze, grid, and particle layers.
- Background glow reduced behind the main title area so haze supports the cyberpunk tone without washing out the title.
- Logo true-color preservation retained through the existing tracked brand asset and inline hard lock.
- Hero action line remains removed; the mission line remains confined to the footer/company positioning area.
- Operation layer width remains stabilized with the shared wide container token and table wrapper horizontal scroll.
- Summary cards and table hierarchy remain consistent with shared token colors, stronger numeric hierarchy, and sticky table headers.
- Reviewer Matrix remains structurally alive as a public co-presence view: names can form X/Y axes, cells can carry co-presence counts, and context can reference same case, vendor path, or review cluster.
- Reviewer matrix payload and filter logic untouched.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.3 Operation Layer / Module Hierarchy Lock
- Operation layer hierarchy tightened while preserving the wide min(1760px, calc(100vw - 48px)) control deck.
- Search, sort, module chips, sample tags, and active filter state now share one colder control surface with stable spacing and alignment.
- Module cards now use a consistent height rhythm, stronger active-state treatment, stable bilingual label spacing, and a consistent status badge position.
- Bid Preparation and Reviewer Composition Matrix remain visually important within the module card grid.
- Summary card hierarchy strengthened with shared numeric color, larger number scale, smaller bilingual labels, consistent internal spacing, and stable card height.
- Bid Preparation summaries continue to use filteredRows through computeBidSummary after active sample filters and search query are applied.
- Table headers strengthened with sticky neon cyan headers, heavier type, clearer header background, and denser but readable body rows.
- Bid Preparation and Reviewer Matrix tables keep wide-table behavior with horizontal scroll inside the table wrapper rather than body-level page drift.
- Reviewer / co-presence matrix direction preserved: X axis = person / reviewer / entity names; Y axis = person / reviewer / entity names; cell value = co-presence / overlap count; cell context = same case, same vendor path, or same review cluster.
- Reviewer matrix payload and filter logic untouched.
- Public demo language kept commercial and neutral; no legal-accusation, judgment, or public harm label vocabulary added.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.3.1 Header + Metric Card Hierarchy Micro Repair
- Table header dominance strengthened with larger 15px header text, heavier 900 weight, stronger cyan tone, increased vertical padding, and a clearer header separator.
- Body row density preserved with smaller table body text and unchanged wide-table horizontal scroll behavior.
- Hero metric cards now use a split value/label layout: large value on the left, bilingual label stack on the right, and a subtle divider between them.
- Bid Preparation and Reviewer Matrix summary cards now use the same split value/label hierarchy with larger numeric values and more readable bilingual labels.
- Summary values continue to be computed from filteredRows through computeBidSummary and existing reviewer matrix summary logic.
- B6.2/B6.3 gains preserved: hero readability, true-color logo handling, mission line absence in hero, wide operation layer, module card rhythm, active module state, and reviewer matrix payload/filter logic.
- Reviewer / co-presence matrix direction remains preserved for future X/Y matrix work.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.3.2 Metric Value Alignment Micro Repair
- Metric value alignment unified with centered value zones for both hero metrics and module summary cards.
- Hero metric values now share a fixed value-zone width and center alignment, so short values and longer values follow the same visual discipline.
- Bid Preparation summary values now share a fixed value-zone width and center alignment, preserving the split value/label card structure.
- No per-card or nth-child alignment hacks added.
- Data values, filteredRows summary logic, reviewer matrix payload, filter logic, table body data, and production files untouched.

## B6.4 Public Copy / Brand Surface Lock
- Public-facing copy locked to commercial SaaS / intelligence display demo language.
- Module naming remains public-safe through the locked front-facing labels: Bid Preparation Module, Reviewer Composition Matrix, Custom Supplier Management Module, Supplier Case Management Example, Custom Information Example, Entity Data Management Example, and Timeline Field Calculator.
- Module cards now display public module sample wording instead of backend source-module labels.
- Contract-only state cards now show Public Module with the front-facing English module name.
- Source & Model copy remains locked to the approved 4Force Active Audit Intelligence Chinese paragraph, Model Lead, and Contact lines.
- English-facing company name remains locked as 4Force Lab CO., LTD.; Chinese company wording remains 萬合天宜有限公司 4Force Lab.
- Hero slogan remains What's already there, arranged.; subtitle remains CAIRN in the DARKPOOL.
- Hero mission line remains absent. Footer/company positioning line remains controlled.
- Search, chip, and filter labels remain neutral public UI labels: MODULE CHIPS, SAMPLE TAGS, ACTIVE MODULE, SAMPLE FILTER, SEARCH QUERY, RESULT COUNT, and FILTER MODE.
- Reviewer / co-presence matrix wording remains public-safe through Reviewer Composition Matrix and Co-presence View, with future X/Y matrix direction preserved.
- B6.2/B6.3 visual gains preserved: hero readability, true-color logo, wide operation layer, module card rhythm, split metric cards, centered value zones, table header dominance, wide tables, and filteredRows summary logic.
- Reviewer matrix payload and filter logic untouched.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.4.1 Chinese UI Copy Micro Repair
- Search placeholder localized to 搜尋模組／機關／供應商／案件訊號.
- Sort dropdown visible labels localized to 公告日期由新到舊, 準備天數由少到多, 準備天數由多到少, and 決標金額由高到低.
- Sort option value attributes preserved, so existing sort behavior remains unchanged.
- B6.4 accepted public copy, Source & Model copy, footer company language, module cards, visual hierarchy, payload, and filter logic untouched.

## V8.2 Proposal Surface Seal

- Seal version: V8.2
- Seal target: production root proposal surface
- QA URL: https://aai-display.vercel.app/
- Product boundary: public projection console / four sample routes / consultant unlock
- Core boundary: Core not exposed
- Search boundary: no open SaaS search
- Display boundary: B displays public projection only
- Mobile gate: preserved
- DevTools easter egg: preserved
- Four routes: 李雨蓁 / 協昌 / 三恆一樹 / 屏東縣政府
- V8.1.3 state:
  - commit: 449b195
  - tag: display-v2.9V8.1.3-status-density-disabled-modules-patch
- Manual deploy: none
- Production untouched: expected no diff for index.html and data/*.json.

## B6.4P.2 Hero-to-Control Gap Micro Repair
- Reduced the excessive hero-to-operation vertical gap observed during Vercel preview visual QA.
- Root cause: the hero section used a viewport-height minimum that created extra blank space below the metric cards on taller screens.
- Repair applied: hero now uses content-height flow with a deliberate bottom breathing space, and the decorative hero haze height was reduced to match.
- Hero readability, Source & Model placement, AAI Mobile Terminal, logo true-color rendering, Chinese UI copy, operation deck, module cards, tables, payload, and filter logic untouched.
- Production untouched: expected no diff for index.html and data/*.json.

## B6.4P.3 DevTools Easter Egg Lock
- DevTools console now prints a compact cyberpunk temple-wall message through printDevtoolsEasterEgg().
- Message identifies AAI // Active Audit Intelligence, 4Force Lab, Sanitized Display Layer, Core / Display Boundary, and contact info@4force.com.tw.
- Console copy states that the mine is not here, the viewer is in the display layer, and frontend JSON only exposes public display structure plus sanitized display payload.
- It avoids raw payload dumps, object dumps, stack traces, and outdated B-series console wording.
- UI surface, hero spacing, mobile protection, payload, filter logic, and production files untouched.

## B6.5 Interaction / Filter Behavior Lock
- Interaction state is now routed through setActiveModule(), setSampleFilter(), clearFilters(), and sortMode.
- Module chip and module card switches clear activeSampleFilter and searchQuery before rendering the selected module, preventing hidden carryover between module views.
- Sample tags remain structured filters and do not write into the free-text search query.
- Clear filter actions reset activeSampleFilter and searchQuery while preserving the current active module, returning that module to its current display set.
- Reviewer / co-presence search and sample paths now include sample_case_numbers plus sample_cases, preserving case number and sample case coverage.
- Bid Preparation summary cards continue to recompute from filteredRows through computeBidSummary().
- Mobile layer protection, DevTools easter egg, Source & Model copy, logo lock, hero surface, payload, and production files untouched.

## B6.6 Demo Scenario / Sample Path Lock
- Operation layer now includes a SAMPLE PATH GUIDE beside the structured sample tags.
- Guide frames the page as Public Module Sample / AAI display layer and keeps the route commercial: Bid Preparation Module, Reviewer Composition Matrix, Co-presence View, Timeline Field Calculator, 供應商管理樣本路徑, 客戶訂製訊息範例, and Entity Data Management Example.
- Sample route counts are documented from the current display payload: 李雨蓁 Bid 12 / Co-presence 23, 協昌 Bid 10 / Co-presence 175, 三恆一樹 Bid 6 / Co-presence 8, 屏東縣政府 Bid 1042 / source scope 7653.
- Active module, active sample, result count, and filter mode remain visible below the guide.
- B6.5 interaction behavior preserved: sample tags stay structured, module switches clear sample/search state, clear filters returns the current module to its current display set, and sort option values remain unchanged.
- Reviewer / co-presence payload, sample_case_numbers search support, Bid Preparation filteredRows summaries, mobile protection, DevTools easter egg, Source & Model copy, and production files untouched.

## B6.7 First Machine Release Candidate
- Browser title updated from the previous dry-fit label to B6.7 RC Dry-Fit; visible hero, brand, logo, Source & Model, and operation layout remain unchanged.
- RC readiness check confirms B6.5 interaction lock and B6.6 sample path guide remain intact.
- Demo sample routes remain stable from the current display payload: 李雨蓁 Bid 12 / Co-presence 23, 協昌 Bid 10 / Co-presence 175, 三恆一樹 Bid 6 / Co-presence 8, 屏東縣政府 Bid 1042 / source scope 7653.
- Reviewer / co-presence payload keeps sample_case_numbers and sample_cases search support, plus the future X/Y matrix direction.
- Bid Preparation summary cards continue to recompute from filteredRows.
- Mobile layer protection, DevTools easter egg, Chinese UI copy, Source & Model copy, and Core / Display boundary wording preserved.
- Production untouched: expected no diff for index.html, data/*.json, deployment config, source directories, public assets, and logo asset.

## B7.0 First Machine Final Dry-Fit Lock
- Browser title, hero eyebrow, and display-layer metric are locked to B7.0 Final Dry-Fit / 初號機 final dry-fit wording.
- This is a final dry-fit marker pass only: no layout rewrite, no new module, no new payload, no logo change, no Source & Model change, no mobile gate change, and no DevTools architecture wording change.
- B6.1-B6.7 preservation check remains intact: hero readability, true-color logo, stable hero-to-control gap, wide operation layer, SAMPLE PATH GUIDE, Chinese UI copy, split summaries, table hierarchy, and structured sample filters.
- Demo sample routes remain stable from the current display payload: 李雨蓁 Bid 12 / Co-presence 23, 協昌 Bid 10 / Co-presence 175, 三恆一樹 Bid 6 / Co-presence 8, 屏東縣政府 Bid 1042 / source scope 7653.
- Reviewer / co-presence payload remains a structured preview with sample_case_numbers and sample_cases search support, preserving the future X/Y matrix direction.
- Bid Preparation summary cards continue to recompute from filteredRows.
- Production untouched: expected no diff for index.html, data/*.json, deployment config, source directories, public assets, and logo asset.

## B7.1 Index Landing Candidate - Root Preview Entry
- Root index.html is promoted from the sealed B7.0 Final Dry-Fit standalone review artifact so the Vercel preview root can display the first-machine surface directly.
- Landing strategy: full standalone page promotion, not redirect-only; the review artifact remains preserved under /review.
- Root path normalization completed: logo references use assets/4force-logo.png instead of the review-relative parent path.
- B7.0 locks preserved in the root entry: browser title, hero eyebrow, B7 display-layer metric, hero readability, true-color logo, SAMPLE PATH GUIDE, Chinese UI copy, Source & Model, mobile layer protection, DevTools easter egg, structured sample filters, and co-presence direction.
- Sample route counts remain expected from the embedded display payload: 李雨蓁 Bid 12 / Co-presence 23, 協昌 Bid 10 / Co-presence 175, 三恆一樹 Bid 6 / Co-presence 8, 屏東縣政府 Bid 1042 / source scope 7653.
- Data/config/source/public/logo assets untouched; no manual deploy, no production alias, no Core or B-Prod changes.

## B7.1 Root Landing Visual Polish Pass
- Root entry identity refined with a compact Root Preview Entry marker beside the B7.0 dry-fit eyebrow.
- Hero-to-operation transition kept tight while preserving B7.0 hero readability, true-color logo rendering, Source & Model, and mobile terminal placement.
- SAMPLE PATH GUIDE copy now reads as a root preview entrance and clarifies the four structured sample routes without changing filter behavior.
- Control deck polish keeps Active Module, Sample Filter, Search Query, Result Count, and Filter Mode visible; reset copy is localized while the existing handler remains unchanged.
- Mobile layer protection is enforced at narrow viewport width so the root landing does not expose the operation layer on phone-sized screens.
- Data payload, Bid Preparation filteredRows summaries, reviewer/co-presence rows, future X/Y direction, and DevTools easter egg remain untouched.

## B7.2P Production Visual Observation Lock
- B7.2 Direct Main Root Entry is complete, and production root https://aai-display.vercel.app/ can open the first-machine surface directly.
- The root entry no longer requires the /review path for normal production viewing.
- User production root visual QA: running normally.
- User observed that the production root visual appears better than the local preview, with stronger glow and cyberpunk atmosphere on Vercel production.
- Possible interpretation: HTTP/CDN asset delivery, root path normalization, GPU compositing, browser rendering context, and font/rendering/cache differences may affect the final display surface.
- This observation becomes the visual baseline for later Display Pack Split work.
- Observation-only seal: no machine code change, no index change, no data change, no Core change, no deploy.

## B7.3 Module State Contract Lock
- Root module cards now use one display-layer state contract: Bid Preparation Module and Reviewer Composition Matrix are preview_connected; Custom Supplier Management Module and Timeline Field Calculator are preview_ready; Supplier Case Management Example, Custom Information Example, and Entity Data Management Example are contract_only.
- preview_connected modules retain the existing interactive tables, sample filters, result counts, and filteredRows summary behavior.
- preview_ready modules now open a commercial shell panel that explains authorized display-pack configuration without adding table data.
- contract_only modules now open a commercial sample panel that presents project-contract availability without looking broken or connected.
- Module switching still clears sample/search carryover, sample tags remain structured filters, Chinese UI copy remains in place, and root visual baseline is preserved.
- Reviewer / co-presence payload, sample_case_numbers support, future X/Y matrix direction, mobile layer protection, DevTools easter egg, logo path, Source & Model copy, data assets, Core, B-Prod, and deploy state remain untouched.

## B7.3.1 Timeline Status + Copy Micro Repair
- Timeline Field Calculator remains locked as preview_ready in the display-layer module state contract.
- preview_ready panels use the unified copy: 模組預覽已就緒 / Preview Shell Ready, with display-field configuration and preview payload pending language.
- contract_only panels use the unified copy: 模組契約已鎖定 / Contract Locked, with project-contract access pending language.
- Panel notes now distinguish display field count from connected preview data and commercial display samples from project-specific configuration.
- No data, asset, Core, B-Prod, deployment, table, summary, mobile gate, or DevTools behavior changed.

## B7.3.2 Demo Route Guide Copy Polish
- SAMPLE PATH GUIDE product copy is now DEMO ROUTE GUIDE / 展示路徑導引.
- The guide keeps Public Module Sample / AAI display layer but removes internal root-preview wording.
- Guide body now explains that sample tags provide structured demo routes in Chinese and English.
- No module state logic, sample counts, search/filter behavior, mobile gate, DevTools easter egg, data, assets, Core, B-Prod, push, or deploy changed.

## B7.4 Module Content Depth Pass
- Five non-connected module panels now include product-depth display cards for Purpose, Configurable Fields, Display Capabilities, and Access State.
- Custom Supplier Management Module and Timeline Field Calculator keep preview_ready status while presenting commercial preview-shell descriptions instead of empty-state wording.
- Supplier Case Management Example, Custom Information Example, and Entity Data Management Example keep contract_only status while presenting commercial sample descriptions instead of broken or unavailable behavior.
- Connected modules remain untouched: Bid Preparation Module keeps existing filteredRows summary behavior, and Reviewer Composition Matrix keeps co-presence payload and sample route support.
- No new data rows, no data source change, no Core connection, no B-Prod change, no manual deploy, and no Display Pack Split work.

## B7.5 Display Function Wiring Pass
- Payload inventory: index.html already contains 4,446 Bid Preparation rows and 7,653 Reviewer Composition Matrix rows. Safe display fields available in the root artifact include case number, case name, entity, method, award amount, announce date, bid deadline, preparation days, awarded vendor, reviewer matrix, sample case numbers, sample cases, support, share, and recent date.
- Timeline Field Calculator is wired as a display-layer calculation preview using existing Bid Preparation rows only. Current full-pool sanity: rows scanned 4,446, rows with date fields 4,446, rows with both date fields 4,309, computable intervals 4,269, min 0, avg 15.1, max 199.
- Custom Supplier Management Module is wired as a supplier/entity aggregation view using existing Bid Preparation and Reviewer Composition Matrix display rows only. Current full-pool sanity: source rows 8,695, entities detected 508, rows matched 8,695 before filters.
- Supplier Case Management Example, Custom Information Example, and Entity Data Management Example remain contract_only. Current index payload has partial public fields for future display packs but is not enough to open those modules as full connected views without project-specific display structure.
- No new rows, no external payload, no Core connection, no B-Prod change, no manual deploy, and no Display Pack Split work.

## B7.5.1 Connected Module Semantics + Sample Route Persistence Repair
- Timeline Field Calculator copy now describes the connected calculation as bid preparation days from announce_date to bid_deadline, while keeping the existing display-layer calculation preview and count sanity.
- Module card switching preserves the active sample route, clears only the free-text search query, keeps sort mode intact, and recomputes the selected module result count.
- Sample tag clicks remain structured route filters, clear the free-text search query, and apply to the current active module instead of becoming search text.
- Clear filter still removes both active sample and search query while keeping the current active module.
- Custom Supplier Management labels now distinguish related display rows from distinct case count through 關聯資料列數 / Related Row Count and 關聯案件數 / Related Case Count.
- Module states preserved: Bid Preparation Module, Reviewer Composition Matrix, Custom Supplier Management Module, and Timeline Field Calculator remain preview_connected; the three commercial sample modules remain contract_only.
- No new rows, no mock data, no Core connection, no B-Prod change, no manual deploy, and no Display Pack Split work.

## B7.5.2 State Persistence + Timeline Render Path Hard Repair
- Module card switching now preserves active sample route, manual search query, and sort mode; only active module changes before rows and result count are recalculated.
- Sample tag clicks still set the structured sample route and clear manual search, while clear filter removes both sample route and search without changing the active module or sort mode.
- Filter mode copy is now explicit: Sample + Search Filter, Sample Filter, Search Filter, or All Records.
- Timeline render path now uses bid preparation days copy throughout the connected module: 備標天數, average preparation days, shortest preparation days, longest preparation days, and computable preparation windows.
- Supplier entity cards keep bilingual semantic labels for related display rows, related agencies, distinct case count, and sample route match.
- Module states remain locked: four preview_connected modules and three contract_only modules. No new rows, no mock data, no Core connection, no B-Prod change, no commit, no tag, no push, and no deploy.

## B7.6 Cross-Module Dimension Bridge
- Added DIMENSION BRIDGE / 跨模組維度橋 to align the four preview_connected modules through shared display-layer dimensions: active route, related cases, related supplier/entity, related agency, co-presence rows, preparation window, and source scope.
- The bridge is derived only from existing sanitized display payload rows and updates with active sample route, manual search query, active module, and sort state.
- The 李雨蓁 sample route is supported across the four connected modules by including reviewer composition text in the Custom Supplier Management display-row filter path.
- Bid Preparation now states that bid rows provide the case and date foundation used by Timeline and Supplier context.
- Reviewer Composition Matrix keeps the co-presence table and adds a context note that co-presence rows align to active sample route and related supplier/entity context when available.
- Timeline Field Calculator now includes a Preparation Window summary above the table: shortest, average, longest, and related cases count.
- Custom Supplier Management purpose copy now frames the module as supplier/entity context across cases, agencies, co-presence rows, and bid preparation windows within the active display route.
- Supplier cards now expose Related Cases, Related Agencies, Co-presence Rows, Preparation Days Range, and Sample Route Match when those fields can be derived from the current display payload.
- No new rows, no mock data, no Core-like inference wording, no Core connection, no B-Prod change, no manual deploy, no commit, no tag, and no push.

## B7.7 Route Narrative Layer
- Base: B7.6 / e4516689490282092b9d515531a27de77df08d62.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Added ROUTE NARRATIVE / 路徑解讀 near DIMENSION BRIDGE so the root production surface explains how to read the active display route.
- Narrative clarifies that Search Query is the manual observation axis, Sample Filter is the structured demo route, and both can stack without changing the state persistence contract.
- Timeline reading is clarified as display-only bid preparation days from announce_date to bid_deadline, with amount and price linkage not connected in this stage.
- Supplier Management reading is clarified as relational context across cases, agencies, preparation windows, and co-presence rows, not a supplier card wall.
- Count reading is clarified for Related Row Count, Related Case Count, and Sample Route Match.
- Dimension Bridge reading is clarified as the shared display-layer alignment for Bid, Reviewer, Supplier, and Timeline across case, agency, supplier/entity, co-presence rows, preparation window, and source scope.
- No Core touch, no B-Prod touch, no data/assets/public/src/package/vercel touch, no manual deploy.
- Production QA target: https://aai-display.vercel.app/.

## B7.8 Interface Semantics Pass
- Base: B7.7 / 544b4ae4ce567900858c35f102ff4ecdc7283cfc.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- UI label updates: Search Query -> 搜尋欄位 / Search Field; Sample Filter -> 測試路徑 / Demo Route; Filter Mode -> 篩選狀態 / Filter State; Result Count -> 結果筆數 / Result Count; Active Module -> 目前模組 / Active Module.
- Route Narrative intro converted to a full-width reading entry: title, intro, then five compact cards.
- Narrative card copy compressed for Search Field, Demo Route, Timeline, Supplier Context, and Dimension Bridge.
- Card alignment and line-height received a micro repair so Chinese and English text read as separated lines without changing the layout system.
- No Core touch, no B-Prod touch, no data/assets/public/src/package/vercel touch, no manual deploy.
- Production QA target: https://aai-display.vercel.app/.

## B7.8.1 Narrative Copy De-AI Pass
- Base: B7.8 / 1bf1fc463c68e17eeed2e06b317f1c3cfa93ac5e.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Route Narrative card copy revised from negative explanatory wording into positive product-action wording.
- Removed negative free-search wording from the demo route copy.
- Removed vendor-card negative wording from the supplier context copy.
- Timeline card copy now reads announce_date to bid_deadline as a preparation window, with amount and price dimensions reserved for later linkage.
- No function changes, no layout restructuring, no Core touch, no B-Prod touch, no data/assets/public/src/package/vercel touch, no manual deploy.
- Production QA target: https://aai-display.vercel.app/.

## B7.8.2 Dimension Bridge Alignment Fix
- Base: B7.8.1 / 9e8c8eb5db2867e364c1f2fa4b4354718f6a82e8.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Fixed Dimension Bridge card vertical alignment so label and value content start from the top.
- Co-presence Rows long content no longer stretches the entire bridge row; it scrolls inside its own card when needed.
- Bridge cards now top-align label/value content and no longer use space-between spacing.
- No function changes, no data changes, no copy changes beyond report, no Core touch, no B-Prod touch, no data/assets/public/src/package/vercel touch, no manual deploy.
- Production QA target: https://aai-display.vercel.app/.

## B7.9 Route Dashboard Budget Direction Pass
- Base: B7.8.2 / ce720e1d03afdb9aa21f16ab7c86ed5ebadf4198.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Dashboard-first layout introduced under Search Field / Demo Route tags.
- Default route: 李雨蓁.
- Added Route Dashboard / 展示路徑總表.
- Added Budget Direction / 預算方向.
- Added Participated Tender List / 參與案件明細.
- Added Reviewer Co-presence Grid / 案件評委共現棋盤 preview.
- Added Statistical Observation Axes / 統計觀察軸 with exact statistical terms:
  - 完全共線性
  - 隨機性
  - 高群聚係數（High Clustering Coefficient）
  - Dirac Delta Function（狄拉克δ函數）
- Route Narrative moved down as support layer.
- No Core touch.
- No B-Prod touch.
- No data/assets/public/src/package/vercel touch.
- No manual deploy.
- Production QA target: https://aai-display.vercel.app/.

## Gate Result
- Production untouched check: no production diff expected.
- Banned terms scan expected: html_hits [] and md_hits_before_forbidden_section [].
- Preview URL: file:///Users/juantingwei/Documents/4Force-AI-Lab/aai-display-review-codex-b/review/v2-9-b6-0-cyberpunk-public-index-dry-fit.html

## Forbidden Copy Boundary
Review markdown must not duplicate raw blocked vocabulary.

The public preview copy must avoid legal-accusation vocabulary, criminal-judgment vocabulary, and public-label vocabulary that frames entities or cases as public harm signals.

The grep gate is maintained in execution commands, not duplicated as raw terms inside this review document.

Tracked review files should remain clean when scanned by the execution gate.

## B7.9S Shell Restore Prep Only
- Base workspace state: main / 8192cb6befa3c81259ca6ee217d7e5b33687e994.
- Visual shell baseline restored from B7.9 source on top of B7.8.2 Dimension Bridge Alignment Fix.
- Changed files prepared locally: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Old shell copy removed locally: legacy engine label, legacy version marker, legacy distribution wording, and hero mission slash line.
- B7.9 dashboard-first order preserved: hero, Search Field, Demo Route tags, Route Dashboard, Participated Tender List, Reviewer Co-presence Grid, then support layers.
- Default route preserved: 李雨蓁.
- Mobile Layer Protection preserved.
- DevTools easter egg preserved.
- Dimension Bridge alignment fix preserved.
- No data file change, no manifest change, no Core touch, no B-Prod touch, no commit, no tag, no push, and no manual deploy.

## B7.9S Shell Restore Seal + Public Projection Sync
- Previous local shell prep HEAD: 8192cb6befa3c81259ca6ee217d7e5b33687e994.
- Synced remote public projection data commit: 8b9645966f306a19a13c883a96dfd8351a6bf015.
- Local shell restore changes were preserved through stash, fast-forward sync, and clean restore.
- Changed files for shell seal: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Data and manifest updates remain from remote AG2 public projection; this seal does not modify them.
- B7.8.2 visual shell baseline remains restored.
- B7.9 dashboard-first route experience remains preserved with default route 李雨蓁.
- Mobile Layer Protection, DevTools easter egg, Source & Model copy, true-color logo treatment, and Dimension Bridge alignment remain preserved.
- No Core touch, no B-Prod touch, no manual deploy.
- Production QA target: https://aai-display.vercel.app/.

## V8 Alpha Frontend Naming Lock
- Base: B7.9S / 289d9d292f07f94ce85bc707fde65c4f43a48980.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Frontend product state renamed to AAI V8 Alpha / Public Projection Console.
- Hero badge updated to Alpha Surface.
- Hero subtitle updated to Signals already present, arranged for inspection.
- B7.9 dashboard-first route experience, default route 李雨蓁, sample tags, Participated Tender List, Reviewer Co-presence Grid, statistical terms, mobile gate, DevTools easter egg, Source & Model copy, and true-color logo treatment preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## V8 Alpha Product Status Row + Motto Restore Lock
- Base: V8 Alpha frontend naming lock / bb814831c023a3e219c48299c0c0b0e346dc811f.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Hero motto restored to CAIRN IN THE DARKPOOL and What's already there, arranged.
- Added product status row with Last Projection Update, Daily Miner, Public Projection Rows, Display Routes, and Data Boundary.
- Status row reflects AG2 public projection timestamp, active miner state, display row count, three public sample routes, and Public Projection Only boundary.
- B7.9 / V8 dashboard-first route experience, 李雨蓁 default route, 協昌 and 三恆一樹 sample tags, Participated Tender List, Reviewer Co-presence Grid, statistical terms, mobile gate, DevTools easter egg, Source & Model copy, and true-color logo treatment preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## V8 Alpha Absurdity Statement Panel Lock
- Base: V8 Alpha product status row lock / 4d2e0520abc07fae3b758d4af78cbb44efc0886d.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Added right-rail brand philosophy card below Source & Model and AAI Mobile Terminal.
- Statement title: Arrangement Against Absurdity.
- Statement body preserves the 4Force Lab forward-motion message, AAI route-viewing method, 公平、公評、公民, and the closing motto.
- Mobile Layer Protection remains restricted to the terminal surface only.
- B7.9 / V8 dashboard-first route experience, three public sample routes, 李雨蓁 default route, Reviewer Co-presence Grid, statistical terms, DevTools easter egg, Source & Model copy, and true-color logo treatment preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## V8 Alpha Consultant Unlock CTA + Source Semantics Sweep Lock
- Base: V8 Alpha Absurdity Statement Panel Lock / ffabf8953499c95ab1a516eb08217b6534dd7bc9.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Search placeholder updated to consultant unlock wording for designated route service.
- Added Contact / info@4force.com.tw CTA with mailto link.
- Product status row source semantics tightened: precise public row split removed from the top status surface.
- Public Projection Surface now reports Active with Sample routes only.
- Source semantics sweep completed for product-facing search and status-row copy; DevTools architecture boundary wording preserved as required.
- Absurdity statement panel, hero motto, V8 Alpha naming, Public Projection Console, dashboard-first route, three public sample routes, Reviewer Co-presence Grid, statistical terms, mobile gate, Source & Model copy, and true-color logo treatment preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## V8 Alpha Fourth Sample Route Lock
- Base: V8 Alpha consultant unlock CTA lock / a24407c20ca5202779da7f3f0dbade9bab5c49d7.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Confirmed 屏東縣政府 remains available through existing public projection rows and existing sample route logic.
- Product status row Display Routes updated to 4 public samples.
- Sample route guide now labels 李雨蓁 as person route, 協昌 as supplier route, 三恆一樹 as small-pool route, and 屏東縣政府 as agency route.
- Consultant unlock placeholder and Contact / info@4force.com.tw CTA preserved.
- Precise status-row source split remains removed.
- Absurdity statement panel, hero motto, V8 Alpha naming, Public Projection Console, dashboard-first route, Reviewer Co-presence Grid, statistical terms, mobile gate, DevTools easter egg, Source & Model copy, and true-color logo treatment preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## V8.1.3 Status Density + Disabled Module Chips Micro Patch
- Base: V8.1.2 Proposal Readability Pass / 4d72453775779537f517834476b80b6c0fc17753.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Product status row copy shortened while preserving five cards and label / value / note structure.
- Consultant Unlock Modules hint is contained inside the module capability panel.
- Module chips are disabled presentation chips with not-allowed cursor and unlock hover hint.
- Sample route chips remain interactive and the four public routes are preserved.
- Dashboard computation, sample route logic, Participated Tender List, Reviewer Co-presence Grid, Statistical Observation Axes, Demo Route Guide, Dimension Bridge, lower module cards, mobile gate, DevTools easter egg, Source & Model copy, hero motto, and bottom slogan preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## B V8.3 Fast Response Suppliers Pass
- Base head: 818d82d V8.2 Proposal Surface Seal.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Added Fast Response Suppliers / 快速反應供應商 as a display-layer grouping from existing public projection rows.
- Added Compressed Notice Window / 公告壓縮窗口 summary for route average window, shortest window, fast window case count, fastest supplier, and related co-presence rows.
- Added Calendar Pressure Strip / 時程壓力帶 with compact case, agency, supplier, announce, deadline, day count, and route match display.
- Uses existing public projection data embedded in the display page; no data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.3.1 Fast Response Data Floor + Copy Patch
- Base head: 27c9b2b9d0bf0657bab887cf44830ded0bc9ef8e.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Removed self-defense microcopy from the Fast Response panel.
- Fast Response display floor set to 3-14 days.
- 0 / 1 / 2 day edge values are excluded from front-stage ranking.
- Calendar Pressure Strip uses qualified 3-14 day windows only.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.4 Supplier Reviewer Heatmap + Seriation Pass
- Base head: 92ec75e9caebea9daa0ae68265398a1effc80550.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Added Supplier x Reviewer Heatmap / 供應商 x 審委熱力圖 using existing public projection rows only.
- Added reviewer column seriation by observed reviewer-supplier proximity.
- Added Reviewer Co-presence Grid seriation with symmetric row / column order and preserved cell values.
- Projection Update display date refreshed to 2026-05-29.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.4.1 Matrix Fold + Conditional Presence Pass
- Base head: 459345073b46f39415bed9c1e71aef4dc204cd90.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Added compact / expand viewport behavior for matrix sections.
- Supplier x Reviewer Heatmap keeps full matrix data inside a scrollable folded viewport.
- Reviewer Co-presence Grid uses the same folded viewport with sticky header and first column.
- Added Conditional Presence Matrix / 條件出現矩陣 beside the raw co-presence count view.
- Conditional Rate uses the column reviewer diagonal count as denominator.
- Conditional matrix is directional and not forced into symmetry.
- Diagonal cells are visually muted so off-diagonal comparison remains readable.
- Raw co-presence cell values are preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.4.2 Matrix Default Expanded + Supplier Companion Share Pass
- Base head: 3a82ca0f1f466008686e3d1a9f511666ac991b54.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Matrix sections now default to expanded view.
- Matrix overflow is handled by inner viewport and scroll containers.
- Sticky header and first column behavior preserved where browser support allows.
- Supplier x Reviewer Heatmap mode toggle added.
- Count View preserved.
- Reviewer Share / 審委占比 added.
- Supplier Share / 供應商伴隨率 added.
- Top Supplier-Reviewer Share / 供應商審委伴隨率排行 added.
- Selected Reviewer Presence Split deferred.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.4.3 Upper Overflow + Supplier Share Formula Repair
- Base head: a1ac50d16aac98965cb4671acf55cd09684fd239.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Upper Fast Response / Calendar overflow contained with safe grid and inner viewport handling.
- Calendar strip inner viewport added.
- Metric grid safe layout added.
- Supplier Share formula repaired to use qualified supplier case appearances as denominator.
- Supplier Share constrained to 0-100%.
- Reviewer Share confirmed 0-100%.
- Top Supplier-Reviewer Share list uses repaired share values.
- Lift / over-expected view deferred until expected denominator is defined.
- High Companion Cells deferred.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.4.4 Upper Panel Alignment + Conditional Matrix Reading Label
- Base head: 601776a15c54e9db44ab48e56147821e59c7871a.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Fast Response Suppliers and Calendar Pressure Strip panels now share aligned stretch layout.
- Shared viewport height applied to table and calendar strip inner viewports.
- Calendar strip remains inner vertical scroll.
- Fast Response table remains inner horizontal / vertical scroll.
- Conditional Presence Matrix reading label added.
- Conditional matrix column labels clarified as Appearing Reviewer / Given Reviewer.
- Conditional Rate denominator unchanged.
- Matrix raw values unchanged.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.4.4.1 Upper Overflow Regression Fix
- Base head: 6c696502f459fa9be844c4dd1215c4ea3f0ab044.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- V8.4.4 upper alignment regression identified in shared stretch layout and fixed viewport height.
- V8.4.3 upper containment rebuilt for Fast Response Suppliers and Calendar Pressure Strip.
- Fast Response table remains inside horizontal / vertical inner scroll.
- Calendar Pressure Strip remains inside vertical inner scroll.
- Page-level horizontal overflow removed by restoring safe grid containment and inner viewport bounds.
- Conditional Presence Matrix reading label preserved.
- Conditional matrix column labels preserved.
- Conditional Rate denominator unchanged.
- Matrix raw values unchanged.
- Supplier Share and Reviewer Share remain constrained to 0-100%.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Final git status before seal: modified allowed files only.
- Production QA target: https://aai-display.vercel.app/.

## B V8.4.5 GA Tracking Install
- Base head: 345a3d6f833649be40c0cac454d858b025591e8f.
- GA ID: G-Z9TV0B3TG1.
- Installed Google tag in index.html head.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- No UI, data, formula, route, matrix, mobile gate, or DevTools changes.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## B V8.5 AG3 Presence Contrast Surface
- Base head: 6ff3e79cab1c0ce63daa2fdc97bf79f0fb1e48e6.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Added Presence Contrast Board / 在場對照板.
- Added Companion Drop Surface / 伴隨落差表面.
- Added Compressed Notice × Budget Band / 壓縮公告 × 預算帶.
- Added Initial Reviewer Group display-layer label.
- AG3 presence rows with denominator below 12 are excluded from the main display table.
- Imported only display-ready aggregate subset from AG3 projection references.
- GA tracking preserved.
- V8.4.4.1 upper overflow containment preserved.
- Supplier Share and Reviewer Share bounds preserved.
- Conditional Presence Matrix reading label preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- No A/Core touch.
- No C/Ops Ledger touch.
- Manual deploy: none.
- Semantic gate result: pass.
- Mobile gate preserved.
- DevTools easter egg preserved.
- Production QA target: https://aai-display.vercel.app/.

## V8.1.2 Proposal Readability Pass
- Base: V8.1.1 Route Guide Slogan Text Patch / dee31517565d99b23c1ea9b4d0aed0ee6029cbb1.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Hero metrics and product status cards now use clearer vertical label/value/note alignment for proposal reading.
- Module chip row is presented as 顧問解鎖模組 / Consultant Unlock Modules while preserving existing module chip behavior.
- Sample Tags retain the four public routes, with the proposal-page clear button removed from that row.
- Route Dashboard budget, tender direction, preparation window, co-presence row, and supplier distribution cards now use proposal-facing display copy.
- Participated Tender List, Reviewer Co-presence Grid, Statistical Observation Axes, Demo Route Guide, Dimension Bridge, route identity profiles, lower module cards, mobile gate, DevTools easter egg, Source & Model copy, consultant unlock CTA, hero motto, and bottom slogan preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## V8.1.1 Demo Route Name + Brand Slogan Text Patch
- Base: V8.1 Route Identity Text Patch / e4b434581fe6e276f3402e762448f8c202dfcb08.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Demo Route Guide now displays 李雨蓁 as the sole route name for the person sample.
- Footer product-state words replaced with the brand slogan: Insight × Strategy × Creativity × Execution.
- Hero motto, dashboard route identity profiles, sample route logic, mobile gate, DevTools easter egg, Source & Model copy, consultant unlock CTA, and true-color logo treatment preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.

## V8.1 Route Identity Text Patch
- Base: V8 Alpha Fourth Sample Route Lock / 72f9e66ab10dc8d65ab28fae7bc6a3e2f715148a.
- Changed files: index.html and review/B6_0_CYBERPUNK_PUBLIC_INDEX_DRY_FIT.md.
- Added display-safe route identity profiles for the four public sample routes.
- 李雨蓁 now displays person / reviewer / official with position 屏東縣政府勞動暨青年發展處處長.
- 協昌 and 三恆一樹 now display supplier route with role 得標廠商 / 供應商.
- 屏東縣政府 now displays agency route with role 採購機關 / public agency.
- Other routes continue to use existing display-field fallback behavior.
- Sample route logic, dashboard computation, Reviewer Co-presence Grid, statistical terms, mobile gate, DevTools easter egg, consultant unlock CTA, Source & Model copy, and true-color logo treatment preserved.
- No data, manifest, assets, package, lockfile, vercel, Core, or B-Prod touch.
- Manual deploy: none.
- Production QA target: https://aai-display.vercel.app/.
