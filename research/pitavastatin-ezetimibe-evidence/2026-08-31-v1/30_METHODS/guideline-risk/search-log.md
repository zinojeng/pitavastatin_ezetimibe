# Search Log — guideline-risk-intelligence (Wave 1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Date: 2026-08-31 (Wave 1)

## Session start / health check

1. Read `CLAUDE.md`, `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`, `pitavastatin topic.md`, and the
   run's `00_RUN-MANIFEST.md`–`05_STATUS.md` in full before any search (per CLAUDE.md preamble and
   §13 health check).
2. `ListAgents` — confirmed `pit-eze-research-director` reachable (idle), plus sibling specialists
   `pit-eze-safety-pharmacology` and `pit-eze-trials-efficacy` (both busy, presumably running their
   own Wave 1 work concurrently).
3. Sent `CROSS_SESSION_TEST` to `pit-eze-research-director`; received `TASK_ASSIGNMENT` reply
   confirming scope and Gate/Wave (READY_FOR_NEXT_WAVE, Wave 1) before proceeding — see
   `90_CROSS-SESSION-LOG/`.

## MCP tool connectivity re-check (per `00_RUN-MANIFEST.md` Wave 0 blockers)

- `paper-search` — **connected**, used throughout (search_pubmed, search_crossref, search_europepmc,
  get_crossref_paper_by_doi).
- `tavily` — **connected**, used for web search and one page-content extraction
  (`tavily_extract` on the Taiwan STS 2026 ScienceDirect page).
- `google-scholar` — connected/available (loaded) but not needed this Wave; PubMed/Crossref/Europe
  PMC coverage was sufficient for all targets.
- `llamaparse` — **reconnected since Wave 0.** A connectivity probe (`parse_pdf_to_markdown` against
  a nonexistent path) returned a normal "file not found" application error rather than a
  connection-layer error, confirming the server itself is now reachable. **This contradicts Wave 0's
  `00_RUN-MANIFEST.md` blocker note** (venv missing) — reported to Director as an update, not
  re-verified beyond this probe.
- `research_hub` — **reconnected since Wave 0** and used for two supplementary searches
  (`search_papers`) and one download attempt (see `fulltext-manifest.md` and
  `unresolved-questions.md` for a compliance concern this surfaced). Also contradicts the Wave 0
  blocker note (binary missing) — reported to Director.
- `openevidence` — still shows CONNECTION_CLOSED in this session's tool-availability messages; not
  used (not attempted, since the system reminder marks it as a known failed connection throughout
  this session).
- `scihub` — **not invoked**, per `CLAUDE.md` §10's absolute prohibition. See
  `unresolved-questions.md` for a related compliance note about `research_hub`'s `download_paper`
  tool, which appears to search Sci-Hub internally as one of several sources with no exposed opt-out.

## Searches performed (chronological, condensed)

