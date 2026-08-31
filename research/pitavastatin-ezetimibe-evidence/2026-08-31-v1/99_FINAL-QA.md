# 99_FINAL-QA — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

**Owner: independent-auditor.** Wave 4 audit, conducted 2026-08-31, read-only against the full
repository, against `40_SYNTHESIS/00`–`08` as primary artifact, cross-checked against
`02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md`, `04_OPEN-QUESTIONS.md`,
`30_METHODS/shared/wave2-challenge-round.md` and `wave3-challenge-round-and-gate3.md`, `CLAUDE.md`,
and `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md` §35–36. `50_MANUSCRIPT/` confirmed out of scope
(contains only `.gitkeep`).

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
- [ ] **One numeric claim in `40_SYNTHESIS/02_guideline-risk-positioning.md` is NOT traceable to any
      source in this repository — see Finding 1 below.**
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
- [ ] **Evidence-hierarchy/verification-rigor inconsistency found for citation #28's own numeric
      content — see Finding 1.**
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
- [ ] **One internal inconsistency in caveat application found within `06_adherence-residual-risk.md`
      relative to `02` — see Finding 1 (same root cause).**

### Provenance

- [x] `03_DECISION-LOG.md` entries reflected consistently downstream — spot-checked Decisions 06, 11,
      16, 17, 20, 32 against their corresponding synthesis content; all consistent.
- [x] No Sci-Hub / unauthorized-access provenance anywhere in `40_SYNTHESIS/` (grepped, no matches);
      the six `BLOCKED_FOR_SOURCE` items are recorded as blocked, not routed around.
- [x] No secrets found in the repository (grepped for API-key/token/password/bearer patterns; only
      matches are the project's own prior secret-scan *process* documentation, not actual secrets).
- [ ] **Finding 1 (below) is itself a provenance failure: a number in `40_SYNTHESIS/` with no entry in
      `08_traceability-table.md` and no corresponding content in `02_SOURCE-INVENTORY.md` — exactly
      the failure mode `08`'s own stated purpose says should be "returned to the Director" if found.**

---

## Findings

### Finding 1 (material — numeric traceability / evidence-hierarchy consistency)

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

## Final Gate recommendation

## `HOLD_FOR_CORRECTION`

**Reasoning:** The overwhelming majority of this project's evidence base and synthesis is
exceptionally well-disciplined — all eight known project-specific traps named in the audit brief
(RACING/pitavastatin conflation, HIJ-PROPER subgroup overstatement, REPRIEVE/REAL-CAD/FDC conflation,
Taiwan STS mis-tiering, the dose-comparison significance overclaim, the Sydhom framing, the
#29/#35 and #28/#30 threshold conflations, and the Katzmann cohort-n mix-up) are correctly and
consistently guarded throughout `40_SYNTHESIS/00`–`08`, and the project's own two internal Challenge
Rounds already caught and fixed several adjacent issues before this audit began — a strong sign of
good process. No forbidden overclaim language, no secrets, no Sci-Hub provenance, no unresolved
placeholders, and residual-risk content stays within its charter bound.

However, Finding 1 is a genuine, specific, correctable violation of the project's own
non-negotiable Numeric Integrity Rule — one guideline-table row (`<70 mg/dL, ≥50% 降幅`) with no
traceable source anywhere in this repository, plus an inconsistently-applied verification caveat on
adjacent #28 figures that the project has already demonstrated (twice, for T-005/T-007) it knows how
to apply correctly. Per Runbook §36, only `PASS`/`PASS_WITH_MINOR_ISSUES` may be marked `FINAL`, and
an untraceable number in the corpus is exactly the class of defect this checklist exists to catch
before that happens. The fix is narrow and does not require re-opening Wave 2/3 work or any new
literature acquisition — it is a same-Wave correction to `40_SYNTHESIS/02` and `06` (and `08` once
resolved), owned by the Research Director. Recommend: Director corrects Finding 1, then this audit
(or a follow-up pass focused solely on the corrected sections) is re-run before Final Gate is set.
