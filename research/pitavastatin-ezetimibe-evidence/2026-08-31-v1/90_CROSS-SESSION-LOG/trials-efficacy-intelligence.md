# Cross-session log — trials-efficacy-intelligence

Append-only. Newest entry at bottom (chronological), per CLAUDE.md §6.

---

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]             2026-08-31-v1
[FROM]            trials-efficacy-intelligence
[TO]              Research Director
[TYPE]            CROSS_SESSION_TEST
[FINDING]         ListAgents confirms reachable sockets for pit-eze-research-director (idle),
                  pit-eze-guideline-risk (busy), pit-eze-safety-pharmacology (busy). No prior
                  90_CROSS-SESSION-LOG entries found -- this session is first to log. MCP
                  connectivity re-checked per CLAUDE.md §10: research_hub now CONNECTED
                  (was down at Wave 0); llamaparse CONNECTED (tool available, not yet invoked);
                  openevidence still CONNECTION_CLOSED (unchanged from Wave 0). paper-search,
                  tavily, google-scholar all available.
[IMPACT]          Proceeding into Wave 1 Source/Evidence Verification for trials-efficacy owned
                  domain (CLAUDE.md §2.3, §5 items 5-9) using the confirmed-available lawful
                  source set.
[OUTPUT_PATHS]    30_METHODS/trials-efficacy/search-log.md
[CONFIDENCE]      HIGH
[STATUS]          READY_FOR_NEXT_WAVE
```

---

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]             2026-08-31-v1
[FROM]            trials-efficacy-intelligence
[TO]              Research Director
[TYPE]            EVIDENCE_UPDATE
[QUESTION]        (none blocking)
[FINDING]         Wave 1 Source/Evidence Verification complete for trials-efficacy owned domain.
                  9 citations extracted and verified (TE-001..TE-009), covering all of Search
                  Protocol items 6, 7, 8, 9 and most of item 5. Two NEW sources not previously
                  catalogued in 02_SOURCE-INVENTORY.md were found and directly answer item 5
                  ("pitavastatin 2 mg vs 4 mg", previously listed as T-004/not-yet-located):
                  Tsujita K et al. J Atheroscler Thromb 2023 (Japan, 4-arm K-924 RCT: pitavastatin
                  2mg/4mg/2mg+eze10/4mg+eze10, 12-wk LDL-C %change -39.5/-45.2/-51.4/-57.8) and
                  its 52-week open-label extension (Ako J et al. J Atheroscler Thromb 2024).
                  All numeric figures already quoted in pitavastatin topic.md and Tonvasca_2026.md
                  for HIJ-PROPER (32.8% vs 36.9%, HR 0.89, 95% CI 0.76-1.04, P=0.152; sitosterol
                  subgroup HR 0.71, 95% CI 0.56-0.91) and RACING (overall 9.1% vs 9.9%; DM
                  subgroup 10.0% vs 11.3%, HR 0.89, 95% CI 0.64-1.22, P=0.460; LDL<70 79.9% vs
                  66.8%; intolerance 5.2% vs 8.7%) were independently confirmed via PubMed against
                  the primary publications and match EXACTLY -- no correction needed to these
                  legacy figures. One SOURCE_CONFLICT candidate flagged: Tonvasca_2026.md cites
                  Sydhom et al. 2024 (BMC Cardiovasc Disord) for "combination therapy benefit
                  surpasses high-intensity statin" without the RCT-vs-observational qualifier the
                  source paper's own abstract insists on (RCT-pooled analysis found NO significant
                  clinical-endpoint difference; only observational-pooled analysis showed benefit).
                  Three pre-existing citations (CEPHEUS/Chiang J Atheroscler Thromb 2016, DYSIS-II/
                  Gitt Atherosclerosis 2017, Masana Curr Cardiol Rep 2020) could NOT be located as
                  exact matches after multiple search attempts -- flagged, not silently corrected.
[IMPACT]          Level 1/2/3 evidence-hierarchy framework in pitavastatin topic.md §6 is CONFIRMED
                  unchanged after independent verification: Level 1 (LDL efficacy) strong and now
                  better-supported with a new dose-comparison source; Level 2 (RACING) strong but
                  remains indirect (rosuvastatin, not pitavastatin); Level 3 (HIJ-PROPER) remains
                  the weakest link, no newer pitavastatin/ezetimibe-specific hard-outcome trial
                  found in Wave 1. The Sydhom SOURCE_CONFLICT, if left uncorrected, risks
                  overstating Level 2 evidence as RCT-grade when it is observational-grade for the
                  specific clinical-outcome claim as worded in Tonvasca_2026.md.
[ACTION]          Requesting Research Director: (1) log the Sydhom RCT-vs-observational framing
                  gap in 03_DECISION-LOG.md and route to PI if a manuscript/slide-language decision
                  is needed; (2) note the 2 new sources (Tsujita 2023, Ako 2024) for addition to
                  02_SOURCE-INVENTORY.md's RCTs table (Director-owned file, not edited by this
                  role); (3) be aware Wave 2 full-text acquisition is still pending for several
                  sources (see fulltext-manifest.md) before AE/CK/liver-enzyme dose-comparison
                  detail for Search Protocol item 5 can be considered complete.
[OUTPUT_PATHS]    30_METHODS/trials-efficacy/search-log.md
                  10_DATA/trials-efficacy/extraction-table.csv
                  10_DATA/trials-efficacy/fulltext-manifest.md
                  20_EVIDENCE/trials-efficacy/evidence-map.md
                  20_EVIDENCE/trials-efficacy/unresolved-questions.md
[CONFIDENCE]      HIGH (numeric verification against primary-publication PubMed abstracts);
                  MODERATE (population-scope detail for TE-001 and full dose-arm safety detail for
                  TE-002/003, both pending full-text access -- see unresolved-questions.md)
[STATUS]          READY_WITH_PENDING_ITEMS
```

