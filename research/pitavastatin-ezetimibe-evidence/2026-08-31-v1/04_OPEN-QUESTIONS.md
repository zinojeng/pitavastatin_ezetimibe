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

### Wave 2 Challenge Round findings (Gate 2, 2026-08-31 — see `30_METHODS/shared/wave2-challenge-round.md` and Decision 2026-08-31-27)

- [NEEDS_SOURCE] Taiwan STS 2026's specific "ezetimibe as first add-on for high/very-high risk,
  early combination for extremely-high risk" claim (`CLAUDE.md` §5 item 2 — a headline framing
  concept for this entire project) has never been content-verified against primary text (T-005
  remains `BLOCKED_FOR_SOURCE`). Currently traces only to `pitavastatin topic.md`'s own paraphrase.
  Highest-priority unresolved framing claim identified in the Challenge Round.
- [NEEDS_ANALYST, standing drafting caution for Wave 3] REPRIEVE (T-015) and REAL-CAD (T-016) are
  genuine pitavastatin **monotherapy** hard-outcome positive trials; the highest-likelihood overclaim
  risk in this project's evidence base is a future sentence that reads as if pitavastatin's
  monotherapy CV-outcome evidence extended to the pitavastatin/ezetimibe **FDC** specifically, which
  remains the unestablished Level 3 gap.
- [NEEDS_SOURCE, safety-relevant] **FDC-specific (pitavastatin+ezetimibe combined) CKD dosing** —
  no source in this project addresses the combination product's own CKD dosing; only pitavastatin
  monotherapy CKD dosing is resolved (T-018). Highest-stakes safety gap identified in the Challenge
  Round — any future clinical-facing output must not imply FDC-CKD-dosing equivalence to monotherapy
  without saying so explicitly as an extrapolation.
- [NEEDS_SOURCE — confirmed still blocked, Wave 3, Decision 2026-08-31-29] Singh 2024 (T-003) pools
  RCT and observational studies for its pitavastatin NODM risk ratios — the same methodological
  pattern that produced the Sydhom 2024 RCT-vs-observational framing issue the PI already had to
  resolve (Decision 2026-08-31-06). safety-pharmacology re-attempted lawful acquisition in Wave 3
  (Europe PMC PMCID lookup) — still `is_open_access:false`, no PMCID. **Genuinely unresolved due to
  source access, not a declined judgment call** — cannot determine whether Singh's pooled RR holds
  consistently across study types without full text. Carry into any future full-text acquisition
  attempt; do not treat as abandoned.
- [NEEDS_ANALYST] T-025's (Samnaliev 2025) newly-obtained full text shows its dose-specific R10/E10
  subgroup MACE signal (HR 0.58, 95% CI 0.35–0.96, p=0.030) is **not replicated** in the paper's own
  overall/pooled cohort analysis (no significant persistence/adherence-MACE association there). Do
  not cite the subgroup HR without this caveat.
- [NEEDS_SOURCE, best-available proxy now on record] FDC-specific CKD dosing and true isolated-BCRP-
  inhibitor fold-change both remain `BLOCKED_FOR_SOURCE`/unfound as direct empirical answers.
  T-026/T-027 (PBPK simulations) offer the closest available mechanistic proxies — explicitly not
  equivalent to real clinical DDI/dosing data, tagged `MECHANISTIC SUPPORT` only.
- [NEEDS_ANALYST] The FDC-adherence-improves-outcomes narrative (T-012/Katzmann, T-025/Samnaliev,
  T-022/Wei) rests entirely on retrospective/observational designs subject to healthy-adherer bias —
  no randomized FDC-vs-separate-pills comparison exists in this project's inventory. Any future
  synthesis presenting this as causal rather than associational should say so explicitly.
- [NEEDS_ANALYST] T-017 (Li H, Li J 2026, elderly NODM cohort, n=126, abstract-only) reports a
  striking effect size (0% vs. 10.29%) that should not be featured prominently before full-text
  verification, given the small sample and abstract-only sourcing.

### Still open after all three Wave 2 reports (+ follow-up rounds)

