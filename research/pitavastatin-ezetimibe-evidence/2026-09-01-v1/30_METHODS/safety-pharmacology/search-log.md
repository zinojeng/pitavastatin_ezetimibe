# search-log — safety-pharmacology-intelligence (2026-09-01-v1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`

## Wave 1 approach

Per Director's instruction to "re-confirm/extend rather than re-derive," this Wave did **not**
repeat the full literature search performed in `2026-08-31-v1`. Instead: (1) read forward the prior
run's already Wave-4-audited `evidence-map.md`/`ddi-matrix.md`/`extraction-table.csv` as the baseline
(no changes made to those files — they belong to the prior, closed run, per Golden Rule 9 additive
versioning), (2) applied the new claim-safe taxonomy tags (`positioning-brief.md`,
`attack-defense-contribution.md`), (3) ran a light, targeted search for anything genuinely new since
2026-08-31 relevant to focus area 4.

## Tool connectivity this session

Failed to connect: `paper-search` (ENOENT: `uv` not found), `tavily` (ENOENT: `npx` not found),
`openevidence` (ENOENT: `node` not found) — same pattern the Director recorded at Wave 0. Connected
and used: `research_hub` (`search_papers` only — `download_paper` remains permanently prohibited per
Decision 2026-08-31-08), `google-scholar`, `WebFetch` (for DOI-resolution redirects and publisher
pages). `llamaparse` not needed this Wave — no new PDF obtained.

## What was searched and found

- `google-scholar`: "bempedoic acid vs statin ezetimibe combination tolerability DDI comparison
  2026" — **zero results**. No new bempedoic acid/PCSK9/inclisiran-vs-statin+ezetimibe tolerability
  comparison found this pass; the attack-defense section's §2 mechanistic claims about PCSK9/
  inclisiran DDI advantages remain `EXPERT INFERENCE`, not independently sourced this run — flagged
  explicitly in `attack-defense-contribution.md` §2.2 for the Director/next-round follow-up if a
  formal citation is needed.
- `research_hub search_papers`: "pitavastatin ezetimibe fixed dose combination clinical positioning
  2026" — 14 results. Two directly relevant:
  1. **K-924 (Tsujita 2023, J Atheroscler Thromb) — DOI now confirmed: `10.5551/jat.64006`**
     (previously only had PMID/PMCID on file from the prior run). Verified via WebFetch/DOI redirect
     to J-STAGE — confirmed it is the SAME K-924 trial already fully extracted in
     `2026-08-31-v1/20_EVIDENCE/safety-pharmacology/ddi-matrix.md` (numbers match exactly:
     −39.5%/−45.2%/−51.4%/−57.8%). Not new content, just a completed citation field.
  2. **"Optimizing LDL-C Reduction: High-Dose Pitavastatin Vs. Combination Therapy With Ezetimibe In
     Type II Diabetes"** — DOI `10.53555/ajbr.v27i4s.7096`, *African Journal of Biomedical Research*,
     2024. Title-only candidate, directly on-topic (T2DM population, dose-escalation vs FDC). WebFetch
     on the DOI-redirect target (africanjournalofbiomedicalresearch.com) returned **HTTP 403** — no
     abstract content obtained. **Recorded as a title/DOI-only candidate; no numeric content from it
     may be cited anywhere** (Tool-Confabulation Caution + Numeric Integrity Rule) until independently
     re-attempted with a working access path.
  - Other results from the same search were relevant to trials-efficacy's domain (other-statin FDC
    RWE, ESC 2025 Focused Update, PoLA/PCS Lp(a) recommendations) — not pursued further by this role;
    flagged to Director for routing.

## No new evidence found / no change from prior run

Glycemic profile, DDI matrix, CKD dosing, adherence/FDC evidence — no new sources found this pass
that add to or contradict `2026-08-31-v1`'s already-audited findings. This is a **light, non-
exhaustive search** given the ~1-day gap since the prior run's Wave 4 audit and the reduced tool
availability this session — it should not be read as an exhaustive confirmation that nothing new
exists, only that nothing new was found in this specific pass.

## QA note (2026-09-01, added per Director request): T-101 mg/dL→mmol/L conversion anomaly

While independently re-verifying T-101's East-Asian pharmacogenetic quote and PCSK9/inclisiran
tolerability language (see `positioning-brief.md` §4.3, `attack-defense-contribution.md` §2.1b),
this role also grepped the primary `.md` derivative directly for its LDL-C/non-HDL-C mg/dL↔mmol/L
conversions to check guideline-risk's summary table (`focus-area-1-guideline-wording.md` §5).
**Finding**: guideline-risk's table entry "non-HDL-C <100 mg/dL (2.4 mmol/L)" for the "Severe
hypercholesterolemia, no clinical ASCVD" row is a **faithful, accurate transcription** of what the
source `.md` literally prints at that location (confirmed verbatim at line 369 of the raw file:
"...non–HDL-C <100 mg/dL (2.4 mmol/L) is recommended..."). **This is NOT a guideline-risk
transcription error.** However, the *same* 100 mg/dL non-HDL-C value converts to **2.6 mmol/L** in
at least 7 other locations in the identical document (lines 322, 326, 340, 390, 447, 452, 458, 471 —
all grepped directly), which is the mathematically consistent conversion (100/38.67 ≈ 2.586 ≈ 2.6).
**This single "2.4 mmol/L" instance is a genuine internal inconsistency in the source `.md`
extraction, most plausibly a PDF-extraction column-merge artifact** — the surrounding context is
literally a two-column "Table 1. Continued" (2018 vs 2026 recommendation columns) that appears to
have been extracted into a single interleaved text stream, a known artifact pattern already recorded
for this same source (see `00_RUN-MANIFEST.md`'s Wave 0 note re: the reversed sidebar heading).
**Not confirmed** whether this reflects an actual *Circulation*-published typo or is purely an
extraction artifact — that would require the original PDF page image, not just the `.md` derivative,
to resolve. **Recommendation, not an instruction (this is guideline-risk's owned file)**: guideline-
risk may want to spot-check this specific value against the PDF directly before any manuscript
content relies on the "2.4 mmol/L" figure specifically; every other non-HDL-C <100 mg/dL instance in
the document uses 2.6 mmol/L and is internally consistent. Routing this note to the Director/
guideline-risk rather than editing their file myself, per file ownership (`CLAUDE.md` §3).

## Not used

`mcp__research_hub__download_paper` (permanently prohibited); `scihub`/`download_scihub` (prohibited,
never invoked).
