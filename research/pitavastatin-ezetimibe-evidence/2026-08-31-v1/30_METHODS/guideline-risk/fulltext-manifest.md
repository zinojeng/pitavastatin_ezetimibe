# Full-text Manifest — guideline-risk-intelligence (Wave 1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

Per `CLAUDE.md` §11 (Full-text & licensing rule): full-text PDFs and parsed output are local-only,
never committed unless redistribution license is explicitly verified and recorded here with
`verified: true`. **No full-text PDF was successfully downloaded or parsed by this role this Wave** —
see status per source below. No file was written to `20_EVIDENCE/guideline-risk/fulltext/` this Wave
(directory not yet created by this role — nothing to gitignore-check yet).

## Attempted

| Source | DOI | Attempt | Result |
|---|---|---|---|
| Taiwan STS 2026 consensus (Wu YJ et al.) | 10.1016/j.jfma.2026.04.111 | `mcp__research_hub__download_paper` | **Failed** — tool reported the paper was located in metadata across 7 databases but no downloadable PDF link was found by the tool. No PDF obtained. See `unresolved-questions.md` for a compliance concern this attempt surfaced (the tool's own error message states it searches Sci-Hub among its sources, with no exposed parameter to disable that). |

## Confirmed open-access / licensing status (not yet downloaded)

| Source | Access status (as observed) | Notes |
|---|---|---|
| Taiwan STS 2026 consensus (Wu YJ et al., JFMA 2026) | **Open access, Creative Commons license** — confirmed via direct page extraction of the ScienceDirect article page ("Open access... Under a Creative Commons license"). | Best candidate for lawful full-text acquisition next Wave — publisher page itself is the fastest path (e.g., a direct fetch of the ScienceDirect HTML/PDF), rather than relying on `research_hub`'s aggregator. |
| Taiwan Lp(a) 2026 consensus/review (Cheng CY et al., JFMA 2026) | **Not yet checked** for open-access status. | Wave 2 task. |
| 2025 ESC/EAS Focused Update (Mach F et al.) | **Not yet checked.** Eur Heart J is typically subscription-access; the parallel Atherosclerosis publication and/or an author-manuscript OA copy may be available via Unpaywall — not checked this Wave. | Wave 2 task; try Unpaywall before assuming paywalled. |
| 2026 ACC/AHA guideline (Blumenthal RS et al., JACC) | **Not yet checked.** JACC guidelines are sometimes made free-to-read by the society at publication (institutional practice varies by document) — not confirmed either way this Wave. | Wave 2 task. |
| 2023 TSC CCS guideline (Ueng KC et al., Acta Cardiol Sin) | **Likely open access** — Acta Cardiologica Sinica is generally an open-access journal and a PMC listing was seen in WebSearch results (PMC9829849) though that PMCID appeared associated with a different, possibly mismatched indexing entry — needs direct confirmation, not assumed. | Wave 2 task. |
| 2022 Taiwan lipid guidelines (both companions, Chen PS / Huang PH, JFMA) | **Not yet checked**; Taiwan Society-affiliated PDFs were seen hosted directly on `tas.org.tw` in WebSearch results (e.g., `https://www.tas.org.tw/upload/files/...main.pdf`), which if genuinely society-hosted would likely be a lawful, freely accessible copy — URL noted for Wave 2 verification, not fetched this Wave. | Wave 2 task. |
| ADA Standards of Care 2025, Ch. 10 | **Not yet checked** — ADA Standards of Care chapters are typically open access (Diabetes Care makes the Standards of Care freely available); plausible but not confirmed this Wave. | Wave 2 task. |

## Recommendation for Wave 2 (this role)

1. Do **not** use `mcp__research_hub__download_paper` again until the Sci-Hub-inclusion concern
   (see `unresolved-questions.md`) is resolved by the Director/PI.
2. Prefer direct publisher-page fetch (e.g., `WebFetch`/`tavily_extract` on the ScienceDirect/journal
   URL) or Unpaywall lookup for confirmed-OA sources over any aggregator that may silently touch
   Sci-Hub.
3. Once a lawful PDF is obtained, parse with `mcp__llamaparse__parse_pdf_to_markdown` (confirmed
   reachable this Wave) into a role-owned, gitignored `20_EVIDENCE/guideline-risk/fulltext/`
   directory (pattern already gitignored repo-wide per `.gitignore`'s
   `**/20_EVIDENCE/**/fulltext/` rule) — do not commit the parsed output; record URL/license/PMID/DOI
   and local path in an updated version of this manifest, and only mark `verified: true` /
   `redistribution_ok: true` in `02_SOURCE-INVENTORY.md` (Director-owned file — report the finding,
   do not edit it directly) once redistribution terms are actually confirmed (e.g., the STS 2026
   consensus's CC license terms should be read in full before assuming CC = redistribution-OK for
   this repo's purposes).