---

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]             2026-08-31-v1
[FROM]            trials-efficacy-intelligence
[TO]              Research Director
[TYPE]            STATUS_REPORT
[FINDING]         (Consolidated log of the follow-up exchange after the EVIDENCE_UPDATE above,
                  sent via SendMessage but not yet appended here.) Provided full formatted
                  citations for Tsujita 2023 / Ako 2024 (added to search-log.md). Acknowledged
                  Decision 2026-08-31-08 (no more calls to mcp__research_hub__download_paper) and
                  disclosed one pre-restriction call for TE-001's DOI that returned nothing.
                  Clarified the 9-vs-3 citation-count bookkeeping (4 verified-legacy + 5
                  topic-notes-trials/new-finds = 9 TE-ids; 3 not-located legacy citations counted
                  separately, non-overlapping) -- now also recorded in search-log.md. Logged Q6 in
                  unresolved-questions.md per Director's observation: TE-002's journal title reads
                  "vs. Pitavastatin" (2-arm phrasing) while its abstract confirms an unambiguous
                  4-arm design (N=293) -- no actual contradiction, but exact statistical
                  comparison structure across arms needs full-text confirmation before
                  40_SYNTHESIS/ cites dose-pair significance. Ran local `git commit` only (no
                  push) twice in my own worktree per Director's recommendation (commits 62db3f3,
                  fc9af43 on branch worktree-trials-efficacy-wave1) -- discovered the original 6
                  output files were already present in an earlier automatic checkpoint commit
                  (dc6ee2f, authored "Dr Tseng") that this role did not itself run.
[IMPACT]          No open items from this exchange remain outstanding on this role's side.
[ACTION]          None pending.
[OUTPUT_PATHS]    30_METHODS/trials-efficacy/search-log.md
                  10_DATA/trials-efficacy/extraction-table.csv
                  20_EVIDENCE/trials-efficacy/unresolved-questions.md
                  10_DATA/trials-efficacy/fulltext-manifest.md
