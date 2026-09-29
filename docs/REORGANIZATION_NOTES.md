# Repository reorganization notes (2026-09-29)

This reorganization followed the proposal in *"Reorganización del repositorio de biomateriales"* (uploaded 2026-09-29). This note records what was actually done against that proposal's own sequence (Section 4) and completion criteria (Section 6), including what is still open, per this project's standing rule of not minimizing or hiding gaps.

## What was done

1. **State preserved, branch created.** Work happened on branch `reorg/repo-structure`, starting from the repository's single existing commit (`e477ab6`, "Add files via upload"). Nothing was deleted; superseded files were archived (see below).
2. **Files classified and moved** into `manuscript/`, `data/raw/`, `data/processed/`, `notebooks/`, `src/`, `config/`, `results/{networks,figures,tables,metrics}/`, `supplementary/`, `docs/`, in a commit that only moves files (no content changes).
3. **Methodological correction kept separate** from the pure move, in its own commit, per the proposal's Section 4, item 4 ("Separar la corrección metodológica"). That commit:
   - Added the current manuscript (`.tex`/`.pdf`), not previously in the repository at all.
   - Replaced the 5 old matplotlib network renders (archived at `results/figures/superseded_matplotlib/`, not deleted) with the 3 Gephi renders actually used in the manuscript, plus the 2 additional Gephi renders for the axes discussed only in text.
   - Added all 5 `.gexf` network files, which the manuscript and the previous README both claimed were available but which were **absent from the repository entirely** before this reorganization.
   - Replaced Supplementary Table S3 (adds `Tissue_Application_Secondary`/`Experimental_Model`/`In_vivo`/`CAM` columns used by the SYRCLE assessment; corrects 26 `Tissue_Application` values).
   - Replaced Supplementary Table S4 -- **the previously published CSV was malformed** (unescaped commas break parsing from line 9 onward; confirmed with `pandas.read_csv`) and also predated the `Response_Category` re-examination described in the manuscript (7 of 14 dose-series studies confirmed genuinely non-monotonic).
   - Replaced Supplementary Table S5 with the harmonized risk-of-bias assessment (explicit Yes-count threshold rule for the overall judgement, resolving an internal inconsistency where studies with identical item-level profiles had received different overall ratings under the prior purely qualitative process; a documented `N/A` exception for SYRCLE domain D4 in the 2 CAM studies; three-level Yes/No/Unclear scale, matching the independent second assessor). Added the matching blank template and assessor guide, both consistent with this scale and rule.
   - Replaced the Data Dictionary with the version covering S1-S5 (the previous version only documented S1-S4) and its full revision history.
   - Added the corrected, fixed-seed (seed=33) Q3 notebook as the current one; kept the original unseeded notebook under `notebooks/legacy/` for provenance rather than deleting it.
   - Externalized real pipeline parameters (five-axis keyword dictionaries, methodology vocabulary, classification thresholds, entity-normalization regex rules) into `config/*.json`, extracted verbatim from the corrected notebook.
4. **Executed and checked, within what could actually be verified here:** the manuscript recompiles cleanly from its new location (0 LaTeX errors, 0 undefined references, 15 pages) with figure paths updated to `manuscript/figures/`. The risk-of-bias table's item counts and overall-judgement distribution were re-verified programmatically after every edit (see `docs/RoB_Estado_y_Pendientes.md`). **Not done:** an actual end-to-end re-run of the Q3 notebook from a clean environment -- that requires the 78 studies' full-text PDFs and GPU/CPU time not available in this session; this is disclosed rather than claimed.
5. **Publish a coherent version:** once this branch is merged, tag `v1.0.0` and cite it from the manuscript's Data Availability statement, per the proposal's Section 4, item 6.

## What is intentionally not done yet (and why)

The proposal itself says modularization does not need to precede reorganization ("No es necesario modularizar todo antes de reorganizar los archivos"). Consistent with that:

- **`src/` is empty.** The full pipeline still lives inline in the notebook. See `src/README.md`.
- **`config/*.json` is not read back by the notebook.** It is a faithful, reviewable extraction of the notebook's own dictionaries/thresholds, kept in sync by hand for now. See `config/README.md`.
- **The fragment/topic/entity-level intermediate tables** proposed in the guide's Section 2 (`studies.csv`, `fragments.csv`, `topic_assignments.csv`, `axis_assignments.csv`, `entities.csv`, each with a `run_id`) do not exist as separate files. The closest existing artifact is `data/processed/clasificacion_5ejes_topicos.csv` (topic-level, not fragment-level). See `data/processed/README.md`.
- **`results/metrics/run_manifest.json`** is manually reconstructed from the notebook's own cells (seed, package list, recorded Python version), not emitted by an automated run-logging step. Package versions were never pinned for the run that produced the current results, which is disclosed rather than backfilled with invented version numbers.
- **No independent re-execution of the pipeline** was performed as part of this reorganization (see above).
- **Raw search exports and full-text PDFs remain unavailable** in the repository (licensing/size), as before this reorganization.

## Checklist against the proposal's Section 6 completion criteria

| Criterion | Status |
| --- | --- |
| README links work and paths don't depend on the author's machine | Paths in the new README and manuscript are relative; verified by recompiling the manuscript from its new location. |
| The documented pipeline runs from a clean environment with available inputs | Not independently re-verified end-to-end in this session (requires the 78 PDFs); `requirements.txt` and `results/metrics/run_manifest.json` document what's known. |
| Every result can be tied to the run, fragments, and studies that produced it | Partial -- true for the topic-level `clasificacion_5ejes_topicos.csv` and the 5 networks; not yet true at fragment level (see gap above). |
| Exclusion decisions are justified and match the published run | Unchanged from before this reorganization; documented in the manuscript and `docs/PRISMA_2020_Checklist.md`. |
| Counts and versions are consistent across manuscript, supplements, and results | Yes for everything touched in this reorganization (S3-S5, Data Dictionary, Guide, template, manuscript wording all cross-checked for the risk-of-bias scale and counts specifically). |
| Data-distribution conditions are documented; full PDFs only included where licensed | Yes -- documented in `data/raw/README.md` and the main README; no full-text PDFs are included. |
