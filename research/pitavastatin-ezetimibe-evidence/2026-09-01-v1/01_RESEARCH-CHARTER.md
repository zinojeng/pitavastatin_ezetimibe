# 01_RESEARCH-CHARTER — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence`
RUN_ID: `2026-09-01-v1`

## Relationship to `2026-08-31-v1`

This run does not restate what the prior run already established; it extends it additively. Where
this charter is silent, `2026-08-31-v1/01_RESEARCH-CHARTER.md` and `CLAUDE.md` §2/§5 remain the
baseline (evidence hierarchy, role definitions, Level 1/2/3 hard-outcome framework). This run adds:
(a) new 2025–2026 guideline wording verification (incl. a candidate primary 2026 ACC/AHA text — see
`00_RUN-MANIFEST.md`), (b) presentation/manuscript-ready output (newly PI-authorized), (c) a
structured attack/defense section, (d) explicit claim-safety taxonomy discipline across superiority /
noninferiority / surrogate / observational / subgroup / guideline / expert-inference framings.

## Primary question

Building on the prior run's evidence base: what does the **current, most recent** (2026) ACC/AHA and
other guideline landscape say, in exact wording, about goal-directed LDL-C treatment, early
combination therapy, ezetimibe add-on, and statin intolerance/STS positioning — and how does the
direct pitavastatin+ezetimibe evidence base (Phase III/FDC trial, dose-comparison data,
HIJ-PROPER) versus transferable strategy evidence (RACING and other statin+ezetimibe trials) support
a defensible, claim-safe clinical positioning of pitavastatin/ezetimibe FDC versus (a) pitavastatin
monotherapy, (b) higher-dose/high-intensity statin monotherapy, and (c) other nonstatin add-ons
(bempedoic acid, PCSK9-targeting therapy, inclisiran) — including the strongest good-faith
counterarguments to that positioning?

## Scope — six PI-specified focus areas (each mapped to an owning specialist; see §5-equivalent below)

1. **Exact 2026 guideline wording** *(guideline-risk, primary)* — goal-directed LDL-C treatment,
   early combination therapy, ezetimibe add-on, statin intolerance/STS, high/very-high-risk target
   attainment. Must be exact quotes with COR/LOE and a traceable locator (page/section/line in a
   verified source), not paraphrase.
2. **Direct pitavastatin+ezetimibe evidence** *(trials-efficacy, primary)* — Phase III/FDC trial(s),
   2 mg vs 4 mg, 2/10 vs 4/10, add-ezetimibe-vs-dose-escalation, LDL-C target attainment, safety,
   adherence, real-world evidence (RWE) if any is found.
3. **Direct hard-outcome vs. transferable strategy evidence** *(trials-efficacy, primary; guideline-
   risk cross-checks guideline citations of either)* — HIJ-PROPER (direct, pitavastatin-specific,
   overall primary endpoint non-superior) vs. RACING and other statin+ezetimibe outcome trials
   (indirect, strategy-level, different statin) — **no statin-specific conflation**, carried forward
   from the prior run's central discipline (`CLAUDE.md` §7).
4. **Defensible clinical positioning** *(safety-pharmacology, primary; trials-efficacy for efficacy
   deltas)* — vs. pitavastatin monotherapy, higher-dose/high-intensity statin monotherapy, other
   nonstatin add-ons. Glycemic profile, low CYP3A4-dependent interaction liability, polypharmacy,
   elderly/Asian/Taiwan populations, CKD, tolerability, FDC adherence — **without marketing
   overclaims** (carried forward calibrated-language rules from `CLAUDE.md` §2.4).
5. **Attack/defense section** *(Director-coordinated Challenge Round, all three specialists
   contribute within domain)* — product-specific MACE limitation; indirect-evidence conflation risk;
   "maximize statin first" counter-position; diabetes/DDI claim limits; cost/adherence; when
   PCSK9-targeting therapy, bempedoic acid, or inclisiran is the more defensible choice instead.
6. **Claim-safe distinction taxonomy** *(Director, applied project-wide at Wave 3 synthesis and Gate
   3)* — every claim in `40_SYNTHESIS/`/`50_MANUSCRIPT/` must be legible as one of: superiority,
   noninferiority, LDL-C surrogate efficacy, observational signal, subgroup/hypothesis-generating
   finding, guideline/consensus, or expert inference. This is additive to, not a replacement for, the
   `CLAUDE.md` §7 Evidence Hierarchy tags — every claim carries both.

## New intake handling

`inbox/2026-acc-aha-drive/` (35 files) is unverified secondary material — see `00_RUN-MANIFEST.md`
for full inventory and the `official/` subfolder finding. guideline-risk-intelligence owns intake
deduplication/verification as its first Wave 1 task (dedupe by latest-timestamp-per-slot per
`MANIFEST.md`, verify the `official/` candidate primary source, reconcile the
`markdown/1-s2.0-S0735109725102544.md` reference in `adjudication_log_v2.md`). No claim from the
intake enters `20_EVIDENCE/` tagged higher than `EXPERT INTERPRETATION`/`INSUFFICIENT EVIDENCE` until
independently checked against a primary source per-claim.

