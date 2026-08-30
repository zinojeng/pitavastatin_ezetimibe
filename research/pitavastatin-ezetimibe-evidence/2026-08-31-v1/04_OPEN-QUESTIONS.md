# 04_OPEN-QUESTIONS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

Categories: `NEEDS_SOURCE` | `NEEDS_ANALYST` | `NEEDS_METHODS` | `NEEDS_PI`. Additive — do not delete
resolved items, move them to a "Resolved" section at the bottom with a pointer to the
`03_DECISION-LOG.md` entry that resolved them.

## Open

- [NEEDS_PI] Should a dedicated **manuscript/presentation-intelligence** persistent role be created
  for this run, to eventually turn `40_SYNTHESIS/` content into slide/manuscript material in
  `50_MANUSCRIPT/`? Left unowned at Wave 0 (Decision 2026-08-31-04). See `CLAUDE.md` §3 and
  `03_DECISION-LOG.md` (2026-08-31-04).

- [NEEDS_PI] **Sci-Hub compliance flag on `mcp__research_hub__download_paper`.** This tool's own
  internal multi-source search includes Sci-Hub with no exposed opt-out (confirmed via the tool's
  own response text). No Sci-Hub content has entered the repo — the one call made returned nothing —
  but Director has imposed an interim project-wide restriction on this specific tool pending PI's
  final call on whether `research_hub` (whose metadata-only tools remain permitted) should be
  avoided altogether for this project. See Decision 2026-08-31-08, `CLAUDE.md` §10.

- [NEEDS_SOURCE] `openevidence` MCP server remains unreachable across all sessions that have
  reported on it so far (Wave 0 Director session, Wave 1 safety-pharmacology session both saw
  CONNECTION_CLOSED). `research_hub` and `llamaparse` connectivity is apparently session-specific —
  down for the Director's Wave 0 session, reachable for at least two Wave 1 specialist sessions — so
  treat per-session reachability as needing its own check rather than assuming project-wide status
  either way (see `00_RUN-MANIFEST.md` Wave 1 update).

- [NEEDS_SOURCE] Full-text acquisition and numeric-threshold extraction still pending (Wave 2) for
  every guideline document guideline-risk-intelligence *identified and citation-verified* in Wave 1
  (2026 ACC/AHA, 2025 ESC/EAS Focused Update, Taiwan STS 2026, Taiwan Lp(a) 2026, 2023 TSC CCS, the
  base 2019 ESC/EAS guideline, both 2022 Taiwan lipid-guideline companions, ADA 2025 Ch.10) — Wave 1
  confirmed document *identity* only; the specific numeric thresholds/wording `pitavastatin topic.md`
  attributes to these documents are not yet independently re-confirmed against primary-source text.
  Also pending: dose-arm-level AE/CK/liver-enzyme/CKD/elderly safety detail for the newly found
  Tsujita 2023 / Ako 2024 dose-comparison RCTs (T-004a/T-004b) — full-text needed, not yet acquired.

- [NEEDS_SOURCE] **111 年健康促進統計年報** (Taiwan Health Promotion Administration statistical
  annual report, ROC 111 = 2022), cited in `Tonvasca_2026.md`'s closing slide for Taiwan elderly
  HTN/hyperglycemia/hyperlipidemia prevalence (T-008). Not indexed in PubMed/Crossref/paper-search;
  requires a direct fetch from the 國民健康署 website. Flagged as Wave 2, not attempted under Wave 1
  time pressure per guideline-risk's report.

- [NEEDS_ANALYST] T-009's four adherence-epidemiology citations were copied by guideline-risk exactly
  as printed in `Tonvasca_2026.md`'s footnotes but explicitly **not** independently PMID/DOI-resolved
  or cross-checked. safety-pharmacology-intelligence (new owner, per below) should verify them in its
  own Wave 1/2 pass rather than treating guideline-risk's transcription as confirmed.

- [NEEDS_ANALYST] T-006's author list (Taiwan Lp(a) 2026 consensus/review), as reported by
  guideline-risk, contains a duplicated "Wang CY" entry. Preserved as-received per the Numeric
  Integrity Rule (not silently deduplicated) — flag if this citation is used verbatim in any
  downstream output; someone should confirm against the primary source whether this is a genuine
  duplicate-author transcription or two distinct co-authors sharing a transliterated name.

## Resolved

- [RESOLVED] Citation #27's DOI transcription discrepancy (printed `10.6314/JIMT.202412_35(6).04.04`
  vs correct `10.6314/JIMT.202412_35(6).04`) — see Decision 2026-08-31-09, `02_SOURCE-INVENTORY.md`
  row #27.

- [RESOLVED] HIJ-PROPER (T-001) and RACING (T-002) primary publications located; all numeric figures
  previously quoted from `pitavastatin topic.md`/`Tonvasca_2026.md` independently confirmed to match
  the primary publications exactly (trials-efficacy-intelligence report, 2026-08-31; Director has not
  yet independently re-verified — see `02_SOURCE-INVENTORY.md`).

