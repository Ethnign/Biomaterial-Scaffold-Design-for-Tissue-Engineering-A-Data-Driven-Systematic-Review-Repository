# data/processed/

- `clasificacion_5ejes_topicos.csv` — one row per BERTopic topic produced by `notebooks/pipeline_Q3_BioBERT_5ejes_CORREGIDO.ipynb`: topic id, fragment count, the `s_met` methodological-dominance score, methodology-term coverage, top representative words, the resulting category/decision (`conservar` / `excluir` / `revisar manualmente`), and a boolean flag per content axis. This is the closest existing artifact to the reorganization guide's proposed `topic_assignments.csv` + `axis_assignments.csv` + `results/tables/topic_decisions.csv`, combined into one table at topic granularity.

## Gap versus the proposed schema (Section 2 of the reorganization guide)

The guide's Table 1 proposes fragment- and study-level intermediate tables with stable `run_id`/`study_id`/`fragment_id` columns: `studies.csv`, `fragments.csv`, `topic_assignments.csv`, `axis_assignments.csv`, `entities.csv`. These do not exist as separate saved files today — the corresponding data (cleaned fragments, per-fragment topic and axis labels, normalized entities) is held in in-memory DataFrames inside the notebook (`df_fragmentos`, `df_fragmentos_ejes`, entity lists) and is not persisted to disk at that granularity. Persisting them, with a `run_id` column tying each row to a specific pipeline execution, is listed as future work in `docs/REORGANIZATION_NOTES.md` rather than fabricated here.

`results/metrics/run_manifest.json` records what is known about the one run this repository's current results were generated from (seed, package list from the notebook's own `!pip install` cells) as a partial stand-in for the guide's proposed per-run manifest.
