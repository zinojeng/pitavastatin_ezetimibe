# Unresolved Questions — guideline-risk-intelligence (Wave 1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

Role-local flags for the Research Director to fold into `04_OPEN-QUESTIONS.md` (this role does not
edit that file directly per its file-ownership scope).

## NEEDS_PI / NEEDS_ANALYST

1. **[NEEDS_ANALYST] Citation #27 DOI discrepancy.** `Tonvasca_2026.md` prints the DOI for the 2025
   Taiwan lipid clinical pathway consensus (李貽恒、石崇良, 內科學誌 2024;35:426-430) as
   `10.6314/JIMT.202412_35(6).04.04`. The correct DOI located via independent search is
   `10.6314/JIMT.202412_35(6).04` (single, not doubled, `.04` suffix). Title/authors/journal/volume/
   issue/pages otherwise match. Per the Numeric Integrity Rule this was **not** silently corrected —
   flagging for Director to log in `03_DECISION-LOG.md` with a Decision Taxonomy label (likely
   `VERIFIED_AND_REPLACE` for the DOI field specifically, since the rest of the citation is intact).

2. **[NEEDS_PI] Compliance concern: `mcp__research_hub__download_paper` appears to search Sci-Hub
   internally with no exposed opt-out.** When this role called
   `mcp__research_hub__download_paper(doi="10.1016/j.jfma.2026.04.111")` (Taiwan STS 2026 consensus,
   confirmed open-access/CC-licensed), the tool's own error response stated: *"🔍 Sources Searched:
   ArXiv, CrossRef, SSRN, Sci-Hub, and others."* The tool call ultimately returned no PDF and no
   content was obtained or used — so no actual Sci-Hub content entered this repo. However,
   `CLAUDE.md` §10 states an absolute prohibition on Sci-Hub for this project ("must not be invoked
   by any role... for any purpose, under any framing"), and the `download_paper` schema exposes no
   parameter to disable Sci-Hub inclusion (unlike `paper-search`'s `download_with_fallback`, which at
   least exposes a `use_scihub` boolean, itself also flagged prohibited in `CLAUDE.md` §10). **This
   role will not call `mcp__research_hub__download_paper` again pending Director/PI guidance** on
   whether `research_hub`'s plain metadata-search tools (`search_papers`, used successfully and
   safely this Wave for discovery only) remain acceptable while its *download* tool stays off-limits,
   or whether `research_hub` as a whole should be avoided for this project. Recommend the Director
   raise this with the PI as an environment/tool-policy question, not something for a specialist role
   to resolve unilaterally.

## NEEDS_SOURCE

3. **[NEEDS_SOURCE] "111 年健康促進統計年報"** (Taiwan Health Promotion Administration statistical
   annual report, ROC year 111 = 2022), cited in `Tonvasca_2026.md`'s closing slide for
   hypertension/hyperglycemia/hyperlipidemia prevalence in Taiwanese elderly (63%/28%/40%). This is a
   government statistical report, not indexed in PubMed/Crossref/paper-search. Not verified this
   Wave. Would require a direct fetch from the Health Promotion Administration (國民健康署) website;
   flagging as a Wave 2 acquisition target rather than attempting an unstructured web scrape under
   time pressure this Wave.

4. **[NEEDS_SOURCE, Wave 2] Full-text extraction pending for every guideline document located this
   Wave.** Wave 1 confirmed document *identity* (correct DOI/PMID, title, author list, journal) for
   the 2026 ACC/AHA guideline, the 2025 ESC/EAS Focused Update, the Taiwan STS 2026 consensus, the
   Taiwan Lp(a) 2026 consensus/review, the 2023 TSC CCS guideline, both 2022 Taiwan lipid-guideline
   companions, and ADA 2025 Ch.10 — but **did not** independently confirm the specific numeric
   thresholds and recommendation wording that `pitavastatin topic.md` attributes to them (e.g., the
   exact <55 mg/dL very-high-risk goal wording in the 2026 ACC/AHA text, the exact ESC 2025 in-hospital
   ACS intensification wording, the exact Lp(a) nmol/L thresholds in each document). These claims
   currently trace only to the PI's own topic notes, not to independently re-confirmed primary-source
   text. See `20_EVIDENCE/guideline-risk/evidence-map.md` for exactly which claims carry this caveat.

## Informational (not blocking, but worth Director awareness)

5. **MCP connectivity has changed since Wave 0.** `00_RUN-MANIFEST.md` recorded `research_hub` and
   `llamaparse` as failed-to-connect (ENOENT — binary/venv missing) at Wave 0. Both reconnected
   successfully during this Wave 1 session (see `search-log.md`). Recommend the Director update
   `00_RUN-MANIFEST.md`'s blocker section or note the change in `03_DECISION-LOG.md` so future
   sessions don't assume they are still down — though see item 2 above regarding `research_hub`'s
   download tool specifically.

6. **Domain-boundary ambiguity for several newly found citations.** The adherence-epidemiology
   citations found in the previously unread remainder (Lin YW 2024, Su M 2025, van Driel ML 2016,
   Religioni U 2025) sit between guideline-risk (epidemiology/institutional-practice framing) and
   safety-pharmacology (adherence as a safety/outcomes lever) domains per `CLAUDE.md` §2's domain
   descriptions. This role has not claimed ownership of verifying them — flagging for the Director to
   assign explicitly rather than have both or neither specialist pick them up.
