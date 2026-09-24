# Data Dictionary — Supplementary Tables S1-S4

Corresponds to: Biomaterial Scaffold Design for Tissue Engineering / *Cross-Material Design Strategies in Hydroxyapatite-, Chitosan-, and Polycaprolactone-Based Scaffolds*. Study identifiers (`P##`, `W##`) are internal extraction codes, not the manuscript's `ref##` bibliography numbers; a full `Study_ID` <-> `ref##` crosswalk for the 19 studies discussed in Section 3.5 is provided in Table S4 (columns `Ref_in_manuscript` and `Extraction_Study_ID`). A crosswalk for the remaining 59 studies has not yet been built (see open item at the end of this file).

## Supplementary Table S1 — Full Extraction Matrix (`Supplementary_Table_S1_Extraction_Matrix.csv`)

One row per included study (n = 78).

| Column | Description |
| --- | --- |
| `Study_ID` | Internal extraction code (`P##` or `W##`). |
| `Title_Authors_Year` | Short citation: first author(s), year, title fragment, journal abbreviation. |
| `Material(s)` | Principal focus material(s) as extracted (free text; may include secondary materials in parentheses). |
| `Modification_Strategy` | Free-text description of the design/modification strategy applied. |
| `Experiment_Summary` | Free-text summary of the experimental design (methods, models, assays used). |
| `Qualitative_Results` | Free-text summary of non-numeric findings. |
| `Quantitative_Results` | Free-text summary of numeric findings (percentages, concentrations, statistical values), where reported. |
| `Relevance_Conclusion` | Author's note on why the study is relevant to Q1 and/or Q2, and any caveats. |
| `Sub_Question` | Which review sub-question(s) the study informs: `Q1`, `Q2`, or `Q1+Q2`. |

## Supplementary Table S2 — Reporting-Quality / Bias Indicator (`Supplementary_Table_S2_Bias_Indicators.csv`)

One row per included study (n = 78). This is an approximate, non-validated reporting-completeness indicator (see manuscript Discussion, Limitations) -- **not** a formal risk-of-bias assessment. It is conceptually distinct from the QUIN/SYRCLE risk-of-bias tools referenced in the Discussion as future work.

| Column | Description |
| --- | --- |
| `Study_ID` | Internal extraction code, matches Table S1. |
| `Reports_variability_SD_SE` | `True`/`False` -- whether the study reports a measure of variability (SD or SE) alongside its key quantitative outcome. |
| `Reports_comparison_or_control` | `True`/`False` -- whether an explicit comparison or control group is reported. |
| `Reports_statistical_significance` | `True`/`False` -- whether a statistical significance test/value (e.g., p-value) is reported. |
| `Reports_numeric_value_with_units` | `True`/`False` -- whether at least one quantitative outcome is reported with explicit units. |
| `Risk_Score_0to4` | Simple count (0-4) of how many of the four elements above are `True`. Higher = more completely reported; NOT a study-design quality score. |

Verified: 1/78 studies score 4/4, 36/78 score 2-3, 41/78 score 0-1 -- matches the counts cited in the manuscript's Discussion section exactly (cross-checked against this file on 2026-09-20).

## Supplementary Table S3 — Material x Strategy x Tissue x Outcome x Evidence-Type Matrix (`Supplementary_Table_S3_MxSxTxOxE_Matrix.csv`)

One row per included study (n = 78). Referenced in manuscript Sections 3.2, 3.4, and the Discussion.

| Column | Description |
| --- | --- |
| `Study_ID` | Internal extraction code, matches Table S1. |
| `Material` | Principal material(s), as in Table S1's `Material(s)` column. |
| `Strategy` | The modification/design strategy applied (free text, generally matches Table S1's `Modification_Strategy`). |
| `Tissue_Application` | Target tissue category. Observed values: `bone` (26), `general/not specified` (40), `vascular` (4), `nerve/neural` (3), `skin/wound` (2), `cancer/tumor` (2), `tendon` (1). **Note:** the manuscript's Results (Section 3.4) and Discussion previously cited only bone/tendon/skin-wound/neural/vascular/general-target, omitting the 2-study `cancer/tumor` category; this has been corrected in the manuscript text (Section 3.4) to read "...alongside a vascular cluster (4/78) and cancer/tumor-therapy contexts (2/78)..." so the tissue breakdown now sums to 78. |
| `Outcome_Summary` | Free-text summary of the study's relevance/outcome, generally matches Table S1's `Relevance_Conclusion`. |
| `Evidence_Type` | **Important naming note:** despite the "Evidence-Type" name (inherited from the matrix's title), this column records whether the study met the Stage 2 (full-text) eligibility PASS criterion via `"quantitative value reported"` or via `"explicit comparison (no exact value)"` (see manuscript Section 2.4). It does **not** record in vitro vs. in vivo evidence tier. The in-vitro-only vs. in-vivo-validated split reported in Section 3.4 (49/78 vs. 29/78) is a separate classification not currently captured as its own column in this table -- see open item below. |

## Supplementary Table S4 — Concentration-Response Detail for the 19 Studies in Section 3.5 (`Supplementary_Table_S4_Concentration_Response_19_Studies.csv`)

One row per study cited in the non-monotonic concentration-response pattern (n = 19).

| Column | Description |
| --- | --- |
| `Ref_in_manuscript` | The `\cite{refXX}` bibliography key used in the manuscript text. |
| `Extraction_Study_ID` | The corresponding `Study_ID` in Tables S1-S3 (crosswalk). |
| `Citation_short` | Author(s), year, journal. |
| `Material_system` | The material/system in which the concentration variable was tested. |
| `Concentration_variable` | What was varied (e.g., "ZnO content (wt%)"). |
| `Levels_tested` | The specific levels/range tested, where extractable. |
| `Reported_optimum` | The level identified as optimal, where applicable. |
| `Outcome_summary` | Free-text summary of the reported effect. |
| `Fit_to_non-monotonic_concentration-response_pattern` | `CONFIRMED` (clear multi-level dose series with an intermediate optimum), `CONFIRMED (moderate)` (dose series present but non-monotonicity less explicit), or `FLAGGED` (does not show a clear chemical-concentration series in the extraction -- may be a design/geometric/fabrication-parameter series instead, or a citation that does not fit this pattern). |
| `Notes_for_author_review` | Specific recommendation for author follow-up on flagged rows. |

## Open items for a future revision of this data dictionary

- A `Study_ID` <-> `ref##` crosswalk covering all 78 studies (not just the 19 in Table S4) has not been built. This would require matching each Table S1 `Title_Authors_Year` entry against the manuscript's `\bibitem` list -- mechanical but not yet done.
- Tables S1-S3 do not currently have an explicit `Evidence_Tier` column (in vitro only / in vivo-validated) matching the 49/78 vs. 29/78 split reported in the manuscript text (Section 3.4). If this split was derived by hand from the full texts rather than from a column in these tables, consider adding one for full auditability.