## Final outputs (this run, additive to the prior run's)

- Updated/new `20_EVIDENCE/`, `10_DATA/` entries per specialist domain, each claim Evidence-Hierarchy
  tagged AND claim-safe-taxonomy tagged (focus area 6).
- `40_SYNTHESIS/`: integrated update reflecting any newly verified 2026 guideline wording and the
  attack/defense section.
- **Integrated zh-TW evidence brief** (Traditional Chinese, English drug/technical names retained) —
  new deliverable this run.
- **Slide-ready "Pitavastatin + Ezetimibe clinical positioning and defense" document** in
  `50_MANUSCRIPT/` — new deliverable this run, PI-authorized, gated behind Wave 3.
- `04_OPEN-QUESTIONS.md`: limitations/open gaps, explicit not silently filled.
- `99_FINAL-QA.md`: independent audit report and Final Gate recommendation (Wave 4, new sonnet
  auditor spawned for this run).

## Source of truth

- `2026-08-31-v1/` outputs (verified/audited findings from the completed prior run) — treated as
  established baseline, re-opened only if this run's new sources genuinely contradict them (via the
  Decision Taxonomy, `CLAUDE.md` §8), never silently overwritten.
- `CLAUDE.md`, `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md` — unchanged governance baseline.
- `inbox/2026-acc-aha-drive/` — unverified secondary material, see above.
- This run's own `10_DATA/`, `20_EVIDENCE/`, `30_METHODS/`, `40_SYNTHESIS/`, `50_MANUSCRIPT/` once
  populated.

## Files that must not be modified

- All `2026-08-31-v1/` outputs (superseded RUN_ID — additive versioning only, Golden Rule 9).
- Repo-root legacy inputs (`pitavastatin topic.md`, the Runbook source `.md`, `Tonvasca_2026.md`).
- `inbox/2026-acc-aha-drive/` itself — read-only intake; specialists extract *into* their own owned
  paths, never edit the intake files in place.

## Major uncertainty going in (Wave 0 assessment)

- Whether `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_..._Circulation.{pdf,md}` is a genuine,
  verifiable primary source (high plausibility from Wave 0 spot-check, not yet independently
  confirmed via Crossref/PubMed/doi.org) — see `00_RUN-MANIFEST.md` and `04_OPEN-QUESTIONS.md`.
- Whether DOI `10.1161/CIR.0000000000001423` (Circulation, this new file) and DOI
  `10.1016/j.jacc.2025.11.016` (JACC, prior run's still-`BLOCKED_FOR_SOURCE` citation #28) are two
  genuine co-publication DOIs for the same joint guideline, or one is a bad/fabricated citation
  carried from `Tonvasca_2026.md`/legacy intake material.
- Whether the intake's own line-number-cited "raw guideline source"
  (`markdown/1-s2.0-S0735109725102544.md`) is itself obtainable/real or an artifact of an
  unverifiable upstream process — not assumed either way.
- MCP connectivity for `paper-search`/`tavily`/`openevidence` (down at Wave 0 recon) may constrain
  independent DOI verification and new-literature search until re-checked/repaired.

## Role division

Research Director; guideline-risk-intelligence (focus areas 1, intake verification, guideline
portions of 5); trials-efficacy-intelligence (focus areas 2–3, trial portions of 5); safety-
pharmacology-intelligence (focus area 4, safety/DDI/positioning portions of 5); independent-auditor
(Wave 4). See `CLAUDE.md` §2–§3 for full role/ownership detail, unchanged this run.

## Stop conditions

Unchanged from `CLAUDE.md` §4/`01_RESEARCH-CHARTER.md` (prior run): unreachable required peer →
BLOCKED, reported, never silently substituted; source not lawfully obtainable → `BLOCKED_FOR_SOURCE`,
never routed around; unresolved numeric/factual conflict → `NEEDS_PI`, logged, never guessed.

## Success conditions

- Every claim entering `20_EVIDENCE/`/`40_SYNTHESIS/`/`50_MANUSCRIPT/` carries an Evidence Hierarchy
  tag (`CLAUDE.md` §7) **and** a claim-safe distinction tag (focus area 6 above) **and** a traceable
  citation (PMID/DOI/URL where applicable).
- Every number in `10_DATA/` is byte-for-byte traceable to a specific verified source (Numeric
  Integrity Rule, `CLAUDE.md` §9), including numbers sourced from the new `official/` candidate text
  — which must itself be verification-gated before any number from it is treated as final.
- The `official/` candidate source's authenticity is either confirmed (with a recorded verification
  method) or explicitly left `NEEDS_PI`/`BLOCKED_FOR_SOURCE` — never silently assumed genuine because
  it "looks real."
- No claim conflates RACING/other-statin strategy evidence with pitavastatin/ezetimibe-specific
  hard-outcome evidence (carried-forward top overclaim risk from the prior run).
- Independent audit (Wave 4) reaches PASS or PASS_WITH_MINOR_ISSUES before anything is marked FINAL.
