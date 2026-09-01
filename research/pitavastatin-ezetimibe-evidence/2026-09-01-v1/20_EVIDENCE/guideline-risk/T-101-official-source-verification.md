# T-101 verification — `inbox/2026-acc-aha-drive/official/` candidate primary source

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Owner: guideline-risk-intelligence · Wave 1, Priority 1 (Decision 2026-09-01-03, Q1/Q2/Q3)

## Verdict

**VERIFIED — GENUINE PRIMARY SOURCE.** The file `inbox/2026-acc-aha-drive/official/
2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_Circulation.pdf` is, to the highest confidence
this role's available tools can establish, a genuine copy of the actual published "2026 ACC/AHA/
AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the Management of Dyslipidemia." Evidence
Hierarchy tag: **GUIDELINE / CONSENSUS**. This upgrades Decision 2026-09-01-03's `INSUFFICIENT
EVIDENCE` status — reported here for the Director to record the change in `02_SOURCE-INVENTORY.md`
(this role does not edit that file directly).

**Caveat on residual uncertainty, stated precisely rather than glossed over:** no tool available to
this role can byte-compare this PDF against a fresh publisher-served download (ahajournals.org is
Cloudflare-walled to automated fetches — see below), so this is verification by **independent
external corroboration and internal-consistency triangulation**, not a cryptographic chain of
custody back to the publisher's own server. I consider this sufficient for GUIDELINE/CONSENSUS use
given the strength and independence of the signals below, but it is not absolute proof, and I want
that distinction on record rather than overclaimed.

## Method and findings, in the order performed

### 1. Local integrity check (does the file match its own accompanying manifest?)

Recomputed independently, not trusted from either `OFFICIAL_SOURCE_MANIFEST.md` or the Director's
Wave 0 note:

- PDF SHA-256: `2a6af5e2801b02d75f43d9ed25181e01f344b8751cc76bbc03d181957bf81ffa` — matches.
- `.md` derivative SHA-256: `b7d468b7730973b70a200de6a3ae9550a91cda77b928d14bbf53f8f09f216cf7` —
  matches. Line count: 9,536 — matches.
- `pdfinfo`: Title = "2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the
  Management of Dyslipidemia: A Report of the American College of Cardiology/American Heart
  Association Joint Committee on Clinical Practice Guidelines"; Subject = "Circulation
  2026.153:e1154-e1276"; Pages = 123 — all consistent with the manifest's claims.

**This step only establishes the file hasn't changed since being described — it does not by itself
establish authenticity.** Treated as necessary, not sufficient.

### 2. Independent external verification — DOI resolution (lawful, no-auth metadata lookup)

- `curl` against `https://doi.org/10.1161/CIR.0000000000001423` (the DOI foundation's own
  resolver, not the publisher) returned an **HTTP 302 redirect to
  `https://www.ahajournals.org/doi/10.1161/CIR.0000000000001423`** — i.e., this DOI is genuinely
  registered and resolves to a specific, real ahajournals.org article path. A fabricated/unregistered
  DOI would return a resolver-level 404, not a redirect to a plausible real publisher URL. (The
  publisher page itself then returned Cloudflare's bot-challenge 403, consistent with what this
  project's prior run repeatedly found for `ahajournals.org` — expected, not a red flag.)

### 3. Independent external verification — Crossref API (the DOI registration agency's own database)

Queried `https://api.crossref.org/works/10.1161/CIR.0000000000001423` directly (a free, no-auth,
no-bot-wall public API — the authoritative registry for this DOI, not a secondary aggregator).
Result, compared point-by-point against the PDF's own self-citation:

| Field | Crossref (independent, authoritative) | PDF's own internal citation | Match? |
|---|---|---|---|
| Title | "2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the Management of Dyslipidemia: A Report of the American College of Cardiology/American Heart Association Joint Committee on Clinical Practice Guidelines" | Identical (pdfinfo Title field, and running footer text) | **Exact** |
| Container-title | Circulation | Circulation | **Exact** |
| Publisher | Ovid Technologies (Wolters Kluwer Health) | (not self-stated, but Wolters Kluwer/Ovid is in fact Circulation's real publisher on behalf of the AHA) | **Consistent with known reality** |
| Volume | 153 | 153 | **Exact** |
| Published-print date | 2026-04-28 | Every page footer reads "April 28, 2026" | **Exact — independent cross-validation of a specific date, not just a citation string** |
| Author count / first authors | 63 authors; first named: Blumenthal, Morris, Gaudino, Johnson | Running header: "Blumenthal et al" | **Consistent** |
| ISSN | 0009-7322, 1524-4539 | (Circulation's real ISSNs) | **Consistent with known reality** |

The exact match on a specific, independently-registered publication date (April 28, 2026) between
Crossref's database and the PDF's own running-footer text is the single strongest individual
signal here — a fabricator would need to have either (a) known and correctly embedded the real
Crossref-registered date in every page footer of a 123-page fabricated document, or (b) coincidentally
picked the same date, both very unlikely.

### 4. Q2 resolved: the Circulation DOI and the prior run's JACC DOI (#28) are genuine co-publication DOIs, not a citation error

Compared this DOI's Crossref author list (Blumenthal, Morris, Gaudino, Johnson, ...) against the
prior run's independently-verified Crossref record for DOI `10.1016/j.jacc.2025.11.016` (JACC),
recorded in `2026-08-31-v1/10_DATA/guideline-risk/citation-verification-table.md`: that record's
author list is "Roger S. Blumenthal; Pamela B. Morris; Mario Gaudino; Heather M. Johnson; Timothy S.
Anderson; ..." — **identical name, identical ordering**, same guideline title
("2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the Management of
Dyslipidemia"). **Conclusion: these are two genuine, simultaneous co-publication DOIs for the same
joint multi-society guideline — one in JACC (the ACC's journal), one in Circulation (the AHA's
journal) — a real and common pattern for major joint ACC/AHA guidelines (the 2018 predecessor
guideline was co-published the same way — Circulation 2019;139:e1082–e1143 / JACC 2019;73:3168–3209,
both of which are cited *inside this very document*, see §5 below).** Neither DOI is a bad/fabricated
citation. This resolves Q2 with HIGH confidence. Recommend the Director update citation #28's status
from `BLOCKED_FOR_SOURCE` to reflect that its co-publication (this Circulation DOI) is now verified
and full-text-obtained, even though the JACC-side PDF itself is still not directly in hand.

### 5. Internal-consistency and plausibility checks (corroborating, not standalone proof)

- **"Downloaded from http://ahajournals.org by on August 31, 2026" watermark present on every page**
  of the `pdftotext`-extracted text (checked systematically, not just spot-checked) — this is the
  exact, characteristic institutional-access watermark pattern real ahajournals.org/Wolters Kluwer
  PDF downloads carry. (The blank between "by" and "on" — no institution name — is consistent with a
  non-institutionally-recognized or anonymized download route; not itself suspicious.) The date,
  August 31, 2026, is exactly one day before this run's Wave 0 (2026-09-01), consistent with the
  file's own reported drop-in timestamp.
- **Embedded XMP metadata for figures** shows genuine Adobe Illustrator/Photoshop production
  history (`CreatorTool="Adobe Illustrator 29.5 (Windows)"`, `pdf:Producer="Adobe PDF library
  17.00"`) — consistent with a real publisher's production pipeline for embedded vector figures,
  not with a document assembled by pasting LLM output into a generic PDF exporter.
  The Director's Wave 0 note about a reversed-sidebar-heading OCR/extraction artifact
  ("STNEMETATS...") was not independently re-located by this role in a `pdftotext -layout` pass
  (likely an artifact specific to a different extraction path/tool, e.g. the `.md` derivative's own
  conversion) — not re-verified, not contradicted either; noted for completeness.
- **Content coherence and known-figure cross-checks** — every numeric/clinical fact this role
  spot-checked against established literature knowledge matched exactly and consistently across
  many repetitions (not just once): ezetimibe ~18% LDL-C reduction / ~25% incremental-on-statin
  (textbook-standard figure); "approximately 10% of patients may not tolerate maximum dose daily
  statin therapy"; "small clinically insignificant increase in HbA1C of 0.06% to 0.08%"; "serious
  hepatotoxicity occurs in approximately 1 in 100,000 individuals treated with statins"; correct
  mg/dL↔mmol/L conversions repeated dozens of times without a single arithmetic inconsistency found
  (e.g., 55 mg/dL↔1.4 mmol/L, 85 mg/dL↔2.2 mmol/L, 70 mg/dL↔1.8 mmol/L, 100 mg/dL↔2.6 mmol/L, all
  correct). Term-frequency counts independently re-run this session matched the Director's Wave 0
  counts exactly (ezetimibe ×110 confirmed).
- **Formal COR/Level-of-Evidence table structure** (e.g., "2a B-R" columns preceding each numbered
  recommendation) is reproduced correctly and consistently throughout, matching real ACC/AHA
  guideline house style exactly.

### 6. Q3 — not pursued this Wave; recommend closing as moot

`markdown/1-s2.0-S0735109725102544.md` (the intake's own self-cited "raw guideline source" for its
`adjudication_log_v2.md`) was not searched for. Given that this role has now independently verified
the actual primary guideline directly (§§1–5 above), the intake's secondary adjudication log and its
own claimed source file are no longer load-bearing for anything this role needs — recommend the
Director treat Q3 as low-priority/moot unless another role still needs it for an unrelated reason
(e.g., if the intake's other 34 files' claims need reconciling against it specifically). Not asking
the PI about it this Wave given it's no longer blocking; the Director/PI can revisit if it resurfaces.

## What this verification does NOT establish

- It does not verify every one of the 9,536 lines of the `.md` derivative — extraction-conversion
  errors in the `.md` remain possible; per `OFFICIAL_SOURCE_MANIFEST.md`'s own caveat and this run's
  Decision 2026-09-01-03, **any quote used in synthesis should be checked against the PDF
  (`pdftotext`), not the `.md`** — this is what this role did throughout (see
  `focus-area-1-guideline-wording.md`).
- It does not rule out the (now very unlikely, but not literally impossible) scenario of an
  extremely sophisticated adversarial fabrication that also faked Crossref's public record — Crossref
  itself is not infallible, though tampering with a third-party DOI registry's public API response is
  a materially different and much less plausible threat model than an AI-generated PDF, and is
  treated as out of scope for this role's verification standard.