- [RESOLVED] Search Protocol item 5 / T-004 (2 mg vs 4 mg dose comparison) — previously "not yet
  located," now answered by a direct 4-arm Japanese RCT (Tsujita K et al. 2023, T-004a) plus its
  52-week extension (Ako J et al. 2024, T-004b). See Decision 2026-08-31-07. (Dose-arm-level AE/CK/
  liver-enzyme detail still pending — see Open items above.)

- [RESOLVED] Search Protocol items 1/2/10's previously-unlocated guideline targets (Taiwan STS 2026,
  Taiwan Lp(a) 2026, ESC 2025 Focused Update — T-005/T-006/T-007) are now located and
  citation-verified by guideline-risk-intelligence (2026-08-31). Exact citation strings still owed
  (see Open items above); full-text numeric extraction is Wave 2.

- [RESOLVED] Domain ownership for the four adherence-epidemiology citations found in the previously
  unread `Tonvasca_2026.md` remainder (T-009) — Director assigns to safety-pharmacology-intelligence
  (see `02_SOURCE-INVENTORY.md` T-009 row).

- [RESOLVED] Full formatted citations for #34, #35, T-005, T-006, T-007 (guideline-risk) and
  T-004a/T-004b (trials-efficacy, Crossref-sourced) received and entered into
  `02_SOURCE-INVENTORY.md`. T-009's citations also received but remain unverified (see above).

