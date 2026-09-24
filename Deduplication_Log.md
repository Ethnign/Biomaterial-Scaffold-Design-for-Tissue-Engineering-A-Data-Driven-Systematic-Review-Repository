# Deduplication Log — Methodology and Record Counts

**Status: methodology and record-count reconstruction only.** This file documents the deduplication *method* and the *counts* already reported in the manuscript (Section 2.5). It is **not** a record-level log (i.e., it does not list the actual DOIs/titles that were identified and removed as duplicates), because that requires the raw Scopus and Web of Science search export files, which are not yet in this repository (see README, Open items). If a reviewer or reader wants to verify the deduplication at the individual-record level, the raw exports need to be added and this file regenerated from them.

## Method (as reported in manuscript Section 2.5)

Deduplication was performed using the Digital Object Identifier (DOI) as the matching key, normalized to lowercase with whitespace trimmed, in three sequential passes:

1. **Within-database pass:** within each database (Scopus, Web of Science), across the Q1 and Q2 search exports for that database.
2. **Manual cross-reference pass:** a manual review identified 13 additional Scopus records as redundant (not caught by the automated DOI match in pass 1) and removed them.
3. **Cross-database pass:** a final pass matched records between the Scopus and Web of Science sets; where a DOI matched across databases, the Scopus record was retained preferentially and the Web of Science duplicate was removed.

## Record counts

| Stage | Count |
| --- | --- |
| Records identified (Scopus Q1 + Q2, WoS Q1 + Q2) | 564 |
| Scopus Q1 | 188 |
| Scopus Q2 | 105 |
| Web of Science Q1 | 169 |
| Web of Science Q2 | 102 |
| Duplicate records removed (all 3 passes combined) | 69 |
| -- of which: manual cross-reference pass (step 2) | 13 |
| -- of which: automated DOI-match passes (steps 1 + 3, by difference) | 56 |
| Unique records remaining after deduplication | 495 |

Note: the manuscript does not separately report how the 56 automated-match duplicates split between the within-database pass (step 1) and the cross-database pass (step 3); if that breakdown is available in the original screening records, it should be added here.

## To complete this log at the record level

For full PRISMA-S auditability, add a table (or a separate CSV, e.g. `Deduplication_Log_Records.csv`) with one row per removed duplicate record, containing at minimum: `DOI`, `Title`, `Source_database(s)_where_found`, `Pass_removed_at` (1, 2, or 3), and `Retained_record_DOI` (for cross-database matches, which record was kept). This requires the raw Scopus and Web of Science export files as input.
