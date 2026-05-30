# V8 ALPHA Display Ammo Contract / 初號機展示彈藥規格

## Purpose

This document defines the public-safe display ammo required by the current B V8 ALPHA frontend shell.

B renders only. A/Core computes, cleans, orders, caps, and exports display ammo. B must not analyze raw rows, rebuild matrices from full pools, infer denominators, or reinterpret research projections as runtime route packs.

Baseline inspected:
- B HEAD: `293240290e927a67a0114f04834678f5766990f6`
- Stable visual tag: `display-v2.9V8-ALPHA-intelligence-skin-01`
- Main shell: `index.html`
- Current runtime refs:
  - `data/preview/ag5_4_route_dashboard_public_projection.json`
  - `data/preview/ag5_4_1_route_surface_aggregate_projection.json`
  - `data/preview/ag5_4_3_route_display_semantics_corrected_projection.json`
  - `data/preview/ag5_7_route_partition_projection.json`
  - `data/local_static_pack/local_projection_pack.json`
  - `data/preview/ag6_2_rfb_public_projection_pack.json`
  - `data/preview/g40g_awarded_vendor_reviewer_clique_support.json`

## B Render Rules

- B renders only.
- B does not recompute.
- B does not infer denominator.
- B does not sort unless A provides ordered rows.
- B shows `pending`, `not_projected`, or `—` for explicit null status.
- B fails validation for missing required fields in core dashboard ammo.
- B never consumes raw rows, crawler output, API payloads, source evidence, full text, or full pool.
- B only consumes public-safe display ammo.
- B must keep Matrix Theater expanded, full-width, and out of appendix.
- B must preserve `source_count`, `display_count`, `cap`, `capped`, `basis`, and denominator labels when provided.

## A Output Rules

- A may hold raw / full pool / crawler / parser / computation.
- A must output public-safe display ammo.
- A must match B field names exactly.
- A must provide basis / denominator / cap labels.
- A must separate research projection from display ammo pack.
- A must not expect B to reinterpret aggregate research output as runtime route pack.
- A must provide ordered rows when the UI order matters.
- A must provide explicit status fields such as `not_projected`, `not_available`, or `insufficient_support` instead of leaving B to guess from blanks.

## LOCAL6 Lesson

LOCAL6 aggregate projection has value, but it is not V8 ALPHA main dashboard ammo.

The failure was not that A produced an aggregate projection. The failure was that B consumer logic connected aggregate projection into active route / dashboard main binding. Future aggregate projection may only appear as a side drawer, lab panel, consultant layer, or static appendix. It must not enter the main route dashboard pipeline unless A exports it as a public-safe display ammo pack with route runtime fields, denominators, caps, and explicit display slots.

## Section Contract Table

