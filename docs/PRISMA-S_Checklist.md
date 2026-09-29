# PRISMA-S Checklist (Search Reporting Extension)

**Manuscript:** Cross-Material Design Strategies in Hydroxyapatite-, Chitosan-, and Polycaprolactone-Based Scaffolds: A Systematic Review of Biological Performance and Evidence Quality
**Target journal:** Biomaterials and Biosystems

This checklist follows the structure of PRISMA-S (Rethlefsen et al., 2021, *Systematic Reviews* 10:39), which extends PRISMA 2020 item 7 (search strategy) with search-specific reporting detail. As with the PRISMA 2020 checklist, gaps are stated explicitly rather than omitted. "Location" refers to `Full_Draft_Paper_LaTeX_v3.tex` unless a repository file is named.

| # | Item | Location | Reported? |
|---|---|---|---|
| 1 | Database name(s) | Section 2.5: Scopus, Web of Science (Core Collection) | Yes |
| 2 | Multi-database searching acknowledged, incl. rationale for database choice | Sections 2.5, 2.7 (Limitations of the Search Strategy) | Yes |
| 3 | Study registries searched (e.g., ClinicalTrials.gov) | — | **Not applicable** — this review synthesizes published experimental/laboratory studies, not clinical trials; no trial registries were searched. This should be stated explicitly rather than left silent. |
| 4 | Websites/organizations searched | — | **Not searched / not reported.** Only bibliographic databases were used; no grey-literature websites or organizational sources were consulted. |
| 5 | Search platforms/interfaces (e.g., Scopus via Elsevier, WoS Core Collection via Clarivate) | Section 2.5 names the databases but not the specific platform/interface or subscription/access route | Partially — recommend adding platform/vendor and access route (e.g., institutional subscription) |
| 6 | Total records from each source reported individually | Table 1 (per-database, per-sub-question breakdown: Scopus 293, WoS 271) | Yes |
| 7 | Grey literature searched | — | **Not searched** |
| 8 | Citation searching (backward/forward, e.g., reference list screening, cited-by) | — | **Not performed / not reported** — no snowballing or citation-chasing step is described |
| 9 | Contacting authors/experts/manufacturers for additional studies or data | — | **Not performed.** This is directly relevant to the 37 full texts that could not be retrieved (Table 3): author contact is a standard mitigation the independent peer review specifically recommended and was not attempted. |
| 10 | Handsearching (e.g., specific journals, conference proceedings) | — | **Not performed** |
| 11 | Full, reproducible search strategies for every database (exact syntax, all lines) | Section 2.5 gives the base Boolean template and both question-specific blocks; full literal per-database strings are provided in the repository (`Search_Strategy_Log_Scopus_WebOfScience.md`) | Yes, via the repository file — recommend citing that file explicitly in Section 2.5 for a reader who only has the manuscript |
| 12 | Limits/restrictions used (e.g., language, date, document type) and justification | Section 2.5: English language, 2023-onward (PUBYEAR > 2022), document type "article" | Yes, with justification given for the date restriction |
| 13 | Search filters (e.g., validated methodological filters) | — | **Not applicable** — no pre-validated search filter (e.g., a Cochrane RCT filter) was used; the "question-specific blocks" (Q1/Q2 term sets) function as topic filters and are already fully reported (Section 2.5) |
| 14 | Prior work justifying search strategy design (e.g., a prior scoping search, expert consultation) | Section 2.3 (Focus Materials and Rationale) describes piloting of broader categorical searches that were discarded | Yes, partially |
| 15 | Update searches (if the search was re-run before submission) | Section 2.5 states searches "last executed in August 2026" | Yes (single search date given; no separate update-search step described, which is acceptable for a single-search review provided this is not implied otherwise) |
| 16 | Dates of searches for each database | Section 2.5 gives a single date (August 2026) for both databases jointly | Partially — recommend reporting the exact search date per database individually if they differ, or confirming both were run on the same date |
| 17 | Peer review of the search strategy (e.g., PRESS review) | — | **Not performed / not reported.** No independent peer review of the search strategy (e.g., a PRESS-style check) is described. |
| 18 | Total records retrieved from all sources, and deduplication method | Section 2.6 and Table 2: 564 total, 69 duplicates removed via a three-pass DOI-matching process (Section 2.6) | Yes, in detail |
| 19 | Deduplication tool/method (manual, software, or both) | Section 2.6: DOI-based matching, normalized and trimmed, in three sequential passes (automated matching plus a manual cross-reference pass) | Yes |

## Notes for the authors

1. **Items 3, 4, 7, 8, 9, 10, 17 are the clearest gaps**: no trial registries, grey literature, citation-chasing, author contact, handsearching, or independent search-strategy peer review were used. None of these are necessarily required for a review of this scope, but PRISMA-S expects an explicit statement either way (e.g., "Grey literature sources were not searched; this review is restricted to peer-reviewed bibliographic databases"), rather than silence. Adding one or two sentences to Section 2.5 covering items 3-4 and 7-10 would close this cheaply.
2. **Item 9 (contacting authors) is the highest-value fix**: since the independent peer-review report specifically flagged the 37 unretrieved full texts as a source of availability bias, even a brief statement that author contact was or was not attempted for these 37 records directly strengthens that part of the manuscript's Discussion.
3. Item 11's full per-database strings currently live only in the repository log file, not the manuscript itself — this is acceptable practice (many journals prefer search strings in supplementary material), but Section 2.5 should explicitly point the reader to that file by name, which it does not currently do.
