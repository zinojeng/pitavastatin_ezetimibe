# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Last updated: 2026-08-31 (Wave 1, Research Director)

## Current Gate

**READY_FOR_NEXT_WAVE** (Gate 0 passed; Wave 1 in progress — Gate 1 not yet reached)

## Wave

1 — Source / Evidence Verification (in progress; 2 of 3 specialists report complete/near-complete)

## Completed — Wave 0

- Repository initialized: `CLAUDE.md`, `README.md`, `.gitignore`, `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`.
- Run directory created with all mandated files/subdirectories (see `00_RUN-MANIFEST.md`).
- Persistent roles, file ownership matrix, Wave/Gate rules, message schema, Evidence Hierarchy and
  Decision Taxonomies, MCP source policy, licensing/secrets rules, and prompt templates written into
  `CLAUDE.md`.
- Prioritized Search Protocol (10 items) written into `CLAUDE.md` §5.
- Preliminary source catalog of `Tonvasca_2026.md`'s ~33 embedded citations in `02_SOURCE-INVENTORY.md`.
- Legacy input files preserved unmodified at repo root; checksummed in `00_RUN-MANIFEST.md`.

## Wave 1 progress

All three domain specialists online and confirmed reachable (`pit-eze-guideline-risk`,
`pit-eze-safety-pharmacology`, `pit-eze-trials-efficacy`); this session confirmed addressable as
`pit-eze-research-director`.