| Section | Current Display Slots | Current Source / Function | Required Ammo Fields | Basis Needed | Cap Needed | Current Gap | B Rule |
|---|---|---|---|---|---|---|---|
| Entry / Hero / Core Inscription | hero title, company, CTA, inscription, mobile gate | static HTML, `intelligenceInscription()`, DevTools block | `hero_copy`, `inscription_zh`, `inscription_en`, `contact`, `timestamp` | copy version basis | no cap needed | none for data; copy is static | render only; never bind raw data |
| Route Controls / Search / Demo Route | search input, sample route chips, active module, route tags | `searchQuery`, `activeSampleFilter`, `setSampleFilter()`, `renderFilterBar()` | `route_keys`, `route_labels`, `route_type`, `sample_route_enabled` | route key basis | routes 4 currently | controls depend on B state, not A ammo | B may switch display route; no recomputation |
| Route Dashboard | route, position, participated tenders, time span, budget direction, budget sum, tender direction, prep window, awarded vendors, reviewer distribution, co-presence rows, supplier distribution | `projectionMetricCards()`, `resolveRouteCard()`, `routeProjection.cards`, `routeProjection.source_counts`, `routeProjection.display_counts`, `routePartition.route_summary` | `participated_tenders`, `distinct_case_count`, `budget_sum`, `award_sum`, `compressed_notice_count`, `reviewer_copresence_rows`, `supplier_count`, `reviewer_count`, `route_match_basis`, `time_scope_label` | `case_count_basis`, `budget_basis`, `award_basis`, `match_basis`, `time_basis` | dashboard cards no row cap; counts must include source/display semantics | count labels can confuse source vs display if A omits basis | fail validation if required dashboard ammo missing |
| War-room Cockpit | active route, route type, direct core count, associated membership, budget sum, avg prep, top signal, stable fast | `renderWarRoomCockpit()`, `routePartition.route_summary`, `direct_route_core`, `associated_route_context`, `supplier_reviewer_share[0]`, `stable_fast_response[0]` | `route_key`, `route_type`, `direct_core_case_count`, `associated_context_case_count`, `budget_sum_direct_core`, `avg_prep_days`, `top_signal`, `stable_fast_response_top` | direct core basis, associated membership basis, route case basis | display cards only | top signal depends on first ordered row | A must order top signal; B must not choose |
| Fast Response / Stable Fast Response | stable supplier cards, fastest single case, qualified count, route presence, best / avg window, sample support | `renderPartitionFastResponsePanel()`, `stable_fast_response`, `fastest_single_cases`; fallback `renderFastResponsePanel()` | `stable_fast_response_cards`, `fastest_single_case`, `qualified_count`, `route_presence_count`, `best_notice_window_days`, `average_notice_window_days`, `support_bucket` | 3-14 day notice window basis, route presence denominator | display 12 stable rows, 8 fastest rows | fallback may compute from active rows; preferred ammo is AG5.7 partition | A orders stable rows; B renders compact table |
| Compressed Notice Window | qualified fast window cases, shortest, average, fastest responder, pressure strip | `renderAggregateFastResponsePanel()`, `route_fast_response`, `route_calendar_pressure`, `resolveCalendarPressureStrip()` | `compressed_notice_cases`, `median_prep_days`, `average_prep_days`, `prep_days_range`, `calendar_pressure_rows` | 3-14 day compressed window basis | pressure rows display 8, cap from pack | incomplete prep dates require explicit `not_projected` | B filters only explicit display rows; no price banding |
| Compressed Notice Budget Band Cards / 四橫卡 | budget band, cases, compressed, avg prep, median prep, display strength, top suppliers, top reviewer groups | `renderAG3PresenceSurfaces()`, `AG3_BUDGET_BAND_ROWS` static display rows | `compressed_notice_budget_bands`, `budget_band`, `case_count`, `compressed_notice_count`, `avg_prep_days`, `median_prep_days`, `top_suppliers`, `top_reviewer_groups` | budget band basis and compressed window basis | four or five bands, ordered by A | currently static, not route ammo | A must pre-compute bands; B must not bucket budgets |
| RFB Specification Fingerprint | RFB cases, clean term cases, requirement terms, rare terms, capped surface cases | `renderRfbFingerprintSurface()`, `ag6_2_rfb_public_projection_pack.route_surfaces` | `rfb_source_count`, `rfb_display_count`, `rfb_surface_cases`, `clean_term_case_count`, `top_requirement_terms`, `top_rare_terms` | RFB surface case basis, term extraction basis | cases display 10, cap 100 visible in metadata | route cases are RFB surface cases, not full route totals | B eats fingerprint result only |
| Rare Term Density | rare term chips, counts | `rfbTermCloud(surface.top_rare_terms)` | `rare_term_density`, `term`, `count`, `document_frequency`, `support_bucket` | capped RFB document basis | display 12 terms | no support status on every term | A should pre-rank and cap |
| Vendor Fingerprint Context | vendor / agency-vendor chip strip, case count, requirement terms, categories | `getRfbVendorSurface()`, `getRfbAgencyVendorSurface()`, `rfbCategoryLabel()` | `vendor_fingerprint_context`, `awarded_vendor`, `agency`, `case_count`, `top_requirement_terms`, `term_categories` | vendor route key and agency-vendor basis | compact chips; labels max 3 recommended | route match can be absent | B must not infer vendor context from raw case rows |
| Document Similarity | case pair, similarity %, shared requirement terms, vendor | `rfbRouteSimilarityPairs()`, `similarity_surfaces.route_pairs` | `document_similarity_rows`, `case_a`, `case_b`, `similarity`, `shared_clean_terms`, `vendor_a`, `vendor_b` | similarity basis and token basis | display 6 pairs | no route-specific pair may fallback to global | A must label route/global fallback |
| RFB Support Metrics | source/display/cap/capped, case count, clean term count | `rfbSurfaceMeta()`, `compactCountBadge()` | `rfb_support_metrics`, `source_count`, `display_count`, `cap`, `capped`, `pack_version` | public projection cap basis | no cap beyond metadata | metadata distributed across pack/surface | A should provide unified support object |
| Presence Contrast / Presence Top Gun | supplier, reviewer group, present, absent, delta, ratio, denominator, readiness, top contrast signal | `renderAG3PresenceSurfaces()`, `AG3_PRESENCE_CONTRAST_ROWS` | `presence_top_entity`, `present_count`, `absent_count`, `companion_delta`, `contrast_ratio`, `denominator`, `readiness_label` | present/absent group basis, denominator basis | main table denominator >=12, top 7 visible | static agency scope; not route-aware | A computes Top Gun; B renders only |
| Companion Drop Surface | supplier cards, present/absent bars, delta, denominator | `renderAG3PresenceSurfaces()`, top 5 filtered rows | `companion_drop_cards`, `supplier`, `present_count`, `absent_count`, `delta`, `denominator` | shared denominator scale basis | display 5 cards | bar scale max denominator local to card set | A may provide scale max; B should not re-rank |
| Ceiling Proximity / Ceiling Top Gun | supplier, cases, median fit, 95+ count/share, 98+ count/share, display strength, top budget signal | `renderAG4BudgetFitSurfaces()`, `AG4_CEILING_PROXIMITY_ROWS` | `ceiling_top_vendor`, `case_count`, `median_fit`, `fit_95_count`, `fit_98_count`, `display_strength` | award / budget ratio basis | display current rows, A ordered | static list with supplier-key prioritization | A computes; B may prioritize matching supplier only if explicit |
| Award-to-Budget Rhythm | supplier, dominant fit band, band count, band share, cases, strength | `renderAG4BudgetFitSurfaces()`, `AG4_CEILING_PROXIMITY_ROWS` | `award_budget_rhythm_cards`, `dominant_fit_band`, `band_count`, `band_share`, `case_count` | fit band basis | display current rows | dominant band assumed 98_to_100 in B | A should output dominant band explicitly |
| Participated Tender Evidence Strip | case, title, agency, budget, prep days, awarded vendor, method, reviewers | `renderProjectionTenderTable()`, `routeProjection.tables.participated_tenders`; fallback `tenderTable` | `participated_tenders`, `case_no`, `title`, `agency`, `budget`, `prep_days`, `awarded_vendor`, `procurement_method`, `reviewers_compact` | route case basis | display 30 from AG5.4 | procurement method often missing | A must include method status |
| Supplier x Reviewer Heatmap | supplier labels, reviewer columns, count, reviewer coverage, supplier co-presence rate | `renderPartitionSupplierReviewerHeatmap()`, `supplier_reviewer_share`; fallback `renderSupplierReviewerHeatmap()` | `supplier_reviewer_heatmap`, `row_labels`, `column_labels`, `cells`, `count`, `reviewer_share`, `supplier_share`, `matrix_basis` | supplier route presence denominator, reviewer route presence denominator | suppliers 12, reviewers 12 | fallback still builds from active rows when partition absent | A should export ready matrix; B must not rebuild for core route |
| Reviewer Co-presence Grid | raw count matrix, diagonal self count, seriated order | `renderAggregateCoPresenceMatrixPanel()`, `route_co_presence_matrix`; fallback `coPresenceMatrixFromProjection()` | `reviewer_copresence_matrix`, `row_labels`, `column_labels`, `cells`, `self_count`, `co_presence_count`, `seriation_order` | reviewer appearance basis | nodes / cells cap from AG5.4.1 | fallback can still derive from capped rows | A should output matrix cells and order |
| Conditional Presence Matrix | conditional rate matrix, denominator label, support threshold behavior | `renderAggregateCoPresenceGrid(mode='conditional')`, `conditional_presence_pairs`; fallback `renderCoPresenceMatrixPanel()` | `conditional_presence_matrix`, `conditional_probability`, `given_count`, `co_presence_count`, `support_level`, `threshold_pass` | P(row reviewer appears \| column reviewer appears), column denominator | matrix cells cap from aggregate pack | low support spikes require A threshold flags | B shows only threshold-pass rates |
| Top Conditional Presence Pairs | appearing reviewer, given reviewer, raw co-presence, given count, conditional rate, support | `renderAggregateConditionalPairs()`, `resolveConditionalPresencePairs()`; fallback `renderConditionalPairs()` | `top_conditional_pairs`, `row_reviewer`, `column_reviewer`, `co_presence_count`, `given_count`, `conditional_rate`, `support_level` | conditional denominator basis | display 10 pairs | fallback can include thin 1/1 if not thresholded | A must remove low-support false peaks |
| Statistical Observation Axes | four static terms | static DOM in `renderProjectedRouteDashboard()` / `renderRouteDashboard()` | `statistical_observation_axes` optional static labels | no denominator | no cap needed | static explanatory copy | B can keep static; no A ammo required |
| Core Matched Awarded Vendors | vendor, awarded cases, budget exposure, agencies, sample/latest case, route | `renderProjectedAwardedVendorTable()`, `routeProjection.tables.awarded_vendors`; fallback `renderAwardedVendorTable()` | `awarded_vendor_distribution`, `vendor_name`, `case_count`, `budget_sum`, `award_sum`, `latest_case_date`, `latest_case_title`, `appearance_share`, `case_coverage`, `support_bucket` | distinct case and route match basis | AG5.4 display 20 | latest may be representative, not latest | A must label sample vs latest |
| Awarded Vendor Distribution | awarded vendor card/table inside outcome layer | same as above plus `awardedVendorSummary()` fallback | same as above | appearance denominator and case coverage denominator | rows 20 / display 12 fallback | fallback sums from active rows | Prefer A ordered distribution |
| Reviewer Distribution | reviewer, identity, count, appearance share, case coverage, suppliers, cases | `renderProjectedReviewerDistributionTable()`, `routeProjection.tables.reviewer_distribution`, semantics overlay; fallback `renderReviewerDistributionTable()` | `reviewer_distribution`, `reviewer_name`, `appearance_count`, `related_case_count`, `appearance_share`, `case_coverage`, `latest_date`, `identity_tag`, `support_bucket` | appearance share denominator, case coverage denominator | AG5.4 display 20, fallback 12 | share denominator can differ by source | A must provide both denominator labels |
| Direct Core Proof Table | case, title, agency, budget, award, prep days, vendor, method, match basis, reviewers | `renderPartitionDirectCoreProofTable()`, `routePartition.top_budget_cases` | `direct_core_proof_rows`, `case_no`, `title`, `agency`, `budget`, `award`, `announce_date`, `bid_deadline`, `prep_days`, `awarded_vendor`, `procurement_method`, `procurement_method_status`, `match_basis`, `reviewers_compact` | direct route core match basis | top 10 plus capped drawer | method often `—` through lookup | A must output `procurement_method_status` |
| Case Budget Reference List | source/display/cap badge, high budget route rows, same columns as proof | `renderPartitionDirectCoreProofTable()` currently labels this section | `case_budget_reference_rows`, `source_count`, `display_count`, `cap`, `capped`, `basis_text` | route budget reference basis | display 10 plus extra capped rows | currently shares function with proof table | A should separate proof rows from budget reference rows |
| Contract-only / Display Access Pending modules | module key, label, route, status, depth cards, access mode | `modules`, `public_modules`, `moduleContract()`, `renderCards()`, `renderStateCard()` | `module_status`, `module_key`, `status`, `label`, `description`, `access_state` | module contract basis | no cap needed | preview_ready vs contract_only copy can confuse data readiness | Contract-only modules never pretend data exists |
| Appendix / Method / Source Scope | dimension bridge, route narrative, source model, footer, timestamp | `renderDimensionBridge()`, `renderRouteNarrative()`, static footer | `source_scope`, `method_scope_copy`, `footer_timestamp`, `contact` | source scope basis | no cap needed | mostly static | no raw/source internals |
| DevTools easter egg requirements | public projection only, sanitized display layer, no raw rows, core boundary | `printDevtoolsEasterEgg()` | `devtools_copy` optional | architecture-safe copy basis | no cap needed | static | never expose method or engine internals |

