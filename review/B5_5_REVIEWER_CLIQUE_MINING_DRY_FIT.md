# v2.9-B5.5 Reviewer Clique Mining (Dry Fit)

## Objective
Upgrade from B5.4's two-person Co-occurrence Network to a multi-person (3+) Reviewer Clique Mining (委員組合支持度) module. The goal is to discover sets of reviewers (cliques) that frequently co-occur in procurement evaluation committees, establishing empirical baselines for group-level support and observation clusters.

## Data Sources
- **Primary:** `data/preview/g40c_reviewer_records.json`
- **Secondary:** `data/preview/g40c_case_reviewer_summary.json`
- **Read-only Reference (if needed):** `data/preview/g40b_lifecycle_display_enriched.json`

## Metric Definitions & Formulas

Let $c$ be a specific case, $R(c)$ be the set of reviewers for $c$, and $A(c)$ be the set of reviewers who actually attended $c$.
Let $G$ be a specific group (clique) of reviewers.

1. **Group Case Support**  
   The total number of cases where the entire group $G$ is part of the committee.
   $$ \text{group\_case\_support}(G) = \text{count}(\{c \mid G \subseteq R(c)\}) $$

2. **Group Attended Support**  
   The total number of cases where the entire group $G$ was present (attended).
   $$ \text{group\_attended\_support}(G) = \text{count}(\{c \mid G \subseteq A(c)\}) $$

3. **Group Non-Chief Support**  
   The total number of cases where the entire group $G$ was present, excluding any ex officio chief reviewers (e.g., 處長, 局長, 主任).
   $$ \text{group\_non\_chief\_support}(G) = \text{count}(\{c \mid G \subseteq \text{reviewers\_without\_chief}(c)\}) $$

## Constraints & Parameters
- **Group Size:** $|G| \ge 3$ (The clique must consist of at least 3 reviewers).
- **Support Threshold:** $\text{group\_attended\_support}(G) \ge 5$ (Must co-attend at least 5 times).
- **Window:** All historical data (no rolling window initially).

## Vocabulary & Terminology Policy

**Allowed Terms (Neutral / Analytical):**
- Reviewer Clique Support
- Reviewer Group Support
- Group Case Support
- Group Attended Support
- Non-Chief Support
- Observation Cluster
- Signal Tier
- Priority Bucket

**Banned Terms (Subjective / Accusatory):**
- risk score
- critical
- danger
- illegal
- corruption
- 護航
- 黑箱
- 派系

## UI / Output Concept (To be Implemented)
- A new view mode or dedicated module for `Reviewer Clique Mining`.
- Tabular display of frequent cliques sorted by `Group Attended Support`.
- Support for filtering out cliques that strictly rely on internal chief reviewers.
- Drill-down capability to list the exact shared cases for a selected clique.
