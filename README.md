# Biomaterial Scaffold Design for Tissue Engineering — Data & Code Repository

Supporting repository for: **"Cross-Material Design Strategies in Hydroxyapatite-, Chitosan-, and Polycaprolactone-Based Scaffolds: A Systematic Review of Biological Performance and Evidence Quality"** (submitted to *Biomaterials and Biosystems*).

## What this is

A systematic review (PRISMA 2020) of 78 studies on hydroxyapatite-, chitosan-, and polycaprolactone (PCL)-based tissue-engineering scaffolds. This repository holds the full per-study extraction data, the formal risk-of-bias assessment, PRISMA reporting checklists, the manuscript source, and the code and data for the complementary text-mining analysis (Section 4 of the manuscript).

**Research questions this repository's data and code address:**

- **Q1 / Q2** (answered from the manual extraction in `supplementary/Supplementary_Table_S1_Extraction_Matrix.csv` and `Supplementary_Table_S3`): what design/modification strategies are used with each material, and what biological performance do they produce?
- **Q3** (answered by the pipeline in `notebooks/`): what does entity co-occurrence network analysis reveal about the relative conceptual centrality of hydroxyapatite and PCL across five content axes, and what bridge concepts connect otherwise disconnected thematic sub-domains?

**The five content axes**, used throughout the Q3 analysis (topic classification, entity networks) and referenced across several supplementary tables, are non-exclusive (a single study/fragment can belong to more than one):

| Axis | What it captures |
| --- | --- |
| Material/Composition | Matrix, reinforcement, bioactive agent |
| Fabrication Strategy | How the scaffold was built or modified |
| Engineering Property | Measurable physical/mechanical characteristics |
| Biological Function | The biological effect produced |
| Tissue Application | Target tissue or organ |

## Folder structure

```
manuscript/       Manuscript source (.tex) and PDF, and the figures actually used in it.
data/
  raw/            Search-strategy and deduplication logs (see data/raw/README.md for what's not included: raw exports, full-text PDFs).
  processed/      Pipeline-derived intermediate data (topic/axis classification table).
notebooks/        Main pipeline notebook (Section 4/Q3), plus notebooks/legacy/ for the superseded, unseeded version.
src/              Reserved for pipeline functions gradually migrated out of the notebook (currently empty -- see src/README.md).
config/           Externalized pipeline parameters: five-axis keyword dictionaries, thresholds, entity-normalization rules.
results/
  networks/       The five complete, unfiltered co-occurrence networks (.gexf).
  figures/        Rendered network images not used as main-text figures, plus superseded_matplotlib/ (archived pre-Gephi renders).
  tables/         (currently empty; see docs/Figure_Table_Manifest.md for what each manuscript table is sourced from)
  metrics/        Run manifest (seed, recorded environment) for the Q3 pipeline.
supplementary/    Supplementary Tables S1-S5, the risk-of-bias assessor guide, and its blank template.
docs/             Data dictionary, PRISMA checklists, risk-of-bias process log, figure/table manifest, this reorganization's notes.
requirements.txt  Unpinned package list for the Q3 notebook.
CITATION.cff      How to cite this repository and the manuscript.
LICENSE           CC BY 4.0.
```

## Environment

