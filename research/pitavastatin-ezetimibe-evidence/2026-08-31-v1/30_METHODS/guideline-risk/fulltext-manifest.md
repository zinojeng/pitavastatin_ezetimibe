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

## Wave 2 update (2026-08-31, PI-authorized, Decision 2026-08-31-12)

Full detail in `20_EVIDENCE/guideline-risk/wave2-fulltext-extraction.md` — summarized here for the
manifest's own record:

| Source | Attempt | Result |
|---|---|---|
| 2026 ACC/AHA guideline PDF (`ahajournals.org/doi/pdf/10.1161/CIR.0000000000001423`, URL supplied by Director/PI) | `curl` (spoofed UA) | **HTTP 403, Cloudflare bot-challenge.** BLOCKED_FOR_SOURCE (automated means). |
| Taiwan STS 2026 (`sciencedirect.com/.../S0929664626004493`) | `curl` + `WebFetch` | **HTTP 403, Cloudflare bot-challenge** (both tools). Europe PMC's own metadata also shows `is_open_access: False` for PMID 42055832, contradicting the landing page's OA/CC badge text captured in Wave 1 — unresolved discrepancy, not settled empirically because the download itself is blocked. BLOCKED_FOR_SOURCE. |
| ESC 2025 Focused Update (`academic.oup.com/eurheartj/article-pdf/.../ehaf190.pdf`, best-guess path) | `curl` | **HTTP 403, Cloudflare bot-challenge.** `WebFetch` on the landing page returned a response that self-reported "paywalled" but then produced suspiciously specific quoted text and page locators — treated as likely small-model confabulation, **discarded, not used as evidence anywhere in this repo.** BLOCKED_FOR_SOURCE. |
| Razavi AC, Blumenthal RS. "LDL-cholesterol lowering: timing is everything." Am J Prev Cardiol 2026;28:101668. DOI 10.1016/j.ajpc.2026.101668, PMCID PMC13326120. | `curl` against `europepmc.org/articles/PMC13326120?pdf=render` | **SUCCESS — HTTP 200, application/pdf.** License confirmed in-text: CC BY-NC-ND. Parsed successfully with `mcp__llamaparse__parse_pdf_to_markdown`. `verified: false` in `02_SOURCE-INVENTORY.md` terms still pending Director review (this is a secondary editorial, not a primary guideline, and does not address ezetimibe combination timing — see the Wave 2 evidence file for full scoping). File: `20_EVIDENCE/guideline-risk/fulltext/Razavi_Blumenthal_2026_AJPC_LDL-timing.pdf`, SHA-256 `b5a2c3941bcf2f14faf3c2757d35044cd01d520901854df0a277e792e06b806f`, retrieved 2026-08-30T21:02:04Z. Gitignored, not committed. |

No PDF was obtained for any of the three PI-prioritized documents (2026 ACC/AHA, ESC 2025 Focused
Update, Taiwan STS 2026) this Wave. The LlamaParse-tool demonstration requirement was satisfied via a
genuinely open-access, directly-adjacent secondary source instead. See
`20_EVIDENCE/guideline-risk/wave2-fulltext-extraction.md` for the full account, including a new
trials-efficacy-relevant finding (the REPRIEVE pitavastatin RCT, cited in that source's reference
list) flagged for the Director to route.

## Wave 2 item 6 update (2026-08-31) — Huang PH et al., "2022 Taiwan lipid guidelines for primary
prevention" (#35)

