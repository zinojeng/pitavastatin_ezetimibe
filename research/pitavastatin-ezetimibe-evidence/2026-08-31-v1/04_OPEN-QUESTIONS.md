# 04_OPEN-QUESTIONS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

Categories: `NEEDS_SOURCE` | `NEEDS_ANALYST` | `NEEDS_METHODS` | `NEEDS_PI`. Additive — do not delete
resolved items, move them to the Resolved section with a pointer to the `03_DECISION-LOG.md` entry
that resolved them.

> **Housekeeping note (Wave 2 dispatch, 2026-08-31):** this file had accumulated several genuinely-
> open items filed under the wrong heading during rapid Wave 1 processing. Reorganized here into
> correct Open/Resolved sections — no content deleted, only re-filed. See git history for the prior
> (messier) version if needed.

## Open

### Wave 2 full-text acquisition targets (dispatched — see `90_CROSS-SESSION-LOG/` Wave 2 dispatch)

- [NEEDS_SOURCE, dispatched to trials-efficacy] Tsujita K et al. 2023 (T-004a) full text —
  PMC10627746 or J-STAGE advance-publication PDF; and Ako J et al. 2024 (T-004b, 52-wk extension)
  full text — PMC10918028. Extract exact arm structure, LDL-C, AE, CK, AST, ALT, HbA1c, and
  pairwise-vs-pooled significance. Use LlamaParse on at least Tsujita 2023.
- [NEEDS_SOURCE, dispatched to trials-efficacy] Citation #33 (Chou MT 2022, Phase III FDC trial)
  own AE/CK/liver-enzyme detail tables — still paywalled as of Wave 1; do not cite specific AE/CK/
  liver numbers from this paper until full text is obtained.
- [NEEDS_SOURCE, dispatched to trials-efficacy] Katzmann JL et al. 2022 (T-012/TE-010) full text —
  needed specifically to resolve the internally-inconsistent cohort-size figures in
  `Tonvasca_2026.md` (`n=6,429/533` vs. `n=1,639/796` for the same comparison — Decision
  2026-08-31-11). **PI-confirmed (2026-08-31): this stays unresolved and no *n* from this study may
  be cited until full text is obtained.** The 4 already-verified percentage/p-value figures (28.4%
  vs. 19.4% LDL-C reduction; 31.5% vs. 21.0% attainment) remain citable.