- [NEEDS_PI / BLOCKED_FOR_SOURCE — status confirmed by PI, 2026-08-31, do not assume resolvable]
  **Taiwan STS 2026 (T-005), Taiwan Lp(a) 2026 (T-006), base 2019 ESC/EAS (#34), 2026
  ACC/AHA guideline (#28), ESC 2025 Focused Update (T-007), and citation #33 (Chou MT 2022)'s own
  AE/CK/liver tables all confirmed `BLOCKED_FOR_SOURCE`** — via the **precise NCBI elink
  `linkname=pubmed_pmc` method** (empty linkset for all 7 checked PMIDs, a genuinely negative
  result, not an OA-flag inference; Decision 2026-08-31-13 reinforcement), independently
  corroborated for #33 by trials-efficacy's own retry (Decision 2026-08-31-25). This is a more
  rigorous negative than the original Cloudflare-block finding. **The PI has directed that this
  stay recorded as `NEEDS_PI`/`BLOCKED_FOR_SOURCE` explicitly — do not assume the PI will or can
  supply these directly, and no specialist should re-attempt acquisition without new instruction.**
  Partial
  mitigation for the ESC 2025 combination-wording task exists via T-021 (a secondary review that
  paraphrases it, with its own "old 2018 guideline" caveat) — but the primary documents' own exact
  wording remains unconfirmed. The Gate-2 LlamaParse requirement itself is already satisfied (both
  required demonstrations succeeded), so this is a content gap, not a Gate 2 blocker.
- [NEEDS_ANALYST] T-009's four adherence citations (Lin YW 2024, Su M 2025, van Driel ML 2016,
  Religioni U 2025) — full citations re-sent to safety-pharmacology (Decision 2026-08-31-26) after
  it flagged never receiving them in full; still not independently verified by anyone. Assigned to
  safety-pharmacology.
- [NEEDS_ANALYST] T-025 (Samnaliev M et al. 2025) — found by safety-pharmacology, citation identity
  confirmed but abstract-level only, not independently cross-checked further.
- [NEEDS_SOURCE, dispatched — Wave 3 now open, Decision 2026-08-31-28] T-024 (Abbas MS et al. 2026,
  possibly the first pitavastatin+ezetimibe-FDC-specific meta-analysis — highest priority) and
  T-023 (Lu YW et al. 2026, Taiwan real-world post-PCI cohort) — both found by trials-efficacy,
  citation identity confirmed, full text not yet obtained (`is_open_access:False` per Europe PMC for
  both). Dispatched to trials-efficacy as Wave 3's top priority (T-024 first, then T-023).
- [NEEDS_SOURCE — corrected 2026-08-31, was stale] Numeric-threshold/wording confirmation still
  pending only for the two guideline documents that remain `BLOCKED_FOR_SOURCE`: Taiwan Lp(a)
  2026/T-006 and base 2019 ESC/EAS/#34. **2023 TSC CCS (#30), ADA 2025 (#32), and the 2022 Taiwan
  primary-prevention companion (#35) were all subsequently obtained and content-verified** (Decision
  2026-08-31-23 for #30/#32; post-Gate-2 checkpoint for #35) — this bullet previously listed all
  five as still-pending, which was no longer accurate once those three were resolved. #29 (the
  2022 Taiwan secondary-prevention/high-risk companion) was citation-verified in Wave 1 but its
  full-text numeric thresholds were never separately pursued in Wave 2 — remains genuinely open.
- [NEEDS_SOURCE, dispatched to guideline-risk] **111 年健康促進統計年報** (Taiwan Health Promotion
  Administration statistical annual report, ROC 111 = 2022, T-008) — not indexed in PubMed/
  Crossref/paper-search; requires a direct fetch from the 國民健康署 website. Not part of the PI's
  named Wave 2 priorities but still open from Wave 1.
- [NEEDS_SOURCE] **FDC-specific (pitavastatin+ezetimibe combined) CKD dosing** — no source found so
  far addresses the combination product directly; only pitavastatin-monotherapy CKD dosing is
  resolved (T-018, Decision 2026-08-31-22).
- [NEEDS_SOURCE] Pitavastatin-specific BCRP-inhibitor fold-change number — T-019/T-020 corroborate
  an OATP1B1-predominant transporter mechanism generally but neither supplies a pitavastatin-specific
  quantitative BCRP figure. Gap remains open.
- [NEEDS_ANALYST] T-017 (Li H, Li J et al. 2026, elderly pitavastatin-vs-atorvastatin NODM cohort)
  is abstract-only, not open access — MODERATE confidence, not independently cross-checked beyond
  the abstract. Treat accordingly if cited.

### Other open items (not part of the PI's named Wave 2 dispatch, no urgency)

- [NEEDS_ANALYST] Two internal-consistency flags **within `Tonvasca_2026.md` itself** (informational
  only — the file is read-only, not this project's error to fix): a superscript/reference mismatch
  at line 2796, and citation #33 (Chou MT 2022) printed in two different citation-string formats at
  different points in the deck. Relevant only if/when the PI revises the original slide source.
- [RESOLVED, 2026-08-31 — see Resolved section below] safety-pharmacology's git-write blocker
  (originally listed here as `NEEDS_PI`) — resolved by the supervising Codex process. Moved to
  Resolved.
- [NEEDS_ANALYST] T-006's author list (Taiwan Lp(a) 2026 consensus/review), as reported by
  guideline-risk, contains a duplicated "Wang CY" entry. Preserved as-received per the Numeric
  Integrity Rule (not silently deduplicated) — flag if this citation is used verbatim in any
  downstream output.
- [NEEDS_SOURCE] `openevidence` MCP server remains unreachable across every session that has
  reported on it so far. Not part of the PI's Wave 2 authorization (which covers `research_hub`/
  `llamaparse` repair only) — treat as still down until a session reports otherwise.

## Resolved

### Wave 3/4 close-out, supervising-process consolidation (2026-08-31)

- [RESOLVED] **safety-pharmacology's git-write blocker** (Decision 2026-08-31-36) — the supervising
  Codex process independently QA-checked, committed, and pushed safety-pharmacology's six Wave 3
  files as commit `1d48927` on `worktree-safety-pharm-wave1`, resolving the blocker without needing
  a grant of Bash git-write permission to that session directly. See Decision 2026-08-31-37 (Decision
  2026-08-31-36's original rationale left unedited; this is an additive resolution note, not a
  rewrite).
- [RESOLVED] **Main consolidation lag** (the caveat restated in Decision 2026-08-31-35) — the
  supervising Codex process cherry-picked the three Wave 3 specialist commits and all Director Wave
  3/4 commits into local `main` (through Decision 2026-08-31-35), then subsequently completed final
  QA and pushed `main` to `origin` (Decision 2026-08-31-38) — local and `origin` `main` now both
  verified at commit `275ab90`, zero divergence. **Fully resolved, including the GitHub-sync portion
  previously left open.** PR #1 is now `CLOSED` (superseded) — closed by the repo owner after a
  26-path zero-object-mismatch verification against `origin/main` (Decision 2026-08-31-40); no open
  PI decision remains on this point.

### Wave 2 full-text acquisition results (2026-08-31)

- [RESOLVED — SUCCESS] Tsujita 2023 (T-004a) and Ako 2024 (T-004b) full text obtained and
  LlamaParse-parsed by trials-efficacy (PMC anti-bot-blocked, J-STAGE used instead — lawful).
  Exact arm structure, LDL-C, AE/CK/AST/ALT tables extracted. Two important nuances locked in:
  the "add ezetimibe or double the statin" comparison was not formally tested (Decision
  2026-08-31-16); Ako 2024's AE picture is broader than its abstract's "single ADR" framing
  suggests (Decision 2026-08-31-17). This also satisfies one of the two Gate-2 LlamaParse
  requirements (on the actual assigned target).
- [RESOLVED — SUCCESS] Gate-2 LlamaParse requirement for guideline-risk satisfied on a substitute
  source (T-014) after its three assigned targets were blocked — see below.
- [RESOLVED — CONFIRMED BLOCKED, no further automated action possible] Citation #33 (Chou MT 2022)
  AE/CK/liver-enzyme tables — confirmed `BLOCKED_FOR_SOURCE` by trials-efficacy in Wave 2 (no OA
  location via Unpaywall). Genuine institutional/manual access, or a Europe-PMC-PMCID-specific
  retry (see below), would be needed.
- [RESOLVED — SUCCESS, correcting an earlier BLOCKED status, AND the underlying numeric-integrity
  flag fully closed] T-012 (Katzmann 2022) — trials-efficacy first reported this
  `BLOCKED_FOR_SOURCE` via Unpaywall/publisher link; safety-pharmacology independently obtained it
  lawfully via a direct Europe PMC PMCID lookup (PMC8873069, CC BY 4.0) and LlamaParse-parsed it
  (Decision 2026-08-31-20 — the resulting methodological lesson relayed to the other two
  specialists). **From that full text, safety-pharmacology then resolved the Decision
  2026-08-31-11 cohort-size question, confirmed by the Director's own direct read of
  `Tonvasca_2026.md`: both printed n pairs are correct, describing different subsets (n=6,429/533
  = a GP-2018 prescription-count snapshot; n=1,639/796 = the pooled paired-measurement subgroup
  the LDL-C results are actually drawn from). Final decision: `NO_CHANGE`, not `SOURCE_CONFLICT` —
  cite n=1,639/796 alongside the LDL-C/attainment figures.** See Decision 2026-08-31-11's final
  update for full detail.
- [RESOLVED — SUCCESS] T-016 (REAL-CAD trial) fully verified by trials-efficacy — Taguchi I et al.,
  Circulation 2018;137(19):1997-2009, N=13,054, HR 0.81 (95% CI 0.69–0.95). Q8 closed.
- [RESOLVED — SUCCESS] T-015 (REPRIEVE) fully verified by trials-efficacy — see Decision
  2026-08-31-18.
- [RESOLVED] T-013 (Corsini A 2011) bibliographically verified by safety-pharmacology via Crossref.
- [RESOLVED] Clarithromycin DDI gap — upgraded from "not found as fetched" to
  `CONFIRMED_ABSENT_FROM_LABEL` after safety-pharmacology checked the full DailyMed label text
  directly (Decision 2026-08-31-21).
- [RESOLVED — new sources found] T-017 (Li H, Li J et al. 2026, elderly NODM cohort, abstract-only)
  and T-018 (Tramontano D et al. 2025, CKD-dosing review, cross-verified against the FDA label —
  resolves most of the Wave 1 CKD gap) — see Decision 2026-08-31-22. FDC-specific CKD dosing
  remains an open gap (see Open items above).
- [RESOLVED, partial] BCRP mechanism — T-019/T-020 corroborate an OATP1B1-predominant mechanism;
  the pitavastatin-specific quantitative fold-change number remains an open gap (see Open items
  above).
- [RESOLVED — SUCCESS] Item 6 (numeric-threshold confirmation), final: **3/5 complete**: 2023 TSC CCS
  (#30) and ADA 2025 (#32) full text obtained and content-verified by guideline-risk, including a
  genuine threshold difference caught (TSC's <50 mg/dL extreme-risk vs. ACC/AHA's <55 mg/dL
  very-high-risk — do not conflate). T-021 (Katzmann & Laufs 2026 review) obtained as a partial
  substitute for the still-blocked ESC 2025 primary document. See Decision 2026-08-31-23. **#35
  (Huang PH et al. 2022 Taiwan primary-prevention guideline) subsequently completed** — obtained
  lawfully via the Taiwan Society's own tas.org.tw mirror (no PMC deposit; same pattern that worked
  for #30/#32), CC BY 4.0 confirmed verbatim in the parsed text, four risk-stratified
  primary-prevention LDL-C targets extracted (<100/<115/<130/<160 mg/dL) with COR/LOE grading —
  already reflected in `02_SOURCE-INVENTORY.md` row #35. Verified at a post-Gate-2 checkpoint,
  2026-08-31 — see `90_CROSS-SESSION-LOG/2026-08-31_post-gate2-checkpoint-row35.md` and Decision
  2026-08-31-28. **2/5 remain blocked** (T-006 Taiwan Lp(a) 2026, #34 the 2019 ESC/EAS base guideline
  — neither has a PMC copy, no equivalent mirror exists for #34). No target left unattempted.
- [RESOLVED — CONFIRMED BLOCKED] Taiwan STS 2026 (T-005), 2026 ACC/AHA (#28), ESC 2025 Focused
  Update (T-007) — all confirmed `BLOCKED_FOR_SOURCE` by guideline-risk (Cloudflare bot-challenge,
  corroborated via Europe PMC metadata). See the still-open PI question above about direct PDF
  supply — that question covers these three plus, by extension, Chou 2022/Katzmann 2022 above.

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