1. `search_pubmed` — "Halli-Tierney polypharmacy older adults American Family Physician 2019" →
   PMID 31259501 (citation #1).
2. `search_pubmed` — "Meng polypharmacy elderly Taiwan Archives Gerontology Geriatrics 2023" → no
   hit (title mismatch with query terms); refined query "Meng polypharmacy older adults Taiwan
   community" → PMID 37499332 (citation #2).
3. `get_crossref_paper_by_doi` — `10.1161/CIR.0000000000000625` → confirmed 2018 AHA/ACC guideline
   full report (citation #18); `search_pubmed` "2018 AHA ACC Guideline Management Blood Cholesterol
   Grundy Circulation 2019 executive summary" → both PMID 30565953 (Executive Summary, citation #17)
   and PMID 30586774 (full report, citation #18) returned together.
4. `search_pubmed` — "FOURIER Asian subgroup evolocumab Circulation Journal 2021 Keech" →
   PMID 33980763 (citation #24).
5. `get_crossref_paper_by_doi` — `10.6314/JIMT.202412_35(6).04.04` (as printed, citation #27) →
   empty result (not Crossref-resolvable / malformed). `WebSearch` — "李貽恒 石崇良 內科學誌 2024 血脂
   臨床路徑 共識" → located TSIM/Airiti listing; correct DOI identified as
   `10.6314/JIMT.202412_35(6).04` (see citation-verification-table.md for the discrepancy flag).
6. `get_crossref_paper_by_doi` — `10.1016/j.jacc.2025.11.016` → confirmed 2026 ACC/AHA guideline
   (citation #28), JACC 87(19):2624-2757.
7. `get_crossref_paper_by_doi` — `10.1016/j.atherosclerosis.2021.03.039` → confirmed Averna M 2021
   EAS Task Force statement (citation #31).
8. `search_crossref` — "Meng polypharmacy Taiwan Archives of Gerontology and Geriatrics 2023" → no
   direct hit (already resolved via PubMed in step 2; kept as a cross-check, no new information).
9. `search_pubmed` — "Chen 2022 focused update Taiwan lipid guideline high risk J Formos Med Assoc" →
   empty; `WebSearch` refinement → located; confirmed via `search_pubmed` "2022 focused update 2017
   Taiwan lipid guidelines high risk patients coronary artery disease peripheral artery disease
   ischemic stroke Chen" → PMID 35410823 (citation #29).
10. `search_pubmed` — "Ueng 2023 chronic coronary syndrome guideline Taiwan Society of Cardiology
    Acta Cardiol Sin" → empty; `WebSearch` refinement → PMID 36685161 (citation #30).
11. `search_crossref` — "American Diabetes Association Standards of Care Diabetes 2025 lipid
    management" → did not directly return the target; DOI pattern inferred from prior-year DOIs
    (`dc21-s010`, `dc20-s010`, etc.) and confirmed via `get_crossref_paper_by_doi` `10.2337/dc25-s010`
    → exact match (citation #32).
12. `search_pubmed` — "Mach 2019 ESC EAS Guidelines management dyslipidaemias" → returned both the
    base 2019 guideline (PMID 31504418) **and**, unexpectedly, the **2025 Focused Update**
    (PMID 40878289 / 40885687 / 41143316) — this single query located Search Protocol target T-007.
13. `WebSearch` — "2026台灣血脂異常學會 STS Suboptimally Tolerable Statins 共識" → located the Taiwan
    STS 2026 consensus's ScienceDirect page (T-005); `tavily_extract` on that URL for author list,
    abstract, and license status.
14. `WebSearch` — "台灣 Lp(a) 2026 共識 血脂異常學會 脂蛋白" → did not directly surface the Taiwan
    Lp(a) 2026 consensus; refined `WebSearch` — "Taiwan Lp(a) 2026 consensus lipoprotein(a)
    ...site:sciencedirect.com OR site:pubmed..." → located it; confirmed via `search_europepmc` →
    PMID 41881723 (T-006).
15. `search_europepmc` — "2022 Taiwan lipid guidelines primary prevention Huang PH" → no useful hit
    (unrelated results); resolved instead via `search_crossref` — "2022 Taiwan lipid guidelines
    primary prevention Huang PH Journal Formosan Medical Association" → DOI
    `10.1016/j.jfma.2022.05.010`, which also incidentally re-confirmed citation #29's exact DOI/pages
    in the same result set.
16. `mcp__llamaparse__parse_pdf_to_markdown` — connectivity probe only (nonexistent file path), not
    a real parse.
17. `ToolSearch` — loaded `mcp__research_hub__search_papers`; used it for two searches ("2026 ACC AHA
    dyslipidemia guideline" and "ESC 2025 focused update dyslipidaemia acute coronary syndrome
    in-hospital intensification ezetimibe", plus "PREVENT equations coronary artery calcium Lp(a)
    ApoB risk refinement 2026 guideline") — cross-confirmed T-007/#28 via a second source
    (openalex) and surfaced two Wave-2-relevant secondary/commentary sources on the ACC/AHA "goals"
    reframing.
18. `mcp__research_hub__search_papers` — "2026 Taiwan Society Lipids Atherosclerosis suboptimally
    tolerable statins Wu YJ" via `search_europepmc` (not research_hub) → confirmed exact DOI
    `10.1016/j.jfma.2026.04.111` for T-005 (PMID 42055832).
19. `mcp__research_hub__download_paper` — attempted DOI `10.1016/j.jfma.2026.04.111` (Taiwan STS
    2026, confirmed open-access/CC-licensed) → failed (no PDF link found by the tool across the
    sources it searched); **surfaced a compliance concern** — see `unresolved-questions.md`. No
    content was returned or used from this call.

## Not searched this Wave (deferred, in scope for Wave 2)

- Full-text extraction/exact-wording confirmation for any of the guideline documents located above
  (2026 ACC/AHA, 2025 ESC/EAS Focused Update, Taiwan STS 2026, Taiwan Lp(a) 2026, 2023 TSC CCS, the
  two 2022 Taiwan lipid-guideline companions, ADA 2025 Ch.10) — Wave 1 confirms document identity
  and citation-string accuracy only, not the specific numeric/recommendation claims attributed to
  them in `pitavastatin topic.md`.
- google-scholar was not queried directly (paper-search's PubMed/Crossref/Europe PMC coverage was
  sufficient for every target this Wave; kept in reserve for Wave 2 if a specific target proves hard
  to locate through the other sources).