- [NEEDS_PI] **Taiwan STS 2026 (T-005), 2026 ACC/AHA guideline (#28), and ESC 2025 Focused Update
  (T-007) are all `BLOCKED_FOR_SOURCE` by automated means** (Decision 2026-08-31-13) — all three
  return HTTP 403 Cloudflare bot-challenges, corroborated via Europe PMC metadata
  (`is_open_access:False`, no PMCID for any of the three). guideline-risk correctly did not attempt
  any bot-detection workaround. **Question for the PI: can any of these three PDFs be supplied
  directly (manual download or authenticated/institutional access)?** If so, guideline-risk can
  parse immediately with LlamaParse. Without one of these three, the "extract statin+ezetimibe
  combination-therapy wording" Wave 2 task item cannot be completed — the Gate-2 LlamaParse
  requirement was satisfied on a substitute source (T-014) that doesn't discuss ezetimibe.
- [NEEDS_SOURCE, dispatched to guideline-risk, now the active priority per Director 2026-08-31 —
  the three items above are blocked pending PI] Numeric-threshold/wording confirmation still pending
  for every other guideline document identified in Wave 1 (Taiwan Lp(a) 2026/T-006, 2023 TSC CCS,
  base 2019 ESC/EAS/#34, both 2022 Taiwan lipid-guideline companions/#29/#35, ADA 2025/#32) — Wave 1
  confirmed document *identity* only.

- [NEEDS_SOURCE, dispatched to trials-efficacy] T-015 (REPRIEVE trial, Grinspoon SK et al. NEJM
  2023;389:687-699) — new pitavastatin cardiovascular-outcome RCT found by guideline-risk (routed,
  not independently verified). See Decision 2026-08-31-15. Pitavastatin monotherapy, HIV
  population — do not conflate with HIJ-PROPER or RACING.
- [NEEDS_SOURCE, dispatched to guideline-risk] **111 年健康促進統計年報** (Taiwan Health Promotion
  Administration statistical annual report, ROC 111 = 2022, T-008) — not indexed in PubMed/
  Crossref/paper-search; requires a direct fetch from the 國民健康署 website. Not part of the PI's
  named Wave 2 priorities but still open from Wave 1.
- [NEEDS_SOURCE, dispatched to safety-pharmacology] Singh H et al. 2024 (T-003, DOI
  10.1080/17512433.2024.2433603) and Katzmann JL et al. 2022 (T-012) — seek lawful full text; if
  blocked, record `BLOCKED_FOR_SOURCE`. Validate the DDI matrix (T-010) against the official
  DailyMed/FDA source directly (not a secondary transcription). Parse a lawful safety-domain PDF
  with LlamaParse if one is obtained. **Never use `mcp__research_hub__download_paper`** (permanent
  restriction, Decision 2026-08-31-08/12).
- [NEEDS_SOURCE] Clarithromycin-specific DDI data for pitavastatin — not found in the LIVALO label's
  Section 7 as fetched in Wave 1 (a gap in that source's coverage, not evidence of "no
  interaction"). Part of the safety-pharmacology Wave 2 DDI validation above.
- [NEEDS_SOURCE, Wave 2] safety-pharmacology's own Wave 1 `unresolved-questions.md` (now readable —
  see `20_EVIDENCE/safety-pharmacology/unresolved-questions.md` after the Wave 1→main consolidation)
  additionally flags CKD/elderly FDC safety subgroup data and BCRP-mediated DDI numbers as missing —
  carried forward as Wave 2 targets for that role.

### Other open items (not part of the PI's named Wave 2 dispatch, no urgency)

- [NEEDS_ANALYST] Two internal-consistency flags **within `Tonvasca_2026.md` itself** (informational
  only — the file is read-only, not this project's error to fix): a superscript/reference mismatch
  at line 2796, and citation #33 (Chou MT 2022) printed in two different citation-string formats at
  different points in the deck. Relevant only if/when the PI revises the original slide source.
- [NEEDS_PI] safety-pharmacology-intelligence's own task instructions say "do not run
  git commit/push"; the Director recommended a local commit for durability and safety-pharmacology
  correctly declined absent a direct PI instruction. **Not addressed in the PI's Wave 2
  authorization** — still open if the PI wants that session's Wave 1 output committed directly by
  that session (it otherwise remains safe, uncommitted, in `.claude/worktrees/safety-pharm-wave1/`,
  and its content is already visible to the Director via the Codex-process consolidation into
  `main`).
- [NEEDS_ANALYST] T-006's author list (Taiwan Lp(a) 2026 consensus/review), as reported by
  guideline-risk, contains a duplicated "Wang CY" entry. Preserved as-received per the Numeric
  Integrity Rule (not silently deduplicated) — flag if this citation is used verbatim in any
  downstream output.
- [NEEDS_SOURCE] T-013 (Corsini A, et al. Curr Med Res Opin. 2011;27(8):1551-1562) — safety-
  pharmacology self-queued this for its own verification; not separately named in the PI's Wave 2
  dispatch but falls within its DDI-validation scope.
- [NEEDS_SOURCE] `openevidence` MCP server remains unreachable across every session that has
  reported on it so far. Not part of the PI's Wave 2 authorization (which covers `research_hub`/
  `llamaparse` repair only) — treat as still down until a session reports otherwise.

## Resolved

### PI Wave 2 authorization, 2026-08-31 (Decision 2026-08-31-12 — see that entry for full detail)

- [RESOLVED] Sydhom framing (Decision 2026-08-31-06) — PI-decided: state observational-pooled
  benefit only, RCT-pooled clinical endpoints not statistically significant. Applied to
  `02_SOURCE-INVENTORY.md` citation #26.
- [RESOLVED] `research_hub` download-tool restriction (Decision 2026-08-31-08) — made **permanent**
  by the PI (was interim). `CLAUDE.md` §10 updated.
- [RESOLVED] `50_MANUSCRIPT/` ownership (Decision 2026-08-31-04) — Research Director owns
  coordination until Gate 2. `CLAUDE.md` §3 updated.
- [RESOLVED] Multi-worktree consolidation — PI confirms all four branches + Director's Gate 1
  commits reviewed, secret-scanned, and consolidated into local `main` by the supervising Codex
  process; Director independently verified this via `git log` and merged `main` into its own
  working branch for direct file visibility (not a branch-consolidation act). This session will not
  merge branches into `main` itself going forward.
- [RESOLVED] `research_hub`/`llamaparse` MCP repair confirmed by PI, `llamaparse` passed a live
  dummy-PDF smoke test — see `00_RUN-MANIFEST.md` Wave 2 update.
- [RESOLVED] `.metadata_cache/` added to `.gitignore`.
- [RESOLVED] Session registry created — `90_CROSS-SESSION-LOG/SESSION-REGISTRY.md`.
- [RESOLVED] Security TODO recorded (historical hardcoded `llamaparse` credentials exist outside
  this repo, should be rotated/removed) — `CLAUDE.md` §12. No credential value recorded anywhere.

### Wave 1 items resolved before PI authorization

- [RESOLVED] T-012 (Katzmann JL et al. 2022) citation identity and 4 key figures verified by
  trials-efficacy — see Decision 2026-08-31-11. (The cohort-*n* sub-issue specifically remains open
  — see Wave 2 dispatch targets above.)
- [RESOLVED] Citation #27's DOI transcription discrepancy — Decision 2026-08-31-09.
- [RESOLVED] HIJ-PROPER (T-001) and RACING (T-002) primary publications located; legacy figures
  confirmed to match exactly (trials-efficacy, 2026-08-31; Director has not independently
  re-verified).
- [RESOLVED] T-004/T-004a/T-004b (2 mg vs 4 mg dose comparison) — located via Tsujita 2023 + Ako
  2024 — Decision 2026-08-31-07. (Dose-arm-level AE/CK/liver-enzyme detail still a Wave 2 target,
  see above.)
- [RESOLVED] T-005/T-006/T-007 (Taiwan STS 2026, Taiwan Lp(a) 2026, ESC 2025 Focused Update) located
  and citation-verified by guideline-risk; full citation strings received. (Full-text numeric
  extraction is the Wave 2 target above.)
- [RESOLVED] T-009 domain ownership assigned to safety-pharmacology-intelligence.
- [RESOLVED, no action needed] trials-efficacy's single pre-restriction `download_paper` call (for
  citation #33) — no content returned, no Sci-Hub contamination, no policy violation (predates
  Decision 2026-08-31-08).
- [RESOLVED] T-003 (Singh H et al. 2024) identified and distinguished from citation #26 (Sydhom) —
  Decision 2026-08-31-10.
- [RESOLVED] Citation #23's topic/relevance description corrected (was "statin discontinuation
  outcomes," actually the 2019 Taiwan statin-intolerance consensus/STS precursor).
- [RESOLVED] All 16 of safety-pharmacology's assigned legacy citations verified, zero mismatches.
- [RESOLVED] T-011 routing fragments fully resolved (6 duplicates, 2 genuinely new: T-012, T-013).
- [RESOLVED] T-010 (LIVALO/DailyMed DDI label) full figures received.
- [RESOLVED, Director's own earlier flag withdrawn] Row #35 was never a dual-citation-format issue.
- [RESOLVED, with honest caveat] T-005's citation-verification access-status description corrected
  by guideline-risk via self-correction (landing-page badges, not a confirmed full-text retrieval).
  **Full-text access itself remains an open Wave 2 target** (see above) — only the earlier
  *contradiction between two peers' reports* is resolved, not the underlying access question.
- [RESOLVED] trials-efficacy's worktree has a local commit (durable on disk pending consolidation,
  since superseded by the Codex-process consolidation into `main`).
- [RESOLVED, superseded] `Tonvasca_2026.md`'s previously-unread remainder (lines 1795–2811) — read
  in full by guideline-risk during Wave 1.
- [RESOLVED] `research_hub`/`llamaparse` Wave 0 connectivity failures — superseded by the Wave 2 PI
  repair confirmation above; no longer "partially resolved," now fully resolved.