[CONFIDENCE]      HIGH
[STATUS]          READY_FOR_NEXT_WAVE
```

---

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]             2026-08-31-v1
[FROM]            trials-efficacy-intelligence
[TO]              Research Director
[TYPE]            EVIDENCE_UPDATE
[FINDING]         Verified T-012 (Katzmann JL et al. Clin Res Cardiol 2022;111(3):243-252,
                  DOI 10.1007/s00392-020-01740-8, PMID 32949286) per Director's assignment
                  (source originally surfaced by safety-pharmacology). Journal/DOI/numbers
                  (-28.4%/-19.4%/31.5%/21.0%) match Tonvasca_2026.md exactly -- VERIFIED.
                  Disclosure: this citation was already read by this role during Wave 1
                  (Tonvasca_2026.md lines 2296-2345, 2803) but was NOT separately catalogued at
                  the time -- an oversight, now corrected as TE-010. Found a NUMERIC INTEGRITY
                  issue while verifying: the same Tonvasca_2026.md slide states two different,
                  internally inconsistent sample sizes for the same FDC-vs-separate-pills
                  comparison (header: n=6,429/533; results table: n=1,639/796, with the relative
                  size even reversed). PubMed abstract only gives the overall study N=311,242, not
                  the ezetimibe-subgroup n, so neither pair can be confirmed or rejected without
                  full text.
[IMPACT]          Per Numeric Integrity Rule, both n-pairs preserved as-printed and flagged
                  POSSIBLE_ERROR/NEEDS_ANALYST, not resolved by guessing. 40_SYNTHESIS/ should not
                  cite either n from Tonvasca_2026.md for this study until Wave 2 full-text access
                  resolves it.
[ACTION]          Requesting: full-text acquisition of Katzmann 2022 be added to Wave 2 priority
                  list (Crossref indicates a Springer pdf_url, possibly open access).
[OUTPUT_PATHS]    10_DATA/trials-efficacy/extraction-table.csv (TE-010)
                  20_EVIDENCE/trials-efficacy/evidence-map.md
                  20_EVIDENCE/trials-efficacy/unresolved-questions.md (Q7)
[CONFIDENCE]      HIGH (citation identity and the 4 key numbers); the n-mismatch itself is a
                  confirmed discrepancy in the legacy source, not an uncertainty in my verification
[STATUS]          READY_FOR_NEXT_WAVE
```

---

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]             2026-08-31-v1
[FROM]            trials-efficacy-intelligence
[TO]              Research Director
[TYPE]            STATUS_REPORT
[FINDING]         Narrow post-Gate-2 persistence repair (Director-assigned; Wave 3 NOT opened).
                  TE-002 (Tsujita 2023) and TE-003 (Ako 2024) PDFs/LlamaParse outputs, previously
                  stored under a temporary $CLAUDE_JOB_DIR path (see Wave 2 entries above), were
                  confirmed missing. Re-downloaded both from the exact J-STAGE URLs already
                  recorded in fulltext-manifest.md (HTTP 200 both) into a new persistent,
                  role-owned, gitignored path: 20_EVIDENCE/trials-efficacy/fulltext/ (covered by
                  existing .gitignore rule **/20_EVIDENCE/**/fulltext/, verified file-by-file with
                  `git check-ignore -v`). SHA-256 of both re-downloaded PDFs is IDENTICAL to the
                  hashes originally recorded in Wave 2 (afe6befc...4022c26 for TE-002,
                  1e103ff0...1ac960 for TE-003) -- confirms byte-identical source content, no
                  publisher revision. Both re-parsed successfully via
                  mcp__llamaparse__parse_pdf_to_markdown (save_output=true), markdown saved beside
                  each PDF in the same directory. Manually inspected head/tail and ran a
                  truncation/error grep on both .md outputs -- no truncation or parse-failure
                  markers found (only legitimate statistical-terminology hits for "error"). Output
                  character counts differ slightly from the original Wave 2 log (114,243 vs
                  114,893 bytes for TE-002; 106,855 vs 107,117 for TE-003) despite identical source
                  PDF bytes -- attributed to normal LlamaParse layout-inference variance between
                  calls, not data loss; content completeness verified by inspection.
[IMPACT]          TE-002/TE-003 full text and parsed markdown are now durably available at a
                  role-owned path for Wave 3 (or later) extraction use. No change to any previously
                  committed Wave 1/Wave 2 conclusion; wave2-fulltext-extraction.md content
                  unchanged.
[ACTION]          None pending on this role's side. Wave 3 remains NOT opened per task scope.
[OUTPUT_PATHS]    10_DATA/trials-efficacy/fulltext-manifest.md (new section: "Post-Gate-2 持久化修復")
[CONFIDENCE]      HIGH (SHA-256 hash match confirms source-content identity; manual inspection
                  confirms parse completeness)
[STATUS]          READY_FOR_NEXT_WAVE
```
