# notebooks/legacy/

`pipeline_Q3_BioBERT_5ejes.ipynb` here is the **original, pre-correction** version of the Section 4 (Q3) analysis notebook: no fixed random seed, no systematic UMAP/HDBSCAN hyperparameter search, and it predates the word-boundary fix to methodological-term matching and the corrected betweenness-centrality distance weighting.

It is kept for provenance/auditability, not for reuse. The current, corrected, fixed-seed (seed = 33) notebook that the manuscript's reported Section 4 results and `results/networks/*.gexf` files were generated from is `notebooks/pipeline_Q3_BioBERT_5ejes_CORREGIDO.ipynb`. The manuscript documents this correction explicitly (Section 4, "reconstructed pipeline").
