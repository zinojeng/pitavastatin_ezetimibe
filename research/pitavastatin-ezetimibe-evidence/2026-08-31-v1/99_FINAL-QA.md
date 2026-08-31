# 99_FINAL-QA — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

**Owner: independent-auditor.** Wave 4 audit, first pass conducted 2026-08-31, read-only against the
full repository, against `40_SYNTHESIS/00`–`08` as primary artifact, cross-checked against
`02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md`, `04_OPEN-QUESTIONS.md`,
`30_METHODS/shared/wave2-challenge-round.md` and `wave3-challenge-round-and-gate3.md`, `CLAUDE.md`,
and `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md` §35–36. `50_MANUSCRIPT/` confirmed out of scope
(contains only `.gitkeep`).

**Re-audit, 2026-08-31 (same day, second pass):** the Director corrected Finding 1 (commit
`06d5c38`, Decision 2026-08-31-33) and requested re-audit of `02_SOURCE-INVENTORY.md`'s #28 row,
`40_SYNTHESIS/01` (C19), `02`, `06`, and `08`. This pass verifies that correction independently —
including reading the underlying legacy sources (`Tonvasca_2026.md`, `pitavastatin topic.md`)
directly, not merely trusting the Director's cited line numbers — and updates the checklist/finding/
gate below accordingly. See "Re-audit findings" and the revised Final Gate recommendation at the
bottom of this file.

## Final QA Checklist

### Numbers

- [x] Every N, denominator, percentage in `40_SYNTHESIS/03`–`06` traceable via `08_traceability-table.md`
      to a `02_SOURCE-INVENTORY.md` row — spot-checked all ~30 rows of `08` against the exact line
      numbers they cite in `02`; every citation and every figure (LDL-C %, HR/RR/OR with CI, p-values,
      N, dosing figures) matches character-for-character. No drift found.
- [x] Effect sizes (OR/HR/RR) with CI traceable to source — HIJ-PROPER (HR 0.89, 95% CI 0.76–1.04,
      P=0.152; subgroup HR 0.71), RACING (9.1% vs 9.9%), REPRIEVE (HR 0.65, 95% CI 0.48–0.90,
      P=0.002, N=7,769), REAL-CAD (HR 0.81, 95% CI 0.69–0.95, P=0.01, N=13,054), Sydhom pooled HRs
      (0.76/0.80/0.84/0.81), Singh RRs (0.86/0.77), Samnaliev (persistence HR 0.54, adherence OR
      3.00; R10/E10 subgroup HR 0.58) all confirmed exact-match against `02_SOURCE-INVENTORY.md`.
- [x] T-012/Katzmann's cohort n correctly uses 1,639/796 (not 6,429/533) everywhere it is cited in
      `06_adherence-residual-risk.md` and `08_traceability-table.md` — matches Decision 2026-08-31-11's
      final resolution.
