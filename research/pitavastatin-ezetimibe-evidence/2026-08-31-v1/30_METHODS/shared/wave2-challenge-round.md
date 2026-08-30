# Wave 2 Challenge Round — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Conducted: 2026-08-31, at Gate 2 (per PI directive)

Per Runbook §30: a challenge round run *before* integration, asking "why might this conclusion be
wrong?" across four angles, applied here to all evidence accumulated through Wave 2. This is a
self-adversarial review by the Director over the accumulated `02_SOURCE-INVENTORY.md` and
`03_DECISION-LOG.md` record — not the independent Wave 4 audit (which remains a separate,
not-yet-started role per `CLAUDE.md` §2.5). Findings here are risks and cautions to carry into any
future Wave 3 synthesis, not corrections to already-logged decisions (those stand as recorded).

## 1. Guideline angle — which statements go beyond the actual guideline wording?

- **Four guideline documents carry overlapping-looking but contextually distinct LDL-C thresholds**:
  ACC/AHA 2026 (<55 very-high-risk secondary prevention, #28), TSC CCS 2023 (<50 extreme-risk, <70
  general CCS, #30), Taiwan 2022 primary-prevention companion (<100/<115/<130/<160 by risk
  stratum, #35), ADA 2025 (<55 secondary-prevention-with-diabetes, #32). **Risk**: any future
  synthesis sentence that says "the guidelines recommend <X mg/dL" without naming which guideline
  and which risk population would blur four genuinely different numbers into one. No fix needed now
  — flagged as a standing drafting discipline for Wave 3.
- **Taiwan STS 2026's specific "ezetimibe as first add-on" claim (`CLAUDE.md` §5 item 2, a headline
  framing concept for this entire project) has never been content-verified against primary text** —
  only citation-verified (the document exists, is correctly cited) and paraphrase-verified via a
  secondary review (T-021, for ESC 2025, not STS). T-005 (Taiwan STS 2026) itself remains
  `BLOCKED_FOR_SOURCE`. **This is the single largest unverified-but-load-bearing claim in the
  project's own framing** — `pitavastatin topic.md`'s own paraphrase is the only source for it.
  Flagged `NEEDS_SOURCE`, carried to `04_OPEN-QUESTIONS.md`.
- T-021 (Katzmann & Laufs 2026) is a **secondary review paraphrasing** ESC 2025, not the primary
  document — already tagged `INDIRECT EVIDENCE` in `02_SOURCE-INVENTORY.md`; re-flagged here as a
  risk that a future draft could accidentally cite "ESC 2025 states..." when the accurate framing is
  "a 2026 review describing ESC 2025's position states...".

## 2. Trials angle — which conclusions are being extrapolated beyond the actual trial population?