| Field | Value |
|---|---|
| Citation | Huang PH, Lu YW, Tsai YL, Wu YW, Li HY, Chang HY, Wu CH, Yang CY, Tarng DC, Huang CC, Ho LT, Lin CF, Chien SC, Wu YJ, Yeh HI, Pan WH, Li YH, on behalf of the expert committee for the Taiwan Lipid Guidelines for Primary Prevention. "2022 Taiwan lipid guidelines for primary prevention." *J Formos Med Assoc* 2022 (in-press/uncorrected-proof version at time of this PDF; final print pagination 121(12):2393-2407 not reflected in this copy). |
| DOI | `10.1016/j.jfma.2022.05.010` — independently re-confirmed this session via Europe PMC REST API (`search?query=DOI:10.1016/j.jfma.2022.05.010`), which returned PMID 35715290, matching title, journal (*J Formos Med Assoc*), pub year 2022. |
| PMID | `35715290` (no PMC deposit; `elink` confirmed empty in Wave 2). |
| Source URL (lawful, society-hosted) | `https://www.tas.org.tw/upload/files/1-s2_0-S0929664622002157-main%20(1).pdf` — Taiwan Society of Lipids and Atherosclerosis's own direct-hosted mirror, a different host from `sciencedirect.com` and not behind the Cloudflare bot-wall that blocks the publisher's own site directly. `HTTP 200`, `content-type: application/pdf`, no challenge headers observed. |
| Retrieved | `2026-08-30T21:19:35Z` (UTC). |
| License (verified against parsed full text, not assumed) | **CC BY 4.0.** Exact statement, appearing twice in the parsed text (byline footer and abstract footer): *"0929-6646/Copyright © 2022, Formosan Medical Association. Published by Elsevier Taiwan LLC. This is an open access article under the CC BY license (http://creativecommons.org/licenses/by/4.0/)."* |
| Local files (gitignored, untracked — confirmed via `git check-ignore -v` and `git ls-files`, matched against `.gitignore:16` `**/20_EVIDENCE/**/fulltext/`) | `20_EVIDENCE/guideline-risk/fulltext/Huang_2022_Taiwan-primary-prevention-guideline.pdf` (800,604 bytes) and `...Huang_2022_Taiwan-primary-prevention-guideline.parsed.md` (89,459 bytes). |
| SHA-256 (PDF) | `e18cf414bf3ea20e3d8a4467baf38300fde31fd3bedc3c095f5947b392567efc` — recomputed this session via `shasum -a 256` and matches the value recorded at extraction time (`20_EVIDENCE/guideline-risk/wave2-item6-extraction.md` §D). |
| SHA-256 (parsed markdown) | `b7de41285d71dc0b7618d3059c389b87bdfaa89b1ebc8f142488b0a1d44cd583` — recomputed this session and matches. |
| Parsing status | **Successful.** `mcp__llamaparse__parse_pdf_to_markdown` produced a clean, well-formed 740-line markdown file — correct headers, author/affiliation list, table of contents, and running section structure preserved; no visible OCR corruption or truncation; the CC BY license line is intact and legible in two places. |
| `redistribution_ok` implication | CC BY 4.0 permits redistribution with attribution, but per `CLAUDE.md` §11 committing the PDF/parsed markdown to this repo still requires the Director to record `verified: true` / `license: CC BY 4.0` / `redistribution_ok: true` in `02_SOURCE-INVENTORY.md` (Director-owned file) before any such commit — not done by this role. Full text remains local-only, gitignored, and untracked in this repo as of this check. |

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

## Wave 3 update (2026-08-31, PI-authorized)

Full detail in `20_EVIDENCE/guideline-risk/wave3-extraction.md`. Two new sources obtained:

| Source | Retrieved | SHA-256 (PDF) | Notes |
|---|---|---|---|
| Chen PS et al. 2022, Taiwan high-risk focused update (citation #29) | 2026-08-31T02:35:08Z, `tas.org.tw` mirror | `92646e438f5ddab7c9aceec4c91774e3b72bf1493f94d0f9cdc0517a8df0d00b` | CC BY-NC-ND (in-text). COR/LOE-graded recommendations extracted. |
| HPA 2022, Statistics of Health Promotion (T-008, 111年健康促進統計年報) | 2026-08-31T02:39:24Z, direct from `hpa.gov.tw`'s `GetFile.ashx` endpoint (not behind the same WAF as its `Pages/*.aspx` CMS pages) | `7fafac32ca74295dd69349ad4d730a53a533ddc85aeef24c54b00cb96615423a` | Government statistical report, not a journal article — no CC license statement; INSTITUTIONAL PRACTICE tag, not GUIDELINE/CONSENSUS. Exact elderly 三高 prevalence table (63.0%/28.2%/40.0%) extracted, matching `Tonvasca_2026.md`'s closing-slide figures exactly. |

**Near-miss caught and discarded, not in the repo:** a Wayback Machine "closest available snapshot"
lookup for T-008's exact file URL returned a different `sid` parameter than requested; fetching it
produced a genuine but *wrong* 721-page cancer-registry PDF (verified via its own title page, then
rejected). Never copied into `fulltext/`, not referenced anywhere as T-008. Recorded here so no
future session mistakes a similar Wayback fuzzy-match for a verified source without checking content
identity first.

T-005, T-006, and #34 remain untouched this Wave, exactly as recorded — an authorized
OpenEvidence-relay discovery pass was considered but not performed (`oe_health` reported the relay
daemon up but its browser extension not connected; no `oe_ask` call was attempted).