## Dashboard Ammo

Required B dashboard ammo:

- `participated_tenders`
- `distinct_case_count`
- `budget_sum`
- `award_sum`
- `compressed_notice_count`
- `reviewer_copresence_rows`
- `supplier_count`
- `reviewer_count`
- `route_match_basis`
- `time_scope_label`

Basis labels required:

- `case_count_basis`: distinct case basis, direct-core case basis, or display-row basis.
- `budget_basis`: distinct case budget sum; must state whether missing / invalid budgets are excluded.
- `award_basis`: distinct awarded case sum; must state award coverage.
- `match_basis`: agency, supplier, reviewer, person, direct core, or associated context.
- `time_basis`: earliest/latest source date fields used.

## Fast Response / Compressed Notice Ammo

Required ammo:

- `fastest_single_case`
- `stable_fast_response_cards`
- `compressed_notice_cases`
- `median_prep_days`
- `average_prep_days`
- `prep_days_range`
- `compressed_notice_budget_bands`

Rules:

- Four horizontal budget-band cards must be computed by A.
- B must not bucket prices.
- B displays 3-14 day compressed notice rows only when A exports them as display rows or explicitly marks qualified rows.
- B must not show 0 / missing / invalid money as `0`; A should export `not_projected` or null status.

## RFB Ammo