- [x] **Finding 1 (RESOLVED, re-audit 2026-08-31)** — the #28 LDL-C figures in
      `40_SYNTHESIS/02_guideline-risk-positioning.md` are now anchored to exact line ranges in
      `Tonvasca_2026.md`; independently re-verified against the legacy file directly (see "Re-audit
      findings" below). No longer untraceable.
- [x] No numeric token appears silently altered from its printed source; DOI correction (citation
      #27), the Katzmann cohort-n resolution, and all other corrections are handled via logged
      Decision entries, never silently.

### Methods / Evidence

- [x] RACING (T-002) is consistently tagged `INDIRECT EVIDENCE` and never presented as
      pitavastatin-specific hard-outcome evidence — checked in `00`, `01` (C4), `04`.
- [x] HIJ-PROPER's absorber-phenotype subgroup (HR 0.71) is consistently framed as
      hypothesis-generating / `INSUFFICIENT EVIDENCE`, never as confirmed — `00`, `01` (C6), `04`.
- [x] REPRIEVE (T-015) / REAL-CAD (T-016) are never presented as FDC evidence — this is the
      project's own self-identified top overclaim risk and it is exceptionally well-guarded: every
      single appearance in `00`, `01` (C7/C8), `04`, and `08` carries an explicit "pitavastatin
      monotherapy, not FDC" qualifier. `04_cv-outcomes-hierarchy.md` in particular is built almost
      entirely around defending this boundary. No violation found.
- [x] Taiwan STS 2026 (T-005) is cited as `GUIDELINE/CONSENSUS` throughout, never as if its content
      were independently verified — `02` and `01` (C17) both explicitly and repeatedly state its
      specific "ezetimibe as first add-on" claim traces only to `pitavastatin topic.md`'s paraphrase
      and remains `BLOCKED_FOR_SOURCE`. Correctly handled.
- [x] "Add ezetimibe vs double the statin" (T-004a) is never presented as statistically significant —
      `03`, `01` (C3), `08` all correctly describe it as a descriptive point-estimate only
      (−51.4% vs −45.2%, no p/CI), consistent with Decision 2026-08-31-16.
- [x] Sydhom 2024 (#26) clinical-outcome HRs never appear without the PI-mandated
      observational-pooled-only qualifier — `00`, `01` (C9), `08` all carry it verbatim, consistent
      with Decision 2026-08-31-06/12.
- [x] Citation #29 vs #35 (Taiwan secondary- vs primary-prevention guidelines) not conflated — `02`'s
      table correctly keeps them as separate rows with structurally different content (risk-status
      recommendation vs four-tier absolute targets); this also reflects the self-correction already
      made in the Wave 3 Challenge Round (Decision 2026-08-31-32 item 1).
- [x] Citation #28 vs #30 LDL-C thresholds (<55 very-high-risk vs <50 extreme-risk) not conflated —
      `02` explicitly flags them as two different numbers from two different guidelines/risk strata;
      `01` (C19) repeats the same caution.
- [x] **Finding 1 (RESOLVED, re-audit 2026-08-31)** — #28's caveat now applied uniformly to both
      the <55 and <70 mg/dL figures and to its Lp(a) thresholds, matching how T-005/T-007 are
      already treated.
- [x] T-012's cohort n (1,639/796 for the LDL-C results, not 6,429/533) used correctly — verified
      above.

### Writing

- [x] Grep-checked: no instance of "does not cause diabetes," "no DDI," "pitavastatin 沒有交互作用," or
      any equivalent overclaim anywhere in `40_SYNTHESIS/`. Every occurrence of that language is in
      the explicit **prohibited-phrasing** role (labeled 禁止表述/禁用), never in an assertion. The
      required calibrated phrasing ("可能有較有利的血糖 profile," "low CYP3A4-dependent interaction
      liability") is used consistently in `00`, `01`, `05`.
- [x] No unresolved placeholders (grepped for TBD/TODO/XXX/FIXME/[fill — none found).
- [x] Abstract (`00`) ↔ detailed sections (`02`–`06`) ↔ matrix (`01`) ↔ traceability (`08`)
      internally consistent — cross-checked the Level 1/2/3 framework, the Sydhom framing, the
      REPRIEVE/REAL-CAD boundary, and the dose-comparison significance finding across all files; all
      consistent, no drift between files.
- [x] Causal language check: `06_adherence-residual-risk.md` explicitly requires associational, not
      causal, language for the FDC-adherence-outcomes chain given healthy-adherer bias in all
      supporting sources (T-012, T-022, T-025) — correctly worded throughout as "與較佳結果相關,"
      never "FDC 可改善結果."
- [x] Residual-risk/Lp(a) content (`06`) is ~254 words against ~2,650 words of narrative content
      across `00`+`02`–`07` (excluding the reference tables `01`/`08`) — approximately 9.6% of
      narrative output, within the Research Charter's ≤10–15% bound.
- [x] **Finding 1 (RESOLVED, re-audit 2026-08-31)** — `06_adherence-residual-risk.md`'s #28 Lp(a)
      paragraph now carries the same caveat as `02`, plus a more precise mg/dL-vs-nmol/L provenance
      split (mg/dL traces to `Tonvasca_2026.md` line 1361; nmol/L traces only to
      `pitavastatin topic.md` line 149) that the Director surfaced while fixing.

### Provenance

- [x] `03_DECISION-LOG.md` entries reflected consistently downstream — spot-checked Decisions 06, 11,
      16, 17, 20, 32 against their corresponding synthesis content; all consistent.
- [x] No Sci-Hub / unauthorized-access provenance anywhere in `40_SYNTHESIS/` (grepped, no matches);
      the six `BLOCKED_FOR_SOURCE` items are recorded as blocked, not routed around.
- [x] No secrets found in the repository (grepped for API-key/token/password/bearer patterns; only
      matches are the project's own prior secret-scan *process* documentation, not actual secrets).
- [x] **Finding 1 (RESOLVED, re-audit 2026-08-31)** — `02_SOURCE-INVENTORY.md` row 56 now carries
      exact line-range citations to both legacy sources for the LDL-C and Lp(a) figures;
      `08_traceability-table.md` now has entries for the previously-missing <70 mg/dL and Lp(a)
      numbers. Independently re-verified against `Tonvasca_2026.md`/`pitavastatin topic.md` directly
      — see "Re-audit findings" below.

---

## Re-audit findings (second pass, 2026-08-31)

**Finding 1: RESOLVED.** Independently re-verified, not just accepted on the Director's word:

- Read `Tonvasca_2026.md` lines ~1330–1362 and ~1420–1481 directly. Confirmed: the "Not very high
  risk: ≥50% reduction & <70 mg/dL" / "very high risk: ≥50% reduction & <55 mg/dL" table is
  reproduced verbatim, attributed in-file to "Blumenthal RS, et al. J Am Coll Cardiol. Published
  online March 13, 2026. doi:10.1016/j.jacc.2025.11.016" — citation #28's exact DOI. The <70 mg/dL
  figure the first audit pass could not find anywhere in the repository **does exist** in the
  legacy source; it was real project content that had simply never been anchored in
  `02_SOURCE-INVENTORY.md` or `08_traceability-table.md` — not a fabricated number, confirming the
  Director's own verification.
- Read `pitavastatin topic.md` lines 145–153 directly. Confirmed: "≥50 mg/dL / ≥125 nmol/L 為 risk
  enhancer" appears there, sourcing the nmol/L conversion specifically to the PI's topic notes (L-001)
  — matching the Director's claim that this figure does **not** trace to `Tonvasca_2026.md`.
- Read `Tonvasca_2026.md` lines 1330–1362 (the "Risk enhancers" table under the PREVENT-ASCVD
  discussion). Confirmed "Lp(a) ≥50 mg/dL" appears there as a table cell, under a section citing
  reference "2" (the ACC/AHA guideline in this section's local numbering) — consistent with the
  Director's claim that the mg/dL figure traces to L-002 line 1361.
- Checked all four affected files: `02_SOURCE-INVENTORY.md` #28 row now carries exact line-range
  anchors for both sources; `40_SYNTHESIS/02` and `06` now apply the same "unverified against
  primary text" caveat to #28's numbers that T-005/T-007 already carried, worded consistently;
  `01`'s C19 entry now flags the same caveat; `08_traceability-table.md` has new rows for the <70
  mg/dL and Lp(a) figures with the same line-range provenance.
- Decision 2026-08-31-33 is complete, accurate, and correctly attributes the correction path.

**New minor observation (not a blocker):** `08_traceability-table.md` now has a stale, less-detailed
duplicate row — "`Lp(a) ≥50 mg/dL 或 ≥125 nmol/L | 06 | #28 | row 56`" (near line 50) — left over
from before the fix, sitting a few rows below the new, more precise entry that supersedes it
("`Lp(a) ≥50 mg/dL（mg/dL單位）/ ≥125 nmol/L（nmol/L換算）...`", line 46). The two rows do not
disagree on any value, so this is not a traceability or numeric-integrity problem — just an
un-deduplicated leftover that should be removed the next time `08` is touched, for tidiness.

## Findings from the first audit pass

### Finding 1 (material — numeric traceability / evidence-hierarchy consistency) — RESOLVED, see
### "Re-audit findings" above. Original write-up preserved below for the record, not current status.

**Location:** `40_SYNTHESIS/02_guideline-risk-positioning.md`, lines 16–28 (risk-stratification table)
and, secondarily, `40_SYNTHESIS/06_adherence-residual-risk.md`, lines 36–38 (Lp(a) thresholds); also
reflected in `01_claim-evidence-matrix.md` row C19.

**Issue:** Citation #28 (2026 ACC/AHA guideline) has never had its full text obtained — confirmed
`BLOCKED_FOR_SOURCE` in `02_SOURCE-INVENTORY.md` row 56, unresolved through Wave 2 and Wave 3. The
owning specialist's own working file says this explicitly and in strong terms:

> `20_EVIDENCE/guideline-risk/evidence-map.md`, lines 26–30: "The specific numeric claims (the
> <55 mg/dL very-high-risk goal, and the exact PREVENT/CAC/Lp(a)/ApoB risk-refinement mechanics) are
> **not yet independently extracted from the primary document** by this role... Do not treat the
> <55 mg/dL figure as confirmed against the primary source until Wave 2 full-text extraction is done;
> it currently traces only to `pitavastatin topic.md`."

That extraction was never subsequently done (T-005/T-006/#34/#28/T-007/citation #33's tables are the
six items the PI directed stay `BLOCKED_FOR_SOURCE` without further attempts, per Decision
2026-08-31-27/29-31 and `07_limitations-open-gaps.md`).

Despite this, `40_SYNTHESIS/02`'s risk-stratification table presents #28's numbers as ordinary
`GUIDELINE/CONSENSUS` content with no caveat:

- `<55 mg/dL` (very-high-risk secondary prevention) — traceable at least to `CLAUDE.md`'s own
  Search-Protocol framing (itself sourced from `pitavastatin topic.md`), so not fabricated, but
  presented without the "unverified against primary text" caveat the project applies elsewhere to
  claims with the identical provenance chain (PI's topic notes → `CLAUDE.md` → synthesis, primary
  document never obtained).
- **`<70 mg/dL, ≥50% 降幅` for "Not very-high-risk 次級預防"** — this specific figure does **not**
  appear anywhere else in the repository. It is not in `CLAUDE.md`, not in `01_RESEARCH-CHARTER.md`,
  not in `02_SOURCE-INVENTORY.md` row 56, and not in guideline-risk's own `evidence-map.md`,
  `wave2-fulltext-extraction.md`, or `wave2-item6-extraction.md`. It has no entry in
  `08_traceability-table.md` either — a genuine, unattributed number that traces to nothing in this
  project's evidence base.
- The parallel Lp(a) threshold for #28 (`≥50 mg/dL 或 ≥125 nmol/L`, in `06`) is stated flatly, while
  the immediately adjacent ESC 2025 (T-007) Lp(a) threshold in the same paragraph correctly carries
  "此ESC 2025數字...原文未驗證，依 PI 論點筆記轉述" — the identical caveat is not applied to #28's
  number one sentence earlier, even though #28 and T-007 have the exact same access status
  (`BLOCKED_FOR_SOURCE`, never resolved) and the exact same ultimate provenance
  (`pitavastatin topic.md`'s paraphrase, never independently checked against primary text).

This is precisely the class of issue the project's own Wave 3 Challenge Round (Decision
2026-08-31-32, item 2) already caught and fixed once — for T-007's Lp(a) threshold specifically,
relative to T-005 — but the same inconsistency was not caught for #28 relative to T-005/T-007, and
the `<70 mg/dL, ≥50% 降幅` line is a step further: an apparently new, untraceable number, not merely
a missing caveat on an already-recorded one.

**Why this matters:** `CLAUDE.md` §9's Numeric Integrity Rule is the project's most emphasized,
non-negotiable rule, and `08_traceability-table.md`'s own stated purpose (line 52–55) is exactly to
catch this: "任何在 `40_SYNTHESIS/` 中出現、但未列於本表的數字，均應視為潛在的未追溯數字，須退回
Director 補充來源." This number meets that self-defined criterion for return.

**Recommended correction (for the Director, not performed by this audit — auditor is read-only):**
(a) add the same "unverified against primary text, traces only to `pitavastatin topic.md`" caveat to
#28's entries in `02` and `06` that T-005/T-007 already carry; (b) either source the
`<70 mg/dL, ≥50% 降幅` "not very-high-risk" line to an actual location in `02_SOURCE-INVENTORY.md`
(if guideline-risk in fact has it recorded somewhere not yet merged into this branch — cf. the
known multi-worktree consolidation lag noted throughout `05_STATUS.md`) or remove it / mark it
`EXPERT INTERPRETATION`/`NEEDS_ANALYST` pending verification; (c) add a corresponding row to
`08_traceability-table.md` once resolved.

**Severity assessment:** Narrow in scope (confined to a handful of lines in `02` and `06`, one
matrix row in `01`), does not affect the project's carefully-guarded top overclaim risk
(REPRIEVE/REAL-CAD/FDC) or any of the other seven known traps this project has specifically defended
against, all of which check out cleanly. But it is a genuine, unambiguous violation of the Numeric
Integrity Rule on a specific number, not a stylistic nit — it must be corrected before this synthesis
can be marked `FINAL`.

### Minor observations (no correction required, noted for completeness)

- `07_limitations-open-gaps.md` and `04_OPEN-QUESTIONS.md` are consistent on all six
  `BLOCKED_FOR_SOURCE` items and the four Challenge Round priority findings — no drift.
- The T-025 R10/E10 subgroup-vs-overall caveat (Decision 2026-08-31-29) is correctly and consistently
  applied in both `01` (C16) and `06`.
- `08_traceability-table.md`'s row-number cross-references were spot-checked in full against
  `02_SOURCE-INVENTORY.md`'s actual line numbers (all ~30 references) and are accurate — a
  well-maintained table overall, which is what makes Finding 1's gap (an entry that should exist but
  doesn't) more notable rather than less.
- `50_MANUSCRIPT/` correctly contains no content beyond `.gitkeep`, consistent with the PI's
  not-authorized-this-wave decision (Decision 2026-08-31-28).

## Final Gate recommendation (superseded by re-audit below — kept for the record)

~~`HOLD_FOR_CORRECTION`~~ — see revised recommendation below.

---

## Final Gate recommendation (re-audit, 2026-08-31 — current)

## `PASS_WITH_MINOR_ISSUES`

**Reasoning:** The first audit pass found this project's evidence base and synthesis
exceptionally well-disciplined overall, with one material Numeric Integrity Rule violation
(Finding 1). The Director's correction cycle (commit `06d5c38`, Decision 2026-08-31-33) has been
independently re-verified in this pass — including reading the underlying legacy sources
(`Tonvasca_2026.md`, `pitavastatin topic.md`) directly rather than trusting the Director's cited
line numbers — and Finding 1 is confirmed resolved: the previously-untraceable <70 mg/dL figure is
genuine legacy-source content (not fabricated) that is now correctly anchored with exact line
ranges, the "unverified against primary text" caveat is now applied uniformly to citation #28's
numbers wherever they appear, and `08_traceability-table.md` now has entries for the
previously-missing figures.

All eight project-specific known traps named in the original audit brief (RACING/pitavastatin
conflation, HIJ-PROPER subgroup overstatement, REPRIEVE/REAL-CAD/FDC conflation, Taiwan STS
mis-tiering, the dose-comparison significance overclaim, the Sydhom framing, the #29/#35 and
#28/#30 threshold conflations, and the Katzmann cohort-n mix-up) remain correctly and consistently
guarded throughout `40_SYNTHESIS/00`–`08`. No forbidden overclaim language, no secrets, no Sci-Hub
provenance, no unresolved placeholders, and residual-risk content stays within its charter bound.
The six `BLOCKED_FOR_SOURCE` items remain honestly recorded as such per the PI's own Gate 2 exit
criteria, not treated as resolved.

The only remaining item is the minor, non-blocking cosmetic duplicate row now present in
`08_traceability-table.md` (documented above under "Re-audit findings") — the two Lp(a) rows do
not disagree on any value, so this does not constitute a traceability or numeric-integrity failure,
only tidiness debt. Per Runbook §36, `PASS_WITH_MINOR_ISSUES` may be marked `FINAL`. Recommend: the
Director may deduplicate the `08` row at its own convenience (no urgency, no re-audit required for
that alone) and this project may proceed to Final Gate `FINAL` on the Wave 3 synthesis as currently
committed.