- [RESOLVED, no action needed] trials-efficacy-intelligence disclosed a single pre-restriction call
  to `mcp__research_hub__download_paper` (for citation #33/Chou 2022's DOI), made *before* Decision
  2026-08-31-08 existed. The call failed outright ("not found in any of 13 academic databases"), no
  file/content of any kind was returned, and no Sci-Hub link or content appeared in the response —
  no contamination, no policy violation (the restriction did not yet exist). Logged here for
  transparency only; trials-efficacy will not call this tool again and will use `search_unpaywall`
  or institutional/PI-provided access for Wave 2 full-text acquisition instead.

- [RESOLVED] Search Protocol item 3 / T-003 (pitavastatin NODM systematic review, previously "not
  yet located," generically referenced in `pitavastatin topic.md`) — identified as Singh H et al.
  2024 (PMID 39587804) by safety-pharmacology. See Decision 2026-08-31-10 — explicitly distinct
  from, and must never be conflated with, citation #26 (Sydhom P et al. 2024).

- [RESOLVED] Citation #23's topic/relevance description was wrong in the Wave 0 catalog ("statin
  discontinuation outcomes"); corrected to "2019 Taiwan statin-intolerance consensus (STS
  precursor)" per safety-pharmacology's 2026-08-31 report. See `02_SOURCE-INVENTORY.md` row #23
  (original wording struck through, not silently deleted).

- [RESOLVED] All 16 of safety-pharmacology's assigned legacy citations (#3–16, 23, 26-joint)
  verified with zero mismatches (2026-08-31).

- [RESOLVED] T-011 routing fragments fully resolved: 6 of the 8 fragments were duplicates of
  already-catalogued citations (2 more than safety-pharmacology's own check initially found — the
  Director caught that "Mach F... Eur Heart J 2020" = row #34 exactly, and "Huang PH... in-press
  PII" is likely the same paper as row #35 in a different citation format); 2 were genuinely new
  (T-012 Katzmann JL → trials-efficacy, T-013 Corsini A → safety-pharmacology's own queue). See
  `02_SOURCE-INVENTORY.md` T-011/T-012/T-013 rows.

- [RESOLVED] T-003 (Singh H et al. 2024) and T-010 (LIVALO/DailyMed DDI label) full citations and
  exact figures received from safety-pharmacology, 2026-08-31 — entered into
  `02_SOURCE-INVENTORY.md`.

- [RESOLVED] trials-efficacy-intelligence's worktree (`worktree-trials-efficacy-wave1`) now has a
  local commit (`62db3f3`, on top of a pre-existing environment checkpoint commit `dc6ee2f`
  authored "Dr Tseng") — durably saved on disk even though not yet merged to `main`. Same
  consolidation gap as the other two worktrees; see Sync-state caveat in `05_STATUS.md`.

- [RESOLVED, superseded] `Tonvasca_2026.md` lines 1795–2811 unread remainder (Decision 2026-08-31-02)
  — read in full by guideline-risk-intelligence during Wave 1 (2026-08-31); new citations found are
  logged in `02_SOURCE-INVENTORY.md` (#34, #35, T-009) and above.

- [PARTIALLY RESOLVED] `research_hub`/`llamaparse` Wave 0 connectivity failures (Decision
  2026-08-31-03) — reachable in at least two Wave 1 specialist sessions; appears session-specific
  rather than a fixed environment fact. `openevidence` remains down everywhere reported so far. See
  the still-open connectivity item above for the current framing.

- [NEEDS_ANALYST] T-005's access-status discrepancy: guideline-risk reported the Taiwan STS 2026
  consensus (DOI 10.1016/j.jfma.2026.04.111) as open-access/CC-licensed; safety-pharmacology
  independently found the same DOI but describes it as abstract-level-only/paywalled. Both peers
  verified the same source and disagree on accessibility — needs reconciliation before Wave 2
  full-text work assumes either. See `02_SOURCE-INVENTORY.md` T-005 row.

- [NEEDS_ANALYST] Two internal-consistency flags **within `Tonvasca_2026.md` itself** (not this
  project's error to fix, since the file is read-only — informational only): a superscript/reference
  mismatch at line 2796, and citation #33 (Chou MT 2022) printed in two different citation-string
  formats at different points in the deck. Relevant only if/when the PI revises the original slide
  source.

- [NEEDS_PI] safety-pharmacology-intelligence declined the Director's recommendation to make a local
  `git commit` in its own worktree (no push), citing an explicit instruction in its own task
  assignment ("do not run git commit/push") that it does not consider a peer recommendation
  sufficient basis to override — correctly reasoning that relaxing that instruction is a PI-level
  call, not a Director-level one. Director agrees this is the right boundary for the peer to hold.
  **If the PI wants safety-pharmacology's Wave 1 output committed for durability, that instruction
  needs to come from the PI directly to that session.** Its files remain safe in
  `.claude/worktrees/safety-pharm-wave1/` regardless (a worktree persists whether or not it has been
  committed to).

- [NEEDS_ANALYST] Row #35 (Huang PH et al., 2022 Taiwan primary-prevention guideline, final
  citation `J Formos Med Assoc. 2022;121(12):2393-2407`) may be the same underlying paper as a
  citation appearing elsewhere in `Tonvasca_2026.md` in pre-print PII form
  (`J Formos Med Assoc. 2022;S0929-6646(22)00215-7`) — flagged by cross-referencing
  safety-pharmacology's T-011 report against the existing #35 row. If confirmed, this is another
  instance of the legacy source citing the same paper in two different formats (same class of issue
  already flagged for citation #33/Chou MT 2022) — not a new source, just another internal
  consistency flag in the read-only legacy file.

- [NEEDS_SOURCE] T-013 (Corsini A, et al. Curr Med Res Opin. 2011;27(8):1551-1562) — used in
  `Tonvasca_2026.md` to support the CYP3A4-independence framing for statin DDI risk.
  safety-pharmacology self-identified this as within its own domain but outside its originally
  assigned 16 citations; added to its own verification queue. No Director action needed.

- [NEEDS_SOURCE] T-012 (Katzmann JL, et al. Clin Res Cardiol. 2022;111(3):243-252 — FDC vs.
  separate-pill adherence/efficacy) — genuinely new source found by safety-pharmacology while
  routing T-011, assigned to trials-efficacy-intelligence for independent verification.

- [NEEDS_SOURCE] Clarithromycin-specific DDI data for pitavastatin could not be found in the LIVALO
  label's Section 7 as fetched (T-010) — a gap in that source's coverage, not evidence of "no
  interaction." Still an open Wave 2 acquisition target if this specific interaction is needed.

- [NEEDS_SOURCE] Citation #33's (Chou MT 2022, Phase III FDC trial) own AE/CK/liver-enzyme detail
  tables remain unverified — paywalled, per safety-pharmacology. Do not cite specific AE/CK/liver
  numbers from this paper until full text is obtained (Wave 2). K-924/Japan trials (T-004a/T-004b)
  provide a same-drug-combination but different-population substitute, explicitly tagged `INDIRECT
  EVIDENCE` for Taiwan-population claims — see `02_SOURCE-INVENTORY.md` T-004b row.

- [NEEDS_SOURCE, Wave 2] safety-pharmacology's own unresolved-questions.md (unreachable in its
  unmerged worktree) reportedly also flags: CKD/elderly FDC safety subgroup data, BCRP-mediated DDI
  numbers, and clarithromycin-specific DDI data as still missing. Carried forward here since the
  Director cannot read the source file directly; ask safety-pharmacology to restate detail when its
  worktree is consolidated or on request.

## Still unverified (carried forward, unchanged)

Every numeric figure not explicitly marked "Verified" in `02_SOURCE-INVENTORY.md` remains an
unverified legacy figure and may not be cited in `20_EVIDENCE/` or `40_SYNTHESIS/` as confirmed —
this includes citations #20 (Chiang/CEPHEUS), #21 (Gitt/DYSIS-II), and #25 (Masana), which
trials-efficacy-intelligence reports it could **not** locate as exact matches after multiple search
attempts (flagged, not silently corrected or dropped — see `02_SOURCE-INVENTORY.md`).
