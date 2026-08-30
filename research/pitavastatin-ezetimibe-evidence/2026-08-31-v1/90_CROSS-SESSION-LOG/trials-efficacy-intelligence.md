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