- **guideline-risk-intelligence** — `READY_FOR_INTEGRATION`. All 11 assigned legacy citations
  verified (1 DOI transcription error found and logged, Decision 2026-08-31-09). Read the full
  previously-unread `Tonvasca_2026.md` remainder; found 2 new guideline citations (#34/#35) and a
  4-citation adherence-epidemiology cluster (T-009, reassigned to safety-pharmacology). All three
  previously-unlocated guideline Search Protocol targets (Taiwan STS 2026/T-005, Taiwan Lp(a)
  2026/T-006, ESC 2025 Focused Update/T-007) now located and citation-verified. Flagged and
  correctly handled a Sci-Hub compliance concern on `mcp__research_hub__download_paper` (Decision
  2026-08-31-08 — interim project-wide restriction on that tool). Committed and **pushed to origin**
  (`worktree-pit-eze-guideline-risk-wave1`) — not yet merged to `main`. Awaiting: full formatted
  citations for #34/#35/T-005/T-006/T-007/T-009, and clarification of whether a second
  tool-compliance concern (beyond the Sci-Hub one, already resolved) was meant to be flagged.
- **trials-efficacy-intelligence** — `READY_WITH_PENDING_ITEMS`. Wave 1 verification complete for
  Search Protocol items 5–9. Legacy HIJ-PROPER (T-001)/RACING (T-002) figures confirmed to match
  primary publications exactly. Found two new sources (Tsujita 2023/T-004a, Ako 2024/T-004b) closing
  the previously-unlocated 2mg-vs-4mg dose-comparison gap (Decision 2026-08-31-07). Flagged a source
  conflict: Sydhom et al. 2024's (citation #26) clinical-outcome benefit is observational-pooled-only
  per its own abstract, not RCT-pooled as `Tonvasca_2026.md`'s framing risks implying — routed
  `NEEDS_PI` (Decision 2026-08-31-06). Three legacy citations (#20 CEPHEUS/Chiang 2016, #21
  DYSIS-II/Gitt 2017, #25 Masana 2020) could not be located — flagged, not dropped. Output sits
  **uncommitted** in its own isolated worktree (`worktree-trials-efficacy-wave1`) — asked to at
  least locally commit. Awaiting: full citations for Tsujita 2023/Ako 2024; clarification on its
  "9 verified" count vs. the 3 not-located legacy citations (bookkeeping question, not a blocker).
- **safety-pharmacology-intelligence** — `READY_WITH_PENDING_ITEMS`. Confirmed scope (legacy
  citations #3–16, 23, 26-joint; new-source discovery for items 3–5 approved as a Wave 1/2 blend
  since it doesn't build on any unverified legacy claim). Deprioritized Lp(a)/item 10, correctly.
  Reported `research_hub`/`llamaparse` reachable in its own session (logged additively in
  `00_RUN-MANIFEST.md` without overwriting the Wave 0 record). Three sub-agent searches were in
  progress as of its last report; notified of the new research_hub restriction (Decision
  2026-08-31-08) and its new T-009 assignment. No completion report yet.

All cross-session exchanges logged verbatim in `90_CROSS-SESSION-LOG/`.

## Decisions logged this Wave (see `03_DECISION-LOG.md` for full text)

- 2026-08-31-05: `02_SOURCE-INVENTORY.md` is Director-owned; specialists report findings instead of
  editing it directly. `CLAUDE.md` §3 patched.
- 2026-08-31-06: Sydhom et al. 2024 RCT-vs-observational framing gap — `NEEDS_PI`.
- 2026-08-31-07: Tsujita 2023 / Ako 2024 close Search Protocol item 5 (T-004) — `VERIFIED_AND_REPLACE`
  (located-status only).
- 2026-08-31-08: **Sci-Hub compliance** — `mcp__research_hub__download_paper` restricted
  project-wide pending PI's final call. `CLAUDE.md` §10 patched. Flagged to PI directly.
- 2026-08-31-09: Citation #27 DOI transcription error — `VERIFIED_AND_REPLACE` (DOI field only).

## Sync-state caveat (operational, not a research blocker) — escalated to PI

This Director session is a background job isolated in a git worktree (`.claude/worktrees/wave0-init`,
branch `worktree-wave0-init`, commit history through Wave 1 kickoff). `main` already contains Wave 0
content (apparently merged there outside this session). This session's own `git push` to `origin`
initially failed twice then succeeded on a third attempt (transient, not a hard block).
`pit-eze-guideline-risk`'s branch also pushed to `origin` successfully.
`pit-eze-trials-efficacy` made local commits only (no push, per its own task instructions).
`pit-eze-safety-pharmacology` has not committed at all as of this update. **There are now four
separate pieces of work in play** — `origin/worktree-wave0-init` (Director, pushed),
`origin/worktree-pit-eze-guideline-risk-wave1` (pushed), `worktree-trials-efficacy-wave1` (committed
locally only), and `worktree-safety-pharm-wave1` (uncommitted) — with no single session able to
consolidate all four into `main`. Three of the four sessions have independently reported hitting
this same worktree-isolation problem, unprompted. This looks like a structural property of how this
multi-agent run was set up, not a one-off glitch — worth the PI's attention as a process issue for
future runs, not just this one. See the report delivered to the user this turn.

## Update — citation follow-ups closed (both peers)

guideline-risk-intelligence supplied full formatted citations for #34, #35, T-005 (Taiwan STS
2026), T-006 (Taiwan Lp(a) 2026), T-007 (ESC 2025 Focused Update), and T-009 (adherence cluster,
explicitly flagged copied-not-verified). trials-efficacy-intelligence supplied full Crossref-sourced
citations for T-004a (Tsujita 2023)/T-004b (Ako 2024), disclosed one no-op pre-restriction
research_hub call (no policy issue), confirmed a local commit in its own worktree, and resolved the
Director's "9 vs 3" bookkeeping question. All entered into `02_SOURCE-INVENTORY.md`; see
`90_CROSS-SESSION-LOG/2026-08-31_wave1-followups.md`. Two new `NEEDS_ANALYST` items opened: T-009
citations need independent verification (owner: safety-pharmacology), T-006's duplicated "Wang CY"
author entry needs a primary-source check before verbatim use.

## Update — all three specialists have now reported Wave 1 complete

- **safety-pharmacology-intelligence** — `READY_WITH_PENDING_ITEMS`. All 16 assigned legacy
  citations verified (zero mismatches). Completed the deferred read of `Tonvasca_2026.md`'s
  remainder, found more citations (routed as T-011, several likely duplicates of already-catalogued
  ones — needs guideline-risk confirmation) and 2 informational flags on the legacy source's own
  internal inconsistencies. Identified Singh H et al. 2024 as the real T-003 source (Decision
  2026-08-31-10 — must never be conflated with Sydhom 2024/citation #26). Found the FDA/DailyMed
  Livalo label DDI matrix (T-010). Flagged citation #33's own AE/CK/liver tables as unverified/
  paywalled, substituted K-924 (Japan) data tagged `INDIRECT EVIDENCE` for population/product
  reasons. Corrected citation #23's mislabeled topic description. Independently corroborated T-005
  but with an access-status discrepancy vs. guideline-risk's report (flagged, unresolved). **Also
  hit the worktree-isolation-blocks-shared-checkout problem** — output lives uncommitted in
  `.claude/worktrees/safety-pharm-wave1/`, not yet in git at all.

**All three domain specialists have now reported Wave 1 substantially complete.** Remaining before
Gate 1 can be formally called: the citation-routing/access-status loose ends below, and — more
significantly — consolidating four separate worktrees (Director's, guideline-risk's, trials-
efficacy's, safety-pharmacology's) into one coherent `main`. See escalation below and the report
delivered to the PI this turn.

## Pending (Wave 1 exit / Gate 1 criteria)

- T-005's access-status discrepancy (guideline-risk: open-access; safety-pharmacology: paywalled) —
  needs reconciliation.
- T-011 routing fragments — full citations and duplicate-vs-new determination, from
  safety-pharmacology and guideline-risk respectively.
- T-003, T-010 exact citation/figure detail from safety-pharmacology (currently only has summary
  figures from its message).
- safety-pharmacology to at least locally commit its worktree (requested; not yet confirmed done).
- PI decision on the Sydhom framing gap (Decision 2026-08-31-06) and the research_hub/Sci-Hub tool
  policy (Decision 2026-08-31-08).
- PI decision on `50_MANUSCRIPT/` ownership (Decision 2026-08-31-04) — not a Wave 1 blocker.
- Consolidation of the three unmerged worktrees into `main` (see Sync-state caveat above).
- Re-confirm `openevidence` connectivity (still down everywhere reported); `research_hub`/
  `llamaparse` connectivity appears session-specific, not a fixed fact — no single re-test needed,
  each session should check its own.

## Blocked

None at the repository-content level — all three specialists are actively producing verified,
well-provenanced findings. The **sync/consolidation gap** above is an operational blocker on making
Director-side and specialist-side Wave 1 output durable and visible across sessions; it does not
block the specialists' own in-progress work, which continues in their respective worktrees.

## Next action

Director awaits safety-pharmacology's completion report and the two specialists' outstanding
citation strings. PI: resolve the multi-worktree consolidation gap (merge the three branches into
`main`, or grant push permission to the blocked sessions) and make the two `NEEDS_PI` calls above.