- The Q3 pipeline notebook was developed and run on **Google Colab**; its saved kernel metadata records **Python 3.14.7**. Package versions were **not pinned** at the time these results were produced (see `results/metrics/run_manifest.json`) -- this is disclosed as an open reproducibility gap, not fixed retroactively.
- Install packages with `pip install -r requirements.txt` (unpinned names only, for the reason above). A GPU is used automatically if available (falls back to CPU) for the biomedical NER step.
- **Known gap:** the notebook reads and writes its inputs/outputs from hardcoded `/content/...` paths (Colab's local, ephemeral disk), not from a documented, centralized project root, and does not include a `drive.mount()`/download step. Running it therefore currently means uploading inputs directly into a Colab session's `/content/` at each of several points, rather than pointing it at a project folder. See `docs/REORGANIZATION_NOTES.md` (2026-09-30 addendum) for the specific fix recommended and why it was not done blind (no GPU/PDFs available to verify a rewrite would not break the pipeline).

## Main run-through (Section 4 / Q3 pipeline)

1. **Input:** the full-text PDFs of the 78 included studies (not included in this repository; see `data/raw/README.md`) plus `supplementary/Supplementary_Table_S1_Extraction_Matrix.csv` for study identity.
2. **Run:** `notebooks/pipeline_Q3_BioBERT_5ejes_CORREGIDO.ipynb`, top to bottom, with a fixed seed (33, set in an early cell). Stages: PDF text extraction and cleaning -> BioBERT embeddings -> UMAP dimensionality reduction + HDBSCAN clustering (hyperparameter search) -> BERTopic topic modeling -> five-axis topic classification (thresholds and dictionaries mirrored in `config/`) -> entity normalization (`config/entity_normalization_patterns.json`) -> biomedical NER (`d4data/biomedical-ner-all`) -> per-axis co-occurrence network construction.
3. **Output:** `data/processed/clasificacion_5ejes_topicos.csv` (topic -> axis classification), `results/networks/*.gexf` (five complete networks), and the centrality statistics reported in the manuscript's Table (`tab:q3axes`) and Section 4 text. Static renders (`manuscript/figures/*_gephi_crop.pdf`, `results/figures/*_gephi_crop.pdf`) were produced from the `.gexf` files in Gephi, a separate, manual, external step not scripted in the notebook.

See `docs/Figure_Table_Manifest.md` for the complete mapping of every manuscript figure and table (and every Supplementary Table) to its source file and how it was produced, including which results are deterministically reproducible from the notebook and which (S1-S5, the risk-of-bias assessment, the PRISMA diagram) are the product of manual expert judgement and are not.

## Data availability and what is not included here

- The raw Scopus/Web of Science search export files and the 78 included studies' full-text PDFs are **not** included (the latter for copyright reasons). Citations/DOIs for all 78 studies are in Supplementary Table S1; raw exports are available from the corresponding author on reasonable request.
- Everything else needed to interpret and, where the analysis is deterministic, reproduce the manuscript's results is in this repository.

## Reproducibility notes

- The Q3 text-mining analysis is run with a fixed random seed (33, across NumPy, UMAP, and HDBSCAN); this directly supersedes an earlier, non-seeded version of the analysis (kept at `notebooks/legacy/`), acknowledged in the manuscript as a resolved limitation.
- The reporting-quality indicator in Table S2 is an approximate, non-validated screening heuristic, distinct from the formal risk-of-bias assessment in Table S5 (QUIN for in vitro studies, SYRCLE for in vivo/CAM studies), which has been applied to all 78 included studies with a second independent blinded assessor and an explicit, uniform overall-judgement threshold rule (see `docs/Data_Dictionary_Supplementary_Tables.md`).
- Full-text accessibility was a Stage 2 eligibility criterion (manuscript Section 2.4); 37 of 124 records assessed for eligibility were excluded on this basis. No sensitivity analysis comparing these 37 unretrieved records against the 78 included studies has been performed (open item, `docs/PRISMA_2020_Checklist.md`, item 13f).
- Full-text screening was single-reviewer, not dual-independent (manuscript Limitations).

## Open items

1. Raw search exports (Scopus and Web of Science) are available from the corresponding author on request but not included here.
2. A record-level deduplication log (the actual removed-duplicate DOI list) is not included; `data/raw/Deduplication_Log.md` documents the method and manuscript-reported counts only.
3. `src/` and `config/` are not yet wired into the notebook (the notebook does not read `config/*.json` back in) -- see `src/README.md` and `config/README.md`.
3b. The notebook's I/O paths are hardcoded to Colab's `/content/`, not centralized to a documented project root -- see the "Known gap" note under Environment above and `docs/REORGANIZATION_NOTES.md`.
4. The fragment/topic/entity-level intermediate tables proposed in an earlier reorganization plan (`studies.csv`, `fragments.csv`, `topic_assignments.csv`, `axis_assignments.csv`, `entities.csv`, each with a `run_id`) do not exist as standalone files yet -- see `data/processed/README.md`.
5. No independent, dual-reviewer full-text screening has been performed.
6. Consider archiving a versioned snapshot of this repository (e.g., via Zenodo) and citing its DOI in the manuscript.

See `docs/REORGANIZATION_NOTES.md` for the full record of what changed in this reorganization and why.

## Citation

See `CITATION.cff`. Citation to the manuscript itself will be finalized upon acceptance/publication in *Biomaterials and Biosystems*.

## License

This repository is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — see `LICENSE` for the full text. You may reuse, adapt, and redistribute any material here, including commercially, provided you give appropriate credit.