Required ammo:

- `rfb_source_count`
- `rfb_display_count`
- `rare_term_density`
- `vendor_fingerprint_context`
- `document_similarity_rows`
- `rfb_support_metrics`
- `rfb_case_budget_reference_rows`

Rules:

- B does not consume full text.
- B only consumes fingerprint result.
- RFB raw / text / full document does not enter B.
- RFB route cases are RFB surface cases, not complete route totals.
- A must export capped representative cases and similarity pairs.

## Top Gun Ammo

Presence Contrast:

- `presence_top_entity`
- `present_count`
- `absent_count`
- `companion_delta`
- `contrast_ratio`
- `denominator`
- `readiness_label`
- `companion_drop_cards`

Ceiling Proximity:

- `ceiling_top_vendor`
- `case_count`
- `median_fit`
- `fit_95_count`
- `fit_98_count`
- `display_strength`
- `award_budget_rhythm_cards`

Rules:

- A computes all Top Gun picks.
- B only displays.
- B does not choose top signal on the fly unless A has not yet exported display ammo; future pack should eliminate fallback selection.

## Matrix Theater Ammo

Required ammo:

- `supplier_reviewer_heatmap`
- `reviewer_copresence_matrix`
- `conditional_presence_matrix`
- `top_conditional_pairs`
- `statistical_observation_axes`
- `row_labels`
- `column_labels`
- `matrix_basis`