- **Highest-risk conflation identified**: REPRIEVE (T-015, pitavastatin monotherapy, HIV population,
  vs. placebo) and REAL-CAD (T-016, pitavastatin dose-comparison, Japanese CAD, hard outcomes) are
  both genuine positive pitavastatin hard-outcome RCTs. **Risk**: a synthesis sentence like
  "pitavastatin has proven cardiovascular outcome benefit" is true of pitavastatin monotherapy but
  could be read — or written — as if it extended to the pitavastatin/ezetimibe FDC specifically,
  which is precisely the Level 3 gap `pitavastatin topic.md` §6 identifies as *not* established
  (HIJ-PROPER's primary endpoint was not statistically superior). Both trials are already tagged
  "kept outside the Level 1/2/3 framework" in `02_SOURCE-INVENTORY.md`, but this is worth restating
  explicitly as the project's single most likely overclaim risk for Wave 3.
- RACING (T-002) remains rosuvastatin, not pitavastatin — already extensively flagged, no new risk
  identified.
- Tsujita 2023's (T-004a) K-924-HD-vs-LD comparison (statistically significant) must not be
  generalized to the "add ezetimibe or double the statin?" question, since that specific comparison
  was *not* formally tested — already locked in via Decision 2026-08-31-16; re-confirmed here as
  correctly guarded.
- K-924 (Japan, T-004a/T-004b) safety data used as an indirect substitute for citation #33's
  (Taiwan/Australia/NZ) own blocked safety tables — already tagged `INDIRECT EVIDENCE` with a
  population/product caveat; re-confirmed as correctly guarded.

## 3. Safety angle — which recommendation could create patient risk?

- **FDC-specific CKD dosing remains an open gap.** T-018 resolves pitavastatin *monotherapy* CKD
  dosing (1mg start/2mg max, eGFR 15–59 or HD) but **no source found in this project addresses the
  pitavastatin+ezetimibe FDC's own CKD dosing.** This is the highest-stakes safety gap identified in
  this challenge round: if any future clinical-facing output (talk, manuscript) implies the FDC's
  CKD dosing mirrors the monotherapy dosing without saying so explicitly as an extrapolation, that
  would be a real patient-safety-relevant overclaim. Flagged `NEEDS_SOURCE` (already in
  `04_OPEN-QUESTIONS.md`), elevated here to explicit safety-risk status.
- Clarithromycin: `CONFIRMED_ABSENT_FROM_LABEL` (T-010) must not be miscited as "confirmed no
  interaction" — the label simply doesn't address it. Already correctly worded in
  `02_SOURCE-INVENTORY.md`; re-flagged as a phrasing risk for whoever drafts synthesis text.
- T-017 (Li H, Li J 2026, elderly pitavastatin-vs-atorvastatin NODM, n=126, abstract-only, 0% vs.
  10.29%) — a **striking effect size (0%) from a small, abstract-only, not-full-text-verified
  source**. Risk: this could get over-weighted as a headline "pitavastatin is NODM-safe in the
  elderly" claim before full-text verification. Flagged `NEEDS_ANALYST`: full-text confirmation
  should precede any prominent use of this figure.
- BCRP: mechanism corroborated (T-019/T-020) but no pitavastatin-specific fold-change number exists
  in this project's evidence base. Risk: the general "OATP1B1-predominant" framing could be
  overextended to imply BCRP-mediated interactions are ruled out, when the specific number is simply
  missing, not negative.

## 4. Methods angle — association vs. causation; indirect treated as direct

- **Singh 2024 (T-003) pools RCT and observational studies** for its pitavastatin-vs-atorvastatin/
  rosuvastatin NODM risk ratios (RR 0.86/0.77) — the same methodological pattern that produced the
  Sydhom 2024 (#26) RCT-vs-observational framing issue the PI already had to resolve (Decision
  2026-08-31-06). **This has not yet received the same disaggregation scrutiny.** It is not yet
  known whether Singh 2024's pooled RR holds consistently across RCT-only vs. observational-only
  subsets, the way Sydhom's did not. Flagged `NEEDS_ANALYST`/potentially `NEEDS_PI` if a
  RCT-vs-observational breakdown is later found to diverge, parallel to Decision 2026-08-31-06 — not
  yet a confirmed problem, but a directly parallel risk that should not be assumed safe by default.
- **The FDC-adherence-improves-outcomes narrative (Katzmann 2022/T-012, Samnaliev 2025/T-025, Wei
  2023/T-022) is built entirely on retrospective/observational designs**, not on any randomized
  comparison of FDC vs. separate pills. All three are correctly tagged `INDIRECT EVIDENCE` for the
  pitavastatin-specific question (Katzmann/Samnaliev are on other drugs or general-disease scope),
  but there is a second, independent methods risk beyond the population mismatch: **the causal
  chain "FDC → better adherence → better outcomes" is subject to healthy-adherer bias** (patients
  who take medication as prescribed differ systematically, in ways beyond the medication itself,
  from those who don't) in all three observational sources. None of the adherence-outcome
  literature in this project's inventory is a randomized comparison. Any future synthesis presenting
  this as a causal claim rather than an association should say so explicitly.
- HIJ-PROPER's absorber-phenotype subgroup (HR 0.71) remains correctly tagged hypothesis-generating/
  `INSUFFICIENT EVIDENCE` for a superiority claim — re-confirmed as correctly guarded, no new risk.

## Summary — priority findings carried forward

1. Taiwan STS 2026's "ezetimibe as first add-on" claim is unverified against primary text (Guideline
   angle) — highest-priority unresolved *framing* claim.
2. REPRIEVE/REAL-CAD-to-FDC conflation is the highest-likelihood *overclaim* risk for Wave 3
   drafting (Trials angle).
3. FDC-specific CKD dosing gap is the highest-stakes *safety* gap (Safety angle).
4. Singh 2024's RCT-vs-observational pooling is an unresolved *parallel risk* to the already-PI-
   decided Sydhom framing (Methods angle).

None of these block Gate 2 — per the PI's existing authorization, Gate 2 is evaluated on whether the
two required LlamaParse demonstrations succeeded (they did), not on whether every content gap is
closed. All four are carried into `04_OPEN-QUESTIONS.md` for whenever Wave 3 synthesis begins.
