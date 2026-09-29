# config/

Parameters and dictionaries for the Section 4 (Q3) text-mining pipeline, externalized from the notebook so they can be reviewed and diffed without reading code.

- `five_content_axes_and_methodology_vocabulary.json` — the five content-axis keyword dictionaries (Material/Composition, Fabrication Strategy, Engineering Property, Biological Function, Tissue Application), the methodological-vocabulary list, the topic-classification thresholds (the exact `s_met`/coverage rules that decide `excluir`/`conservar`/`revisar manualmente`), the entity-co-occurrence edge threshold, and the NER model identifier.
- `entity_normalization_patterns.json` — the entity-name normalization regex rules (e.g., collapsing hydroxyapatite's 13 spelling variants), including the one known, disclosed limitation of this normalization (possible hyaluronic-acid/HA collision).

**Status:** these two files are verbatim extractions of the corresponding cells in `notebooks/pipeline_Q3_BioBERT_5ejes_CORREGIDO.ipynb` (Fase 5 and Fase 5.5), not a re-implementation. The notebook is still the executable source of truth — it does not yet read these JSON files back in; the pipeline is not fully modularized. Per the reorganization plan (see `docs/REORGANIZATION_NOTES.md`), this is intentional: modularizing every function into `src/`/`config/` before reorganizing the repository was judged unnecessary, and is left as a gradual, separate effort. If the notebook's dictionaries are ever edited, these files must be updated to match by hand until the notebook is refactored to import them directly.

The random seed (33) and thresholds reported in the manuscript are consistent with what is recorded here.
