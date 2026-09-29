# src/

Reserved for reusable extraction/cleaning/classification/NER/network-construction functions, gradually migrated out of `notebooks/pipeline_Q3_BioBERT_5ejes_CORREGIDO.ipynb`.

**Status: empty.** As of this reorganization, the entire Section 4 (Q3) pipeline — PDF text extraction, cleaning, BioBERT embedding, UMAP/HDBSCAN topic modeling, the five-axis classification, entity normalization, biomedical NER, and network construction — lives inline in the notebook. This was a deliberate choice for this reorganization pass (see `docs/REORGANIZATION_NOTES.md`): the notebook is fully runnable end to end and documents the analysis narrative alongside the code, and forcing a full modularization before fixing the repository's file layout and data inconsistencies would have delayed both.

Moving functions here should happen incrementally, one function at a time, each verified to reproduce identical output before the notebook cell is replaced with an import. `config/` already holds the two artifacts (axis keyword dictionaries, entity normalization patterns) that would be the first to be read from `src/`/`config/` instead of being redefined inline.
