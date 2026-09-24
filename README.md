# Biomaterial Scaffold Design for Tissue Engineering — Data & Code Repository

Supporting repository for: **"Cross-Material Design Strategies in Hydroxyapatite-, Chitosan-, and Polycaprolactone-Based Scaffolds: A Systematic Review of Biological Performance and Evidence Quality"** (submitted to *Biomaterials and Biosystems*).

This repository accompanies the manuscript's Data Availability statement and provides the full extraction dataset, risk-of-bias assessment, reporting checklists, and the complementary text-mining analysis code underlying the review's 78 included studies.

## Contents

| File | Description |
| --- | --- |
| `Supplementary_Table_S1_Extraction_Matrix.csv` | Full per-study extraction matrix for all 78 included studies (materials, modification strategy, experimental design, qualitative/quantitative results). |
| `Supplementary_Table_S2_Bias_Indicators.csv` | Approximate, non-validated reporting-completeness indicator (0-4) per study. Not a formal risk-of-bias assessment (see Table S5 for that). |
| `Supplementary_Table_S3_MxSxTxOxE_Matrix.csv` | Material x Strategy x Tissue-Application x Outcome x Evidence-Type matrix for all 78 included studies. |
| `Supplementary_Table_S4_Concentration_Response_19_Studies.csv` | Concentration-level detail (levels tested, reported optimum) for the 19 studies underlying the non-monotonic concentration-response pattern (manuscript Section 3.5). |
| `Supplementary_Table_S5_Risk_of_Bias_QUIN_SYRCLE.xlsx` | Formal risk-of-bias assessment for all 78 included studies: QUIN (12-item tool) for the in vitro component and SYRCLE (10-domain tool) for the in vivo/CAM component, identity-verified against each study's full text, with a second independent blinded assessor for reliability (see manuscript Discussion). |
| `Data_Dictionary_Supplementary_Tables.md` | Column-by-column definitions for Tables S1-S4, plus known open items. |
| `Search_Strategy_Log_Scopus_WebOfScience.md` | Full, literal Boolean search strings for both databases and both question-specific blocks (Q1, Q2), with record counts and translation notes. |
| `Deduplication_Log.md` | Methodology and record-count accounting for the three-pass deduplication process (564 -> 495 unique records). |
| `PRISMA_2020_Checklist.md` | Completed PRISMA 2020 27-item reporting checklist, mapped to manuscript sections, with open items stated explicitly. |
| `PRISMA-S_Checklist.md` | Completed PRISMA-S (search reporting extension) checklist, mapped to manuscript sections. |
| `nlp_analysis/pipeline_Q3_BioBERT_5ejes.ipynb` | Full executable notebook for the Section 4 (Q3) analysis: BioBERT embeddings, UMAP/HDBSCAN topic modeling via BERTopic, biomedical named-entity recognition, and the five content-axis co-occurrence networks. Run with a fixed random seed (seed = 33) for reproducibility. |
| `nlp_analysis/Reporte_Metodologico_Q3.pdf` | Methodology narrative for the Q3 pipeline (hyperparameters, validation diagnostics). |
| `nlp_analysis/Reporte_5_Ejes_Analisis_Red.pdf` | Full results report for the five content-axis networks, including per-axis findings and the source network visualizations. |
| `nlp_analysis/networks/` | Final network visualizations for all five content axes (Material/Composition, Fabrication Strategy, Engineering Property, Biological Function, Tissue Application), each as both `.png` and vector `.pdf`, filtered to the most highly connected nodes for legibility (Gephi). |
| `LICENSE` | CC BY 4.0 (Creative Commons Attribution 4.0 International). |

## Reproducibility notes

- The Section 4 (Q3) text-mining analysis is run with a fixed random seed (seed = 33 across NumPy, UMAP, and HDBSCAN); an independent re-run using the provided notebook and corpus should reproduce the same topic assignments, cluster boundaries, and entity-network structure reported in the manuscript. This directly supersedes an earlier, non-seeded version of the analysis, which is acknowledged in the manuscript as a resolved limitation.
- The reporting-quality indicator in Table S2 is an approximate, non-validated screening heuristic distinct from a formal risk-of-bias tool. A formal risk-of-bias assessment (QUIN for in vitro studies, SYRCLE for in vivo/CAM studies) has been applied to all 78 included studies and is provided in `Supplementary_Table_S5_Risk_of_Bias_QUIN_SYRCLE.xlsx`, with a second independent, blinded assessor confirming the overall risk judgement for every study.
- Full-text accessibility was applied as a Stage 2 eligibility criterion (manuscript Section 2.4); 37 of 124 records assessed for eligibility were excluded on this basis (manuscript Table 3). No sensitivity analysis comparing these 37 unretrieved records against the 78 included studies has been performed; this remains an open item (see `PRISMA_2020_Checklist.md`, item 13f).
- The network files in `nlp_analysis/networks/` are visual renders (PNG/PDF) produced from the underlying co-occurrence data, filtered for legibility. The raw, unfiltered graph data files (`.gexf`, as referenced in the manuscript) are not yet included in this repository; if you need the complete unfiltered networks for independent reanalysis, please contact the corresponding author.

## Open items before this repository is submission-ready

1. Raw search exports (Scopus and Web of Science, Q1 and Q2) have not been added and are not currently assembled; they are available from the corresponding author upon reasonable request.
2. A record-level deduplication log (the actual list of removed duplicate DOIs) has not yet been added; `Deduplication_Log.md` currently documents the *method* and the *record counts* reported in the manuscript, not a row-by-row log, since the raw search exports were not available when this file was built.
3. The raw, unfiltered `.gexf` network data files for the five Q3 content axes are not yet included (only filtered visual renders are provided; see Reproducibility notes above).
4. Consider archiving a versioned snapshot of this repository (e.g., via Zenodo) and citing its DOI in the manuscript, per common journal data-availability requirements — this has not yet been done.
5. No independent, dual-reviewer full-text screening or eligibility re-assessment has been performed (single-reviewer screening, acknowledged as a limitation in the manuscript, Section 2.7 and Discussion).

## Citation

If you use this dataset, please cite the manuscript (citation to be finalized upon acceptance/publication in *Biomaterials and Biosystems*).

## License

This repository is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — see `LICENSE` for the full text. You may reuse, adapt, and redistribute any material here, including commercially, provided you give appropriate credit.
