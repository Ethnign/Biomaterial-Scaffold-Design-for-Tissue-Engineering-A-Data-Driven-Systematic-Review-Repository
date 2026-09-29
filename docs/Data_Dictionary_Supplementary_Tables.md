# Data Dictionary — Supplementary Tables S1-S5

Corresponds to: *Cross-Material Design Strategies in Hydroxyapatite-, Chitosan-, and Polycaprolactone-Based Scaffolds: A Systematic Review of Biological Performance and Evidence Quality*. Study identifiers (`P##`, `W##`) are internal extraction codes, not the manuscript's `ref##` bibliography numbers; a full `Study_ID` <-> `ref##` crosswalk for the 19 studies discussed in Section 3.5 is provided in Table S4 (columns `Ref_in_manuscript` and `Extraction_Study_ID`). A crosswalk for the remaining 59 studies has not yet been built (see open item at the end of this file).

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

One row per included study (n = 78). This is an approximate, non-validated reporting-completeness indicator (see manuscript Discussion, Limitations) -- **not** a formal risk-of-bias assessment. It is conceptually distinct from the QUIN/SYRCLE risk-of-bias tools in Table S5.

| Column | Description |
| --- | --- |
| `Study_ID` | Internal extraction code, matches Table S1. |
| `Reports_variability_SD_SE` | `True`/`False` -- whether the study reports a measure of variability (SD or SE) alongside its key quantitative outcome. |
| `Reports_comparison_or_control` | `True`/`False` -- whether an explicit comparison or control group is reported. |
| `Reports_statistical_significance` | `True`/`False` -- whether a statistical significance test/value (e.g., p-value) is reported. |
| `Reports_numeric_value_with_units` | `True`/`False` -- whether at least one quantitative outcome is reported with explicit units. |
| `Risk_Score_0to4` | Simple count (0-4) of how many of the four elements above are `True`. Higher = more completely reported; NOT a study-design quality score. |

Verified: 1/78 studies score 4/4, 36/78 score 2-3, 41/78 score 0-1 -- matches the counts cited in the manuscript's Discussion section.

## Supplementary Table S3 — Material x Strategy x Tissue x Outcome x Evidence-Type Matrix (`Supplementary_Table_S3_MxSxTxOxE_Matrix.csv`)

One row per included study (n = 78). Referenced in manuscript Sections 3.2, 3.4, and the Discussion.