| value_type | Display Rule |
|---|---|
| count | integer |
| share | 0-100% |
| lift | may exceed 100%, label as Lift |
| delta | percentage point |
| conditional_probability | 0-100%, basis required |

Rules:

- B does not build matrix from full rows.
- B does not change row-column order.
- B does not fold Matrix Theater by default.
- B does not move Matrix Theater to right rail or appendix.
- A must provide support thresholds for conditional probability and top pairs.

## Vendor / Reviewer Distribution Ammo

Awarded Vendor Distribution:

- `vendor_name`
- `case_count`
- `budget_sum`
- `award_sum`
- `latest_case_date`
- `latest_case_title`
- `appearance_share`
- `case_coverage`
- `support_bucket`

Reviewer Distribution:

- `reviewer_name`
- `appearance_count`
- `related_case_count`
- `appearance_share`
- `case_coverage`
- `latest_date`
- `identity_tag`
- `support_bucket`

Definitions:

- Appearance Share = 出現次數占比.
- Case Coverage = 覆蓋案件占比.
- B does not guess denominator.

## Direct Core Proof Table Ammo

Required row fields:

- `case_no`
- `title`
- `agency`
- `budget`
- `award`
- `announce_date`
- `bid_deadline`
- `prep_days`
- `awarded_vendor`
- `procurement_method`
- `procurement_method_status`
- `match_basis`
- `reviewers_compact`

