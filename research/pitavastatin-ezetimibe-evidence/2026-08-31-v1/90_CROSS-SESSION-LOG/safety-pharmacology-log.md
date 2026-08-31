# 90_CROSS-SESSION-LOG — safety-pharmacology-intelligence

Append-only control-plane message log for this role, per CLAUDE.md §6. Full research content lives
in this role's owned `10_DATA/`/`20_EVIDENCE/`/`30_METHODS/` paths, not here.

---

## 2026-08-31 — Wave 1 health check + task assignment confirmation

[TYPE] CROSS_SESSION_TEST → pit-eze-research-director. Reported orientation complete (CLAUDE.md,
runbook, pitavastatin topic.md, run governance files 00/01/02/04/05, 03_DECISION-LOG.md), ListAgents
confirmed reachable peers (Director idle, guideline-risk busy, trials-efficacy busy).
[STATUS] READY_FOR_NEXT_WAVE.

Director replied [TYPE] TASK_ASSIGNMENT confirming Gate/Wave (READY_FOR_NEXT_WAVE, Wave 1) and
asking for exact scope reconciliation against CLAUDE.md §2.4/§5 and `02_SOURCE-INVENTORY.md` rows
#3–16, #23, #26(joint).

Replied [TYPE] STATUS_REPORT confirming scope: (1) LEGACY_VERIFICATION of the above rows; (2) in
parallel, NEW_SOURCE_DISCOVERY for Search Protocol items 3 (glycemic/NODM), 4 (DDI), 5 (2mg vs 4mg
dose comparison, joint with trials-efficacy) — flagged explicitly as Wave-2-shaped work run now
because none of it builds interpretation on top of an unverified legacy claim; (3) muscle AE/CK/
liver/CKD/elderly/adherence and STS-vs-formal-intolerance; explicitly deprioritized Lp(a)/ApoB/
remnant pharmacology (item 10) per its own ≤10–15% weighting. Also reported: `research_hub` and
`llamaparse` reachable in this session (unlike Wave 0 ENOENT failures logged in
`00_RUN-MANIFEST.md`); `openevidence` still down.

Director replied approving the Wave-1/Wave-2 boundary reasoning, with the condition that every note/
table tag its producing activity (`LEGACY_VERIFICATION` vs `NEW_SOURCE_DISCOVERY`) for auditor
legibility — **done**, applied throughout `evidence-map.md`, `extraction-table.csv`,
`ddi-matrix.md`. Confirmed Lp(a)/ApoB deprioritization is correct, no need to pull forward.

