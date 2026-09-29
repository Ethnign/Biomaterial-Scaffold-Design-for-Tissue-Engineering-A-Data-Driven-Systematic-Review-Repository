# PRISMA 2020 Checklist

**Manuscript:** Cross-Material Design Strategies in Hydroxyapatite-, Chitosan-, and Polycaprolactone-Based Scaffolds: A Systematic Review of Biological Performance and Evidence Quality
**Target journal:** Biomaterials and Biosystems

This checklist follows the PRISMA 2020 statement (Page et al., 2021, *BMJ* 372:n71). "Location" refers to the section/page of `Full_Draft_Paper_LaTeX_v3.tex`. Where an item is not addressed, this is stated explicitly rather than omitted, consistent with the manuscript's own disclosed limitations.

| # | Item | Location in manuscript | Reported? |
|---|---|---|---|
| 1 | Title: identify the report as a systematic review | Title | Yes |
| 2 | Abstract: see PRISMA 2020 for Abstracts checklist | Abstract | Yes (structured narrative abstract; see note below) |
| 3 | Rationale: describe the rationale in the context of existing knowledge | Introduction, para. 1-3 | Yes |
| 4 | Objectives: explicit statement of objectives/questions | Introduction (Q1, Q2, Q3) | Yes |
| 5 | Eligibility criteria | Section 2.4 | Yes |
| 6 | Information sources, incl. dates last searched | Section 2.5 ("last executed in August 2026"); Scopus and Web of Science only | Yes, but limited to two databases (declared limitation, Sections 2.7 and Discussion) |
| 7 | Full search strategies for all databases | Section 2.5, Table 1; full literal strings also in `Search_Strategy_Log_Scopus_WebOfScience.md` (repository) | Yes |
| 8 | Selection process: number of reviewers, independence, automation tools | Sections 2.6, 2.7; single reviewer for both Stage 1 and Stage 2 | Reported, but **not independent dual screening** (declared limitation) |
| 9 | Data collection process: number of reviewers, independence | Section 2.6 | Single reviewer (same limitation as item 8) |
| 10a | Data items: outcomes sought | Section 2.6; Supplementary Table S1/S3 | Yes |
| 10b | Data items: other variables sought | Section 2.6 | Yes |
| 11 | Risk of bias assessment methods (tools, reviewers, independence) | Discussion, Limitations paragraph; Supplementary Table S5 | Yes — QUIN (in vitro) + SYRCLE (in vivo/CAM), all 78 studies, with a second blinded assessor for reliability |
| 12 | Effect measures | — | **Not applicable**: no meta-analysis was performed; the review reports a narrative/descriptive synthesis, not pooled effect sizes |
| 13a | Synthesis methods: process for grouping studies | Section 3 intro; Supplementary Table S3 | Partially — grouping logic (material/strategy/tissue/outcome) is described but no formal pre-specified synthesis protocol is stated |
| 13b | Synthesis methods: data preparation (missing data, conversions) | — | **Not reported** — open item |
| 13c | Synthesis methods: tabulation/visual display | Tables 4-6, Supplementary Table S3/S4 | Yes |
| 13d | Synthesis methods: synthesis method and rationale; meta-analysis details | — | **Not applicable / not reported** — no meta-analysis; no explicit justification of why narrative synthesis (vs. meta-analysis or a formal Synthesis-Without-Meta-analysis, SWiM, framework) was chosen. Flagged as an open item. |
| 13e | Methods to explore heterogeneity | — | **Not reported** |
| 13f | Sensitivity analyses | — | **Not reported** — in particular, no sensitivity analysis was performed comparing the 37 unretrieved full texts against the 78 included studies |
| 14 | Reporting bias assessment methods | — | **Not reported** — publication/reporting bias is not formally assessed |
| 15 | Certainty assessment methods (e.g., GRADE) | — | **Not applicable / not performed** — no formal certainty-of-evidence framework was applied across outcomes |
| 16a | Study selection results, ideally with flow diagram | Figure 1 (PRISMA flow diagram), Table 2 | Yes |
| 16b | Studies that appeared eligible but were excluded, with reasons | Table 3 | Yes |
| 17 | Cite each included study and its characteristics | Bibliography (refs 1-78); Supplementary Table S1 | Yes |
| 18 | Risk of bias for each included study | Supplementary Table S5 | Yes |
| 19 | Results of individual studies | Sections 3.2-3.4 (narrative); Supplementary Table S1/S3 | Yes (narrative/tabular, not forest plots — no meta-analysis) |
| 20a | Summary of characteristics/risk of bias contributing to synthesis | Discussion, Limitations paragraph | Yes |
| 20b | Results of statistical syntheses | — | **Not applicable** — no meta-analysis performed |
| 20c | Investigations of heterogeneity | — | **Not reported** |
| 20d | Sensitivity analyses | — | **Not reported** (see item 13f) |
| 21 | Risk of bias due to missing results | Discussion, Limitations (availability-bias paragraph) | Partially — the risk is acknowledged narratively but not formally assessed with a dedicated method |
| 22 | Certainty of evidence per outcome | — | **Not applicable / not performed** |
| 23a | General interpretation in context of other evidence | Discussion | Yes |
| 23b | Limitations of the evidence | Discussion, Limitations paragraph | Yes |
| 23c | Limitations of the review process | Discussion, Limitations paragraph; Section 2.7 | Yes |
| 23d | Implications for practice/policy/future research | Discussion; Conclusion | Yes |
| 24a | Registration information | — | **Not registered.** This review was not prospectively registered (e.g., PROSPERO); this is not currently stated in the manuscript and should be added explicitly, with a brief justification (e.g., scope as a recent-evidence update rather than a full historical review). |
| 24b | Protocol availability | — | **No protocol was prepared or made available.** Should be stated explicitly in the manuscript rather than left silent. |
| 24c | Amendments to registration/protocol | — | Not applicable (no protocol registered) |
| 25 | Sources of financial/non-financial support | Declarations, "Funding" | Yes ("received no external funding") |
| 26 | Competing interests | Declarations | Yes |
| 27 | Availability of data, code, and materials | Declarations, "Data Availability"; GitHub repository | Partially — extraction tables, RoB assessment, and (pending upload) the Q3 analysis notebook are available; raw search exports and a versioned/DOI'd release are not yet available (open repository items) |

## Notes for the authors

1. **Items 24a/24b are the clearest gap**: the manuscript currently does not state anywhere whether the review was registered or whether a protocol exists. PRISMA 2020 requires an explicit statement either way — "this review was not prospectively registered" is an acceptable, honest answer, but it must be written into the manuscript (recommended location: end of Section 2.1, Protocol and Reporting Standard).
2. **Items 12-15 and 20b-22 (effect measures, meta-analysis, certainty assessment)** are marked "not applicable" on the assumption that this review does not intend to perform a quantitative meta-analysis. If that is correct, consider adding one sentence in Section 2 explicitly stating that a narrative synthesis was chosen instead of meta-analysis, and why (heterogeneity of outcomes/designs) — this directly satisfies PRISMA item 13d and closes a point the independent peer-review report also raised.
3. **Items 13e/13f/20c/20d (heterogeneity, sensitivity analyses)** are open items consistent with what the independent review report flagged (in particular, no sensitivity analysis on the 37 unretrieved full texts). These remain honestly unresolved in this checklist rather than papered over.
4. **Item 2 (Abstract)** — PRISMA has a separate 12-item "PRISMA 2020 for Abstracts" checklist; this document does not reproduce it separately. If the target journal requires a structured abstract, that checklist should be completed against the final published abstract format.