| Column | Description |
| --- | --- |
| `Study_ID` | Internal extraction code, matches Table S1. |
| `Material` | Principal material(s), as in Table S1's `Material(s)` column. |
| `Strategy` | The modification/design strategy applied (free text, generally matches Table S1's `Modification_Strategy`). |
| `Tissue_Application` | Primary target-tissue category, one label per study. Current values (verified against this file): `bone` (40), `general/not specified` (20), `skin/wound` (5), `nerve/neural` (5), `cartilage` (4), `vascular` (2), `bladder` (1), `tendon` (1). Sums to 78 and matches the tissue-distribution sentence in manuscript Section 3.4. |
| `Tissue_Application_Secondary` | Second target-tissue label, populated only for studies whose scaffold was explicitly designed or evaluated for a **second, distinct anatomical/functional application** rather than a single primary target (addresses reviewer Comment 2). Empty string for the other 76 studies. Populated for 2 studies: `P06` (`nerve/neural` -- a spatially patterned, two-region PCL scaffold with one region carrying osteogenic markers and the other neurogenic markers, an explicit dual-tissue design) and `W40` (`cancer/tumor` -- a PCL-gold-nanosphere scaffold explicitly designed for both photothermal ablation of bone-cancer cells and regeneration of healthy bone tissue; also discussed in manuscript Section 3.4). **Deliberately conservative scope:** angiogenesis/vascularization reported as a *supporting biological outcome* for a study's primary tissue target (e.g., a bone scaffold whose bioactivity is partly demonstrated via a pro-angiogenic or CAM assay) is **not** coded as a secondary `vascular` application -- this follows the reviewer's own illustrative caution (a biological function is not automatically a distinct tissue application) and was checked against a keyword-based re-screen of all 78 studies' Table S1 free text (13 additional candidates were identified and manually reviewed; all 11 not listed above were confirmed as false positives -- e.g., "osteosarcoma" cell-line names, "bone marrow"-derived cell sources, or explicit "not bone"/"outside of bone" phrasing in the source text -- and are not coded as secondary applications). |
| `Outcome_Summary` | Free-text summary of the study's relevance/outcome, generally matches Table S1's `Relevance_Conclusion`. |
| `Evidence_Type` | **Important naming note:** despite the "Evidence-Type" name (inherited from the matrix's title), this column records whether the study met the Stage 2 (full-text) eligibility PASS criterion via `"quantitative value reported"` or via `"explicit comparison (no exact value)"` (see manuscript Section 2.4). It does **not** record in vitro vs. in vivo evidence tier -- see `Experimental_Model`/`In_vivo`/`CAM` below for that. |
| `Experimental_Model` | One of `In vitro only` (51 studies), `In vivo` (25 studies, a live-animal model -- rat, mouse, rabbit, or pig), or `CAM` (2 studies, a chick chorioallantoic-membrane / in-ovo assay, which is neither purely in vitro nor a full live-animal study). Derived directly and only from which studies have a Table S5 `SYRCLE_in_vivo` row (27 studies) versus only a `QUIN_in_vitro` row (all 78 studies get QUIN; 51 do not additionally get SYRCLE); the 2 CAM studies were identified from the SYRCLE sheet's own free-text `Notes` column (explicit "CAM" / "chorioallantoic membrane" / "in-ovo" wording) rather than assumed. In vitro (51) + in vivo (25) + CAM (2) = 78, and in vivo + CAM (27) matches the "27 studies with an in vivo or CAM component" figure in manuscript Sections 3.4 and the Discussion/Limitations exactly. Addresses reviewer Comment 3's request for this column. |
| `In_vivo` | `Yes`/`No` -- `Yes` only for the 25 studies with a genuine live-animal component; `No` for the 2 CAM-only studies and the 51 in-vitro-only studies. Kept as a separate boolean column (alongside the categorical `Experimental_Model` above) so that "in vivo" and "CAM" can each be filtered independently, per reviewer Comment 3. |
| `CAM` | `Yes`/`No` -- `Yes` only for the 2 chick chorioallantoic-membrane studies (`W65`, `W69`); `No` otherwise. |

## Supplementary Table S4 — Concentration-Response Detail and Categorization for the 19 Studies in Section 3.5 (`Supplementary_Table_S4_Concentration_Response_19_Studies.csv`)

One row per study screened for the concentration-response pattern discussed in manuscript Section 3.5 (n = 19). Addresses reviewer Comment 1.

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
| `Fit` | `CONFIRMED` for the 14 studies that reflect a genuine chemical/compositional concentration series (regardless of which `Response_Category` they were ultimately assigned, see below), or a `FLAGGED - ...` reason for the 5 studies excluded from the categorization because they do not reflect a concentration series at all (a single-formulation study, a fabrication/mounting-frame design, a Taguchi process-parameter design-of-experiments study, or a geometric groove-size comparison). |
| `Response_Category` | The per-study response-shape classification requested by reviewer Comment 1, assigned by re-examining each of the 14 `CONFIRMED` studies against the same outcome, experimental time point, and tested concentration series. Values: `Non-monotonic (confirmed)` (3 studies -- a tested level exists both below and above the reported interior optimum), `Non-monotonic (tentative)` (4 studies -- an intermediate/low-moderate level performed best, but not every level on both sides of the optimum is itemized in the extraction, or the effect is confounded with a second co-varied factor), `Best result at studied boundary` (2 studies -- the best outcome is at the highest or lowest concentration tested, not an interior point), `Composition/architecture comparison`, `Composition/formulation comparison`, and `Composition comparison` (1 study each, 3 total -- these three labels all describe the same underlying category, a comparison between distinct formulations/architectures/additive identities rather than a single-variable dose series, and should be read as equivalent pending a follow-up pass to unify the label text), `Trade-off between outcomes` (2 studies -- different outcomes are each optimized at a different concentration), and `Excluded` (the 5 `FLAGGED` studies, not further categorized). Counts: 3 + 4 + 2 + 1 + 1 + 1 + 2 + 5 = 19. Only 7 of the 19 (3 confirmed + 4 tentative) are actually non-monotonic; this is the authoritative classification referenced by manuscript Section 3.5, which no longer describes all 14 `CONFIRMED` studies uniformly as "non-monotonic." |
| `Category_Notes` | One-sentence, study-specific justification for the `Response_Category` assigned, written to be independently checkable against `Levels_tested`/`Reported_optimum`/`Outcome_summary` in the same row. |

## Supplementary Table S5 — Risk-of-Bias Assessment (QUIN / SYRCLE) (`Supplementary_Table_S5_Risk_of_Bias_QUIN_SYRCLE.xlsx`)

Two sheets. Addresses reviewer Comment 3.

**`QUIN_in_vitro`** -- one row per included study (n = 78; header occupies rows 1-3, data starts row 4). Columns: `Study_ID`, `Reference (short citation)`, `Q1`-`Q12` (the 12 QUIN items, each `Yes`/`No`/`Unclear` -- three-level scale; see revision notes below), `Overall risk judgement (assessor's judgement)` (`Low risk`/`Some concerns`/`High risk`, assigned by an explicit threshold: `Some concerns` only when at least 8 of the 12 items are `Yes`, `High risk` otherwise), `Notes` (free-text justification, including the specific reporting gaps driving the rating). QUIN was developed and validated for in vitro dental-material studies; it is applied here, without modification to its items, to the in vitro component of each of the 78 studies (see manuscript Discussion/Limitations for the adaptation caveat this implies).

**`SYRCLE_in_vivo`** -- one row per study with an in vivo or CAM component (n = 27; same header layout). Columns: `Study_ID`, `Reference (short citation)`, `D1`-`D10` (the 10 SYRCLE domains, each `Yes`/`No`/`Unclear`, except `D4` which is `N/A` for the 2 CAM studies -- see below), `Overall risk judgement (assessor's judgement)` (assigned by the same threshold logic: `Some concerns` only when at least 4 of the applicable domains are `Yes`, `High risk` otherwise), `Notes`. The `Notes` column is also the source used to derive Table S3's `Experimental_Model`/`In_vivo`/`CAM` columns: 25 of these 27 rows describe a live-animal model (rat, mouse, rabbit, or pig) and 2 (`W65`, `W69`) explicitly describe a chick chorioallantoic-membrane / in-ovo assay rather than a full live-animal study; for these 2 rows, `D4` (random housing, which presumes a live-animal housing environment) is marked `N/A` rather than `Yes`/`No`/`Unclear` and is excluded from that row's Yes-count and overall judgement.

**Revision note (2026-09-29a):** this table originally used a three-level `Yes`/`No`/`Unclear` item scale, matching the independent QUIN/SYRCLE assessments in progress by two additional raters (for a planned Cohen's kappa), who were believed at the time to be using a binary `Yes`/`No` scale instead. To keep all three assessments comparable, this table was revised to binary: every `Unclear` item was recoded to `No` (i.e., anything short of an explicit, reported confirmation is `No`), except the `D4`/CAM cases above, which are a genuine not-applicable case rather than an unreported one. Recoding surfaced an unrelated data-quality issue: a number of studies sharing an identical or near-identical item-level profile had received different `Overall risk judgement` values under the original, purely qualitative assignment. This was resolved by adopting the explicit, uniform threshold described above and re-deriving every study's overall judgement from it, which changed 17 QUIN studies and 3 SYRCLE studies from `Some concerns` to `High risk` (none changed to or from `Low risk`). Counts at that point: QUIN 71 `High risk` / 7 `Some concerns` (was 54/24); SYRCLE 25 `High risk` / 2 `Some concerns` (was 22/5).

**Revision note (2026-09-29b, supersedes 2026-09-29a's scale choice):** the assumption above was incorrect for one of the two other raters: the completed assessment received from Juan García (father) in fact uses the original three-level `Yes`/`No`/`Unclear` scale, not binary. Since `Unclear` (insufficient information to judge) and `No` (explicitly confirmed absent) are a real methodological distinction -- not just a labeling nuance -- and the practical reason for binarizing (comparability for Cohen's kappa) no longer held once a three-level rater turned up, the item-level data in this table was reverted to the original three-level values (`Yes`: 503, `No`: 358, `Unclear`: 75 for QUIN; `Yes`: 40, `No`: 11, `Unclear`: 217, `N/A`: 2 for SYRCLE). The `D4`/`N/A` exception for the 2 CAM studies is unaffected by this reversion. Because the explicit Yes-count threshold rule depends only on how many items are `Yes` (not on whether the remaining items are `No` or `Unclear`), re-deriving `Overall risk judgement` from the restored three-level data reproduces the exact same 20-study reclassification and the same final counts as the binary version: QUIN 71 `High risk` / 7 `Some concerns`; SYRCLE 25 `High risk` / 2 `Some concerns`. No numeric result reported in the manuscript changed as a result of this reversion.

Both sheets record a single `Overall risk judgement` per study per tool (assigned by the primary assessor); a second, blinded assessor independently repeated the full assessment, under the original three-level scale and prior to the threshold correction above, and reached the same overall judgement as the first assessor for every study under both tools (see manuscript Discussion/Limitations). Item-level (per-question/per-domain) ratings from the second assessor are not included as separate columns in this file, so a formal item-level concordance statistic (e.g., Cohen's kappa) cannot currently be computed from this file alone; this is recorded as an open item below.

## Open items for a future revision of this data dictionary

- A `Study_ID` <-> `ref##` crosswalk covering all 78 studies (not just the 19 in Table S4) has not been built. This would require matching each Table S1 `Title_Authors_Year` entry against the manuscript's `\bibitem` list -- mechanical but not yet done.
- The three composition-comparison labels in Table S4's `Response_Category` (`Composition/architecture comparison`, `Composition/formulation comparison`, `Composition comparison`) describe the same category under three slightly different strings; a follow-up pass should unify them to one label.
- Table S3's `Tissue_Application` value `general/not specified` (20 studies) includes at least one materials-characterization study (`W60`, a fish-bone-derived hydroxyapatite/bioceramic comparison) whose reported outcomes (osteoconductivity, apatite formation) are bone-specific proxies even though the study itself does not test an in vivo or tissue-specific application; whether this and similar cases should be recoded from `general/not specified` to `bone` was not decided during this pass and is flagged here for author review rather than changed unilaterally.
- Table S5's two `Overall risk judgement` columns record only the primary assessor's final judgement per study per tool; the second assessor's full item-level ratings (used to confirm agreement at the overall-judgement level, per the manuscript's Discussion/Limitations) are not themselves included as columns here, so Cohen's kappa cannot yet be computed from this file. Adding the second assessor's per-item ratings (e.g., as parallel `D1_R2`...`D10_R2` / `Q1_R2`...`Q12_R2` columns, one set per tool) would make full item-level inter-rater reliability directly computable from this file once that data is available.
