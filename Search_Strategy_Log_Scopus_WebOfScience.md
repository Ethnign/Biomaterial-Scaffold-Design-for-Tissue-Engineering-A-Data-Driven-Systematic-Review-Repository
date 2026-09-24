# Search Strategy Log — Full Boolean Strings (Scopus and Web of Science)

Corresponds to Section 2.3 ("Search Strategy") and Table 1 of the manuscript.
Searches last executed: August 2026. Restricted to: document type = Article, language = English, publication year 2023 onward.

Base terms (identical across all four searches):
- Scaffold/tissue-engineering term: `"tissue engineering scaffold*"`
- Materials term: `hydroxyapatite OR chitosan OR polycaprolactone OR PCL`

Question-specific blocks:
- Q1 (biocompatibility outcomes): `biocompatib* OR cytocompatib* OR "cell viability" OR cytotox* OR "cell proliferation" OR "cell adhesion"`
- Q2 (modification strategies): `crosslink* OR "surface modification" OR functionali?ation OR "growth factor*" OR nanoparticle* OR coating OR "drug loading"`

## Scopus

**Q1 (n = 188)**
```
TITLE-ABS-KEY("tissue engineering scaffold*") AND TITLE-ABS-KEY(hydroxyapatite OR chitosan OR polycaprolactone OR PCL) AND TITLE-ABS-KEY(biocompatib* OR cytocompatib* OR "cell viability" OR cytotox* OR "cell proliferation" OR "cell adhesion") AND PUBYEAR > 2022 AND (LIMIT-TO(DOCTYPE,"ar")) AND (LIMIT-TO(LANGUAGE,"English"))
```

**Q2 (n = 105)**
```
TITLE-ABS-KEY("tissue engineering scaffold*") AND TITLE-ABS-KEY(hydroxyapatite OR chitosan OR polycaprolactone OR PCL) AND TITLE-ABS-KEY(crosslink* OR "surface modification" OR functionali?ation OR "growth factor*" OR nanoparticle* OR coating OR "drug loading") AND PUBYEAR > 2022 AND (LIMIT-TO(DOCTYPE,"ar")) AND (LIMIT-TO(LANGUAGE,"English"))
```

## Web of Science (Core Collection)

Reconstructed from the confirmed statement that Web of Science used the identical term blocks as Scopus, adapted to WoS Advanced Search syntax (`TITLE-ABS-KEY` -> `TS=`, Topic field covering title/abstract/keywords).

**Q1 (n = 169)**
```
TS=("tissue engineering scaffold*") AND TS=(hydroxyapatite OR chitosan OR polycaprolactone OR PCL) AND TS=(biocompatib* OR cytocompatib* OR "cell viability" OR cytotox* OR "cell proliferation" OR "cell adhesion") AND PY=(2023-2026) AND DT=(Article) AND LA=(English)
```

**Q2 (n = 102)**
```
TS=("tissue engineering scaffold*") AND TS=(hydroxyapatite OR chitosan OR polycaprolactone OR PCL) AND TS=(crosslink* OR "surface modification" OR functionali?ation OR "growth factor*" OR nanoparticle* OR coating OR "drug loading") AND PY=(2023-2026) AND DT=(Article) AND LA=(English)
```

## Notes on the Scopus-to-WoS translation

- `TITLE-ABS-KEY(...)` (Scopus) maps to `TS=(...)` (WoS Topic search: title, abstract, author keywords, and Keywords Plus).
- The `?` single-character wildcard behaves the same in both databases, so `functionali?ation` correctly matches both "functionalisation" and "functionalization" in each.
- The `PUBYEAR > 2022` / `PY=(2023-2026)` and document-type/language filters are stated separately in the manuscript text (Section 2.3) rather than inside the quoted example boolean string, which shows only the core term structure for brevity; both are included here in full for reproducibility.
- STATUS: this reconstruction has not been independently re-run against the live Web of Science database to confirm it returns exactly 169/102 records; the author should verify this before treating the PRISMA-S checklist item as fully closed, or note that filters were re-applied via the WoS interface rather than the inline string shown above.