Rule:

If A cannot project `procurement_method`, A must export:

```json
{"procurement_method_status": "not_projected"}
```

B must not use plain `—` to hide a missing method state.

## Case Budget Reference Ammo

Required fields:

- `source_count`
- `display_count`
- `cap`
- `capped`
- `case_budget_reference_rows`
- `basis_text`

Row fields:

- `case_no`
- `title`
- `agency`
- `budget`
- `award`
- `prep_days`
- `awarded_vendor`
- `procurement_method`
- `match_basis`
- `reviewers_compact`

Positioning:

Case Budget Reference is route budget reference. It is not the signal judgment body. A should order a high-budget capped sample. B only displays.

## Module Status Ammo

Required fields:

- `module_key`
- `status`
- `label`
- `description`

Recommended status values:

- `active`
- `preview_connected`
- `contract_locked`
- `display_access_pending`
- `not_projected`

Rule:

Contract-only modules must not pretend they have data.

## Current Gap Top 5

1. `procurement_method` and `procurement_method_status` need explicit A projection. Current B lookup can show pending / dash.
2. Case Budget Reference and Direct Core Proof currently share one renderer and row source; A should separate proof rows from budget reference rows.
3. Supplier x Reviewer Heatmap still has fallback construction from capped active rows; future ammo should provide ready matrix cells and row/column order.
4. Presence Contrast / AG3 and Ceiling Proximity / AG4 are static display rows; future ammo should provide route-aware or explicitly scoped pack metadata.
5. Share / coverage values require explicit denominator labels everywhere; B must not infer from display row counts.

## A Next Step

A can produce a `v8_alpha_display_ammo_pack` using this contract.

Minimum pack shape:

```json
{
  "pack_type": "v8_alpha_display_ammo_pack",
  "pack_version": "v8-alpha-ammo-v0.1",
  "projection_scope": "public_display_ammo",
  "routes": [
    {
      "route_key": "李雨蓁",
      "dashboard_ammo": {},
      "fast_response_ammo": {},
      "rfb_ammo": {},
      "top_gun_ammo": {},
      "matrix_theater_ammo": {},
      "distribution_ammo": {},
      "direct_core_proof_ammo": {},
      "case_budget_reference_ammo": {},
      "module_status_ammo": {}
    }
  ],
  "boundary": {
    "contains_raw_rows": false,
    "contains_full_pool": false,
    "contains_full_text": false,
    "public_safe": true
  }
}
```