Director also disclosed: this Director session is currently isolated in its own git worktree whose
commits are not reaching the shared `main` checkout (an earlier push attempt was blocked by this
environment's permission classifier) — flagged as stale/pending, "no action needed" from this role.
**This safety-pharmacology session subsequently hit the identical structural issue** (see
"Worktree isolation" entry below) — recorded here as it may be a project-wide environment condition
affecting every persistent role in this run, not isolated to the Director.

## 2026-08-31 — Wave 1 execution (3 internal subagents)

Ran three internal, temporary subagents (workflow-internal labor, not persistent peers) in parallel:
`safety-citation-verify` (LEGACY_VERIFICATION: 16/16 of the assigned Tonvasca_2026.md citations
VERIFIED_MATCH; completed the Wave-0-deferred read of lines 1795–2811 per Decision 2026-08-31-02),
`safety-glycemic-search` (NEW_SOURCE_DISCOVERY: identified Singh H et al. 2024, PMID 39587804, as
the "2024 systematic review" referenced generically in `pitavastatin topic.md`, distinct from
Sydhom P et al. 2024; 14-row comparative evidence table incl. Taiwan's PAPAGO-T RCT), and
`safety-ddi-dose-search` (NEW_SOURCE_DISCOVERY: FDA/DailyMed Livalo label DDI numbers, K-924 Japan
dose-comparison trial safety data, Taiwan STS 2026 consensus located via Crossref — corrects
`02_SOURCE-INVENTORY.md` T-005's "not yet located" status).

Full findings written to this role's owned paths — see [OUTPUT_PATHS] in the completion report sent
to Director immediately following this log entry.

### Findings requiring routing to other roles (not actioned by this role — file-ownership boundary)

- **To guideline-risk-intelligence**: citation #23 (Chien SC et al., J Formos Med Assoc.
  2019;118(10):1385-1392, PMID 30584005) is mislabeled in `02_SOURCE-INVENTORY.md` as "Statin
  discontinuation outcomes" — its actual subject is the 2019 Taiwan Society of Lipids and
  Atherosclerosis statin-intolerance consensus, the direct precursor to the 2026 Taiwan STS
  consensus this project needs (Search Protocol item 2). Also flagging: Mach F et al. (2019 ESC/EAS
  dyslipidaemia guideline), Huang PH et al. and Chen PS et al. (Taiwan guideline updates), ADA 2025,
  and Masana L et al. (combination-therapy mechanism/residual-risk framing) were found in the
  previously-unread tail of `Tonvasca_2026.md` (lines 1795–2811) and belong to guideline-risk's
  domain per the existing Source Inventory assignment pattern.
- **To trials-efficacy-intelligence**: Katzmann JL et al. (Clin Res Cardiol. 2022;111(3):243-252 —
  FDC adherence/efficacy, recurring citation also at lines 2296–2345 outside this role's read range)
  and Corsini A et al. (Curr Med Res Opin. 2011;27(8):1551-1562 — DDI/CYP3A4, recurring at lines
  2066/2236) were both found in the unread tail; Corsini overlaps this role's DDI domain too and has
  been logged in `unresolved-questions.md` item 5-equivalent for a future verification pass by
  whichever role picks it up first. Also: two internal-consistency flags in `Tonvasca_2026.md`
  itself (superscript "13"/ref-12 mismatch at line 2796; Chou MT 2022 cited in two formats) — both
  outside this role's write scope, reported to Director for `03_DECISION-LOG.md`.
- **To Director** (for `02_SOURCE-INVENTORY.md` updates this role cannot make directly): (1) topic
  correction for #23 above; (2) T-005 (Taiwan STS 2026 consensus) status should change from "not yet
  located" to found — Wu YJ et al., J Formos Med Assoc, April 2026, DOI 10.1016/j.jfma.2026.04.111
  (Crossref-confirmed bibliographic record; full text still paywalled, content below FULL-TEXT
  confidence).

### Safety notice received and complied with

Director relayed (2026-08-31): `mcp__research_hub__download_paper`'s internal search includes
Sci-Hub with no opt-out (discovered by guideline-risk-intelligence). This role never called that
tool during Wave 1 — see `fulltext-manifest.md` for full detail — and will not call it going
forward; `research_hub`'s metadata-only tools remain in use.

## 2026-08-31 — Wave 2 (PI-authorized, Decision 2026-08-31-12)

Director dispatched Wave 2 tasks: lawful full text for T-003 (Singh 2024) and T-012 (Katzmann 2022),
optional LlamaParse demonstration, direct re-verification of the DDI matrix (T-010) against the
primary DailyMed source, and continued queue items (T-013 Corsini, CKD/elderly/BCRP gaps). Complied
with the standing `mcp__research_hub__download_paper` prohibition throughout (never called it).

Results: Katzmann 2022 full text obtained lawfully (PMC8873069, CC BY 4.0) and parsed via
LlamaParse; Singh 2024 confirmed BLOCKED_FOR_SOURCE (Europe PMC: not open access, no PMCID) — full
structured abstract already sufficient for current needs. T-013 (Corsini A 2011) bibliographically
VERIFIED_MATCH via Crossref. DDI matrix independently re-verified directly against DailyMed (not
secondary transcription) — all previously-reported cyclosporine/erythromycin/rifampin/gemfibrozil
figures confirmed exact; clarithromycin's absence from the label upgraded from "not found this pass"
to CONFIRMED_ABSENT_FROM_LABEL; fenofibrate's exact section locator corrected (12.3 Table 3, not
Section 7); new fibrates-class/niacin/colchicine caution language captured.

Two unplanned but directly relevant finds surfaced during Wave 2 discovery: (1) Li H, Li J 2026 (Br
J Hosp Med, PMID 42528438) — elderly-specific pitavastatin vs atorvastatin glycemic/NODM comparison,
partially filling the Wave-1-flagged elderly-subgroup gap (BLOCKED_FOR_SOURCE for full text,
abstract obtained); (2) Tramontano D et al. 2025 (Drugs, PMID 40106181, PMC12098426, CC BY-NC 4.0)
— downloaded, LlamaParse-parsed, and its CKD dosing table cross-verified against the FDA label
directly, resolving most of the Wave-1-flagged pitavastatin-CKD dosing gap (1mg starting/2mg max in
eGFR 15-59 or hemodialysis; no adjustment for mild impairment). The FDC-specific (pitavastatin+
ezetimibe combined) CKD dosing sub-question remains open — no source found addresses that
combination specifically.

BCRP gap partially converged: two open-access mechanistic/pharmacovigilance sources found (Schmith
2026, PMC12868915; Stäuble 2026, PMC12929307) supporting the OATP1B1-predominant mechanism framing,
but no specific BCRP-inhibitor fold-change number for pitavastatin was located — gap remains open.

Full details, exact quotes, and file-level provenance (SHA-256, retrieval timestamps, license) in
this role's owned `20_EVIDENCE/safety-pharmacology/` and `30_METHODS/safety-pharmacology/` files.

## 2026-08-31 — Wave 3 (PI-authorized Synthesis wave, Director dispatch)

Director confirmed session model (Sonnet 5, per system identity — meets the stated PI requirement)
and dispatched 5 tasks. Results: (1) Singh 2024 RCT-vs-observational disaggregation — re-attempted
via Europe PMC PMCID lookup per Director's suggestion; still is_open_access:false, no PMCID;
BLOCKED_FOR_SOURCE unchanged, question cannot be answered without full text, reported as such rather
than guessed. (2) T-025 (Samnaliev 2025) deepened — discovered it's actually open access (PMID
40454236, PMCID PMC12123881, CC BY) via a fresh Europe PMC lookup; downloaded and LlamaParse-parsed
lawfully; extracted the R10/E10 dose-subgroup's full persistence/adherence/LDL-C/MACE data,
including a subgroup MACE HR 0.58 (95% CI 0.35-0.96) not visible at abstract level — flagged as an
overall-cohort-vs-subgroup inconsistency worth noting if cited. (3a) FDC-specific CKD dosing —
targeted search found nothing; recorded as BLOCKED_FOR_SOURCE with an explicitly-labeled EXPERT
INTERPRETATION (not a finding) about why this likely doesn't exist. (3b) BCRP quantitative number —
found the closest thing to date: Hong E et al. 2025 (PMC11945117, PBPK-modeled, not clinical) gives
a pitavastatin AUC ratio of 2.24 with a multi-mechanism CFTR-modulator combination — clearly flagged
as simulation-based, not equivalent to the label's measured DDI numbers. Also found Wu Y et al. 2025
(PMC12389332) — PBPK model showing ~75% reduction in hepatic OATP1B1/3 abundance in ESRD, providing
mechanistic rationale for the label's CKD dose cap (not a new empirical number). (5) OpenEvidence —
confirmed still CONNECTION_CLOSED in this session; the authorized one-pass discovery could not be
executed because the tool itself is unavailable, not by choice.

Full detail, exact quotes, and provenance in this role's owned files (updated in place).

### Worktree isolation note

This background session's file writes to the shared checkout were rejected by the harness pending
`EnterWorktree`. All Wave 1 outputs from this role are written to
`.claude/worktrees/safety-pharm-wave1/` (branch `worktree-safety-pharm-wave1`) and have **not been
committed or merged to `main`**, per this role's task instruction not to run git commit/push. This
mirrors the Director's own reported sync gap and appears to be an environment-level condition
affecting this run generally — flagged for the PI/Director to resolve (e.g., merging each role's
worktree branch, or adjusting the session's worktree-isolation setting), not something this role can
fix unilaterally.
