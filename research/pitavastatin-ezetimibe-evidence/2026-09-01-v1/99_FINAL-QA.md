# 99_FINAL-QA — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

---

## RE-CHECK ADDENDUM 2 (2026-09-01): outstanding file now confirmed corrected — Final Gate restored to `PASS_WITH_MINOR_ISSUES`

The Director was right that my prior HOLD_FOR_CORRECTION check was stale: `20_EVIDENCE/guideline-risk/
focus-area-1-guideline-wording.md` had not yet been corrected at the moment I first checked it, but
guideline-risk's fix (cherry-picked onto this branch at commit `54b8c42`, recorded in Decision
2026-09-01-15) landed shortly after. Working directly in `worktree-pit-eze-run-2026-09-01` (the same
branch the Director asked me to re-check, not a stale reference), I confirm `git log` shows
`54b8c42`/`cd4e4c7`/`32dedf6` present in this worktree's history, and I re-read the current file fresh
(not from any cached context).

**Re-verified independently, not just trusted:**
- `grep -n "does not exist" focus-area-1-guideline-wording.md` — all 8 occurrences are inside past-tense
  correction-history narrative ("this role wrongly concluded...", "an earlier version... wrongly
  concluded it 'does not exist'... that conclusion is itself now corrected") — none is a live,
  present-tense assertion that the figure is absent. The Methods caution header, §1's Tier 2 quote and
  its dedicated source-internal-inconsistency callout (with `SOURCE_VALUE`/`FLAG`/`ACTION` fields
  correctly following the Numeric Integrity Rule's own prescribed format), §3's cross-pointer, §5's
  table cell and note, and the Summary's three-round correction history are all now consistent with
  `00_executive-synthesis.md` §2.2, `02_evidence-traceability-table.md`, and `02_SOURCE-INVENTORY.md`
  T-106 — same two page numbers (e1159/e1199), same two values (2.4/2.6 mmol/L), same "2.6 controls per
  document convention, 2.4 retained as annotated anomaly, mg/dL target unaffected" resolution, same
  attribution of independent confirmation via four separate extraction passes (guideline-risk's
  `pdftotext -f 6 -l 6` isolated single-page check, the PI's raw `pdftotext`, the Director's PyMuPDF,
  and this audit's own independent PyMuPDF re-extraction in the first correction addendum below).
- `grep -rn "2\.4 mmol"` across `40_SYNTHESIS/`, `50_MANUSCRIPT/`, `20_EVIDENCE/`,
  `02_SOURCE-INVENTORY.md` — every occurrence is consistent with the corrected account; no stray
  "does not exist"/"purely an artifact" framing survives anywhere in the currently-committed content.
  `50_MANUSCRIPT/` confirmed (again) to not reference this granular table at all.
- `03_DECISION-LOG.md` Decision 2026-09-01-15 accurately describes what guideline-risk changed and
  matches what I independently see in the file — no discrepancy between the decision log's summary and
  the actual diff.

**No outstanding correction remains.** The one item that justified `HOLD_FOR_CORRECTION` in the first
correction addendum (below) is resolved. All other findings/observations from both the original report
and the first correction addendum stand unaffected (the K-924 verification, retraction greps, Taiwan
STS/inclisiran discipline, and the commit-hash provenance nit remain as previously stated).

**Revised Final Gate recommendation: `PASS_WITH_MINOR_ISSUES`.** This run's handling of the "2.4 vs 2.6
mmol/L" episode — including surfacing and correcting a post-Final-Gate error rather than letting a
`PASS` stand on a factual mistake — is, in this auditor's assessment, a genuine demonstration of the
Numeric Integrity Rule and Golden Rule 8/9 working as intended across three independent people/roles
(PI, Director, guideline-risk) plus this auditor's own participation in both the error and its
correction. Per Runbook §36, `PASS_WITH_MINOR_ISSUES` may be marked `FINAL`.

---

## CORRECTION ADDENDUM (2026-09-01, post-Final-Gate reopening, Decision 2026-09-01-14)

**This audit's original "spot-check #4" (below) reached the wrong conclusion, and this addendum
corrects it honestly rather than quietly editing the original text out.** The original report is
preserved unmodified below the line; read this addendum first, as it supersedes spot-check #4's
finding and the Final Gate recommendation that partly relied on it.

### What went wrong in the original audit

Spot-check #4 grepped line 369 of the `official/` `.md` derivative, found "2.4 mmol/L" sitting inside
what read as a garbled, two-fragment-concatenated sentence, and concluded this corroborated
guideline-risk's `pdftotext -raw` conclusion that "2.4 mmol/L" does not exist as real source content
— i.e., that it was purely an extraction artifact. **This was an error of method, not just conclusion:**
the `.md` derivative is a single, already-known-artifact-prone extraction pipeline; finding a garbled
rendering there is not evidence that the underlying PDF itself lacks a coherent, genuinely-printed
value — it is only evidence that *that one pipeline* rendered it badly. The correct check — independently
re-extracting the actual PDF with a tool distinct from both the `.md` derivative's pipeline and
guideline-risk's `pdftotext`, and reading the surrounding sentence in full — was not done. Had it been
done, it would have shown what the PI's and Director's independent checks (below) show: a complete,
coherent, non-garbled sentence.

### Independent re-verification performed for this addendum

Using PyMuPDF (`fitz`) — a third extraction pipeline, distinct from both `pdftotext` (used by
guideline-risk and, per the Director's report, the PI) and the intake's own `.md`-conversion pipeline
(used, mistakenly, by this audit's original spot-check #4) — this audit independently re-extracted the
actual PDF (not the `.md` derivative) and confirms, matching the Director's Decision 2026-09-01-14
exactly:

- **PDF page e1159** (PDF page index 5 by direct 0-indexed page count; "Table 1. 2018 vs 2026" summary
  comparison table, row "4.2.4.3. Severe Hypercholesterolemia With LDL-C ≥190 mg/dL," "Revised" 2026
  column) contains, as a complete, grammatically coherent sentence with no interleaving or fragment
  concatenation:
  > "COR 1: In adults with severe hypercholesterolemia with LDL-C ≥190 mg/dL (4.9 mmol/L) without
  > clinical ASCVD but with clinical or genetic confirmation of HeFH, additional ASCVD risk factors,
  > or documented coronary calcification, who are on maximally tolerated statin therapy, the addition
  > of ezetimibe, a PCSK9 mAb and/or bempedoic acid to achieve a goal of LDL-C <70 mg/dL (1.8 mmol/L)
  > and non–HDL-C <100 mg/dL (2.4 mmol/L) is recommended to lower LDL-C and reduce ASCVD risk."
- **PDF page e1199** (PDF page index 45; authoritative numbered "Recommendations for Severe
  Hypercholesterolemia With LDL-C ≥190 mg/dL" section, recommendation #4, COR 1/LOE B-R) contains, for
  the textually near-identical clinical population and LDL-C target:
  > "...the addition of ezetimibe, a PCSK9 mAb, and/or bempedoic acid to achieve a goal of LDL-C
  > <70 mg/dL (1.8 mmol/L) and non–HDL-C <100 mg/dL (2.6 mmol/L) is recommended to lower LDL-C and
  > reduce ASCVD risk."

Both are complete, well-formed, non-garbled sentences. This audit independently confirms: **"2.4
mmol/L" is genuinely, coherently printed in T-101 at page e1159; a genuinely different value, "2.6
mmol/L," is printed at page e1199 for what reads as the same recommendation. This is a real
source-internal printing inconsistency in the published guideline, not an artifact of any extraction
tool** (this audit's original spot-check #4's tool included). The mg/dL target itself (`<100 mg/dL`)
is unaffected and consistent at both locations.

### Verification of downstream corrections

- [x] `03_DECISION-LOG.md` Decision 2026-09-01-14 — read in full; accurately documents the correction,
      the exact quotes/pages (matching this audit's independent re-extraction exactly), and an honest
      process-failure account naming all three roles that missed this (guideline-risk, Director, and
      this auditor) — appropriately unflinching, not self-serving toward any one role.
- [x] `02_SOURCE-INVENTORY.md` T-106 entry — added, consistent with Decision -14.
- [x] `40_SYNTHESIS/00_executive-synthesis.md` §2.2 — corrected. The revised 3-tier table now correctly
      states `<100 mg/dL (2.6 mmol/L)` as the controlling value for Tier 2 with an explicit inline note
      that the source's own summary table independently prints `2.4 mmol/L` for the same target, and
      that this is a source-internal inconsistency rather than an artifact. This matches the correct,
      non-silent Numeric Integrity Rule treatment (report both printed values, flag the inconsistency,
      do not silently pick one without disclosure) — and is now, correctly, closer to the *original*
      Decision 2026-09-01-08 framing than to the reversed Decision 2026-09-01-10 framing.
- [x] `40_SYNTHESIS/02_evidence-traceability-table.md` — corrected, consistent with the above.
- [ ] **`20_EVIDENCE/guideline-risk/focus-area-1-guideline-wording.md` — NOT YET CORRECTED.** This
      audit independently re-checked this file (not merely trusted `05_STATUS.md`'s checklist) and
      confirms it still asserts, in multiple places (lines ~64–71, ~175, ~230, ~255–260 at the time of
      this check), the now-superseded claim that "there is no '2.4 mmol/L' figure anywhere in the
      actual severe-hypercholesterolemia recommendations... it does not correspond to a real
      recommendation at all." **This is a live, material contradiction between a specialist's owned
      evidence file and the corrected synthesis it is supposed to ground** — exactly the "claim ↔
      citation" and "no stale/superseded values" failure mode the Final QA Checklist (Runbook §35,
      Writing section) exists to catch. This is not a new independent error — it is the same not-yet-
      applied correction already identified and routed by the Director (Decision 2026-09-01-14 action
      item 3, `05_STATUS.md`) — but it is still outstanding as of this audit, and this audit cannot
      correct it directly (file ownership: `focus-area-1-guideline-wording.md` belongs to
      guideline-risk-intelligence, not the auditor).
- [x] `50_MANUSCRIPT/` — independently re-checked (not just trusted the Director's note): confirmed
      `pitavastatin-ezetimibe-positioning-slides.md` does not contain the granular severe-
      hypercholesterolemia tier table or either mmol/L figure at all — no correction needed there.

### Revised assessment

This is a genuine, still-open internal inconsistency in the repository as of this audit — not
resolved by the corrections already made to `03_DECISION-LOG.md`/`02_SOURCE-INVENTORY.md`/
`40_SYNTHESIS/`. Until `focus-area-1-guideline-wording.md` is corrected, a reader who follows the
citation trail from `00_executive-synthesis.md` §2.2 back to its underlying evidence file will find
the evidence file flatly contradicting the synthesis that cites it. This is narrow in scope (one file,
a handful of lines, an easy and already-identified fix) but it is a live writing-consistency failure,
not a hypothetical one, and per this project's own discipline (never treat a known-wrong document as
if it were already fixed) this audit cannot recommend a clean `PASS`/`PASS_WITH_MINOR_ISSUES` while it
remains uncorrected.

**Revised Final Gate recommendation: `HOLD_FOR_CORRECTION`**, narrowly scoped to one outstanding
action: correct `20_EVIDENCE/guideline-risk/focus-area-1-guideline-wording.md` (lines ~64–71, ~175,
~230, ~255–260 at time of this check) to match `00_executive-synthesis.md` §2.2's corrected framing —
i.e., replace "there is no 2.4 mmol/L figure... does not exist" with the corrected account (2.4 mmol/L
genuinely printed at page e1159, Table 1; 2.6 mmol/L genuinely printed at page e1199, the authoritative
recommendation; source-internal inconsistency, 2.6 mmol/L controls per document-wide convention, 2.4
mmol/L retained as an annotated source anomaly, not discarded). Once that one file is corrected, this
audit expects (but will independently re-verify, not merely assume) that this run returns to
`PASS_WITH_MINOR_ISSUES` — the underlying facts are now correctly established and well-documented
everywhere else; only this one specialist file's text has not yet caught up. No other outstanding
issue was found in this re-audit beyond the one already noted in the original report (see below,
now itself superseded on the "2.4 mmol/L" point specifically — the commit-hash provenance quirk noted
in the original "Minor observations" #2 still stands independently and is unaffected by this
correction).

**Everything below this line is the original, unmodified Wave 4 report, preserved for the record.**
Its spot-check #4 and the parts of its Final Gate reasoning that relied on spot-check #4 are
superseded by this addendum; all of its other findings (retraction greps, K-924 verification, Taiwan
STS/inclisiran discipline checks, T-101 verification-methodology honesty, etc.) are unaffected and
still stand.

---

**Owner: independent-auditor.** Wave 4 audit, read-only, conducted 2026-09-01 against the fully
consolidated Director branch `worktree-pit-eze-run-2026-09-01`. Reviewed `CLAUDE.md`,
`docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`, all six governance files (`00`–`05`), every file in
`10_DATA/`, `20_EVIDENCE/`, `30_METHODS/`, `40_SYNTHESIS/`, `50_MANUSCRIPT/`, `90_CROSS-SESSION-LOG/`,
and the prior closed run's `2026-08-31-v1/99_FINAL-QA.md` for baseline context. Verification was not
taken on the Director's word alone: independent `grep` passes were run across `40_SYNTHESIS/` and
`50_MANUSCRIPT/`, `git log`/hash checks were run against the actual worktree, and the `official/`
guideline `.md` derivative was independently grepped against several quotes cited in
`20_EVIDENCE/guideline-risk/focus-area-1-guideline-wording.md` and
`20_EVIDENCE/safety-pharmacology/positioning-brief.md`/`attack-defense-contribution.md`.

---

## Final QA Checklist

### Numbers

- [x] K-924 matched-dose LS-difference figures (−11.9% [95% CI −15.2 to −8.7], −12.7% [95% CI −15.9
      to −9.4]) are traceable to trials-efficacy's own prior-run (2026-08-31-v1 Wave 2) LlamaParse
      full-text extraction, hashed on file. The originally-relayed "−51.4% vs −45.2%" cross-arm claim
      is correctly retracted everywhere it could recur (see grep results below).
- [x] The K-924 raw four-arm descriptive percentages (−39.5%/−45.2%/−51.4%/−57.8%) are preserved
      correctly wherever they still appear (`positioning-brief.md` §1.1) with an explicit correction
      note distinguishing them from the retracted cross-arm comparison — not silently dropped, not
      silently reused as a comparison.
- [x] HIJ-PROPER overall primary endpoint (HR 0.89, 95% CI 0.76–1.04, P=0.152) stated identically
      everywhere it appears (`00_executive-synthesis.md` §1/§5, `01_attack-defense.md` A, manuscript
      Slide 4) — no drift.
- [x] TE-016 (sitosterol subgroup, HR 0.71, 95% CI 0.56–0.91) and TE-017 (baseline-LDL-C subgroup,
      N=686/743, HR 1.13/0.72, interaction P=0.012) figures are stated consistently across
      `evidence-map.md`, `extraction-table.csv`, `00_executive-synthesis.md` §5, and manuscript
      Slide 4 — no numeric drift between files.
- [x] REAL-CAD (HR 0.81, 95% CI 0.69–0.95, P=0.01) and the three hard-outcome comparator trials
      (CLEAR-Outcomes, FOURIER, ODYSSEY OUTCOMES) DOIs/figures consistent across
      `evidence-map.md`, `01_attack-defense.md` C/F.1, `02_evidence-traceability-table.md`.
- [x] **Independently re-verified against the primary `.md` derivative** (not just trusted from the
      specialists' extraction files): the "East Asian ancestry... initial treatment should be with
      lower doses" quote, the ezetimibe 18%/25% figure, the PCSK9 mAb 45–64% "well tolerated and
      safe" language, the inclisiran 48–52% "well tolerated" language, and the bempedoic acid
      21–24%/17–18% "statin-attributed side effects" language all substantively match what is cited
      in `focus-area-1-guideline-wording.md` and `positioning-brief.md`/`attack-defense-contribution.md`
      §2.1b (see "Independent spot-checks" section below for the exact grep evidence and a caveat
      about this document's two-column PDF layout producing line-interleaving artifacts that make a
      naive single-line grep unreliable — this does not affect the correctness of the cited
      quotes, which were pulled with a proper `pdftotext -layout`/`-raw` pass by the specialists, not
      naive grep).
- [x] **Numeric Integrity Rule corrections are genuinely transparent, not silent** — three separate
      corrections this run (K-924 cross-arm retraction, COR 2a→1 grading, and the "2.4 mmol/L does
      not exist" finding) are each documented with before/after values, a stated root cause, and an
      explicit acknowledgment in `03_DECISION-LOG.md` and `00_executive-synthesis.md` §2.2.

### Methods / Evidence Hierarchy

- [x] RACING tagged `INDIRECT EVIDENCE`/`NONINFERIORITY` consistently everywhere (executive synthesis
      §1/§7/§8, attack A/B/C, manuscript Slide 3) — never presented as pitavastatin-specific.
- [x] HIJ-PROPER's two subgroups (TE-016, TE-017) are kept as two distinct, non-conflated axes
      everywhere checked, each tagged `SUBGROUP/HYPOTHESIS-GENERATING`, never upgraded to
      `SUPERIORITY`. TE-017's interaction P=0.012 is correctly described as raising the subgroup's
      methodological weight without being escalated to a settled/general claim — this distinction is
      maintained consistently, including in the manuscript slide notes.
- [x] Taiwan STS 2026's specific "ezetimibe as first add-on" content claim is stated as
      `BLOCKED_FOR_SOURCE` with equal prominence in the internal synthesis (`00_executive-synthesis.md`
      §0/§6), the attack/defense document, and the presentation-facing manuscript (dedicated Slide 11,
      explicitly marked "must be kept in any formal presentation"). This is the single highest-risk
      item this run's own specialists flagged, and it was not softened in the audience-facing document
      relative to the internal one — confirmed by direct comparison, not assumed.
- [x] Inclisiran is never grouped with bempedoic acid/PCSK9i as "hard-outcome-proven" without the
      no-published-outcome-trial caveat. Checked every occurrence in `01_attack-defense.md` F.1/F.2,
      `00_executive-synthesis.md` §7/§9, `02_evidence-traceability-table.md`, and manuscript Slide 9 —
      the caveat is present at every occurrence, including the one place inclisiran is paired with
      PCSK9i for a *different* claim (DDI-mechanism favorability on Slide 9's OATP1B1 row, not
      hard-outcome status) — that pairing is evidence-appropriate (siRNA/mAb mechanism argument, not
      an outcomes claim) and does not contradict the hard-outcome caveat rule.
- [x] T-101 is never cited as pitavastatin-specific or FDC-specific anywhere in `40_SYNTHESIS/` or
      `50_MANUSCRIPT/` — checked every reference; each carries a "statin-agnostic" or equivalent
      qualifier.
- [x] REPRIEVE/REAL-CAD boundary (pitavastatin monotherapy, not FDC) is preserved this run wherever
      REAL-CAD is newly emphasized (Attack C) — correctly scoped as "SUPERIORITY, but for pitavastatin
      dose intensity, not the FDC."
- [x] T-101's verification methodology (DOI resolution + Crossref metadata + internal-coherence
      review, explicitly *not* a byte-for-byte publisher re-download) is represented consistently and
      honestly everywhere it is cited — `02_SOURCE-INVENTORY.md` T-101, `03_DECISION-LOG.md` Decision
      2026-09-01-04, `00_executive-synthesis.md` §2.1, and the manuscript's Slide 1 speaker note all
      state or imply the same calibrated confidence level. No instance found where T-101 is referred
      to as "the official guideline" without qualification, or where the Cloudflare-wall caveat is
      dropped.

### Writing

- [x] Grep-checked (`grep -in "does not cause diabetes\|no DDI"`): every hit across `20_EVIDENCE/`,
      `40_SYNTHESIS/` is inside an explicit "never write this" prohibition, never used as a live claim.
      The calibrated phrasing ("可能有較有利的血糖側寫" / "low CYP3A4-dependent interaction liability")
      is used consistently wherever the underlying evidence is invoked.
- [x] No unresolved placeholders found (TBD/TODO/XXX/FIXME/[fill) in `40_SYNTHESIS/`/`50_MANUSCRIPT/`.
- [x] `00_executive-synthesis.md` ↔ `01_attack-defense.md` ↔ `02_evidence-traceability-table.md` ↔
      `50_MANUSCRIPT/` internally consistent — cross-checked the Level 1/2/3 framework, the two-caveat
      "must not be removed" rule stated in §0, and the "cannot say" list (manuscript Slide 12) against
      every location those items are discussed; no drift found.
- [x] The manuscript's own explicit instruction ("任何刪減本文件內容以製作精簡版投影片時，不得刪除誠實
      限制/攻防段落") is a genuinely unusual and good practice for a presentation-facing document —
      worth noting as a strength, not just a pass/fail item.

### Provenance

- [x] `03_DECISION-LOG.md` decisions (04, 05, 06, 07, 08, 09, 10, 11, 12) are each reflected
      consistently downstream — spot-checked all against their corresponding synthesis content.
- [x] No Sci-Hub / `download_paper` usage anywhere in this run's search logs (grepped
      `30_METHODS/*/search-log.md` and the evidence files) — every specialist explicitly logs that
      the prohibited tools were "not used."
- [x] No secrets found in tracked content.
- [x] `inbox/2026-acc-aha-drive/` (including `official/`) is correctly excluded from git tracking —
      independently confirmed via `.gitignore` (both the shared-checkout stray edit and the worktree's
      own copy correctly list `inbox/`), and the PDF/`.md`/manifest files were independently
      re-hashed by this audit and match the SHA-256 values recorded in `00_RUN-MANIFEST.md` and
      `T-101-official-source-verification.md` exactly.
- [x] Decision 2026-09-01-10 (superseding the PI's own "preserve the 2.4 mmol/L annotation"
      instruction) is handled transparently: `03_DECISION-LOG.md` states the supersession and its
      reasoning explicitly under an "Explicitly flagged for the PI" heading, `00_executive-synthesis.md`
      §2.2 repeats the same explanation in the synthesis itself (not just the decision log), and
      `30_METHODS/shared/gate3-challenge-round.md` §5 records a deliberate, separate check that this
      was not silently done. This is exactly the disclosure standard the project's own governance
      requires (never silently comply with an outdated instruction, never silently override it either).

---

## Independent spot-checks performed by this audit (not merely re-reading specialist files)

1. **Git/commit verification**: `git log --oneline` on the consolidated branch confirms the commit
   sequence claimed in `03_DECISION-LOG.md`/`05_STATUS.md` exists (86 commits total), including the
   3-tier severe-hypercholesterolemia correction commit (`8a1ab51`), the Decision -10 commit
   (`4d0be8d`), the K-924 upgrade commit (`6226c47`), and the Wave 3 synthesis commits. One very minor
   provenance quirk noted, not a defect: `05_STATUS.md`/`03_DECISION-LOG.md` reference commit hashes
   `b7bf5fa` and `38f40a9` for safety-pharmacology's own branch state before cherry-pick; these exact
   hashes do not appear verbatim in the consolidated branch's `git log` (expected — cherry-picking
   changes commit hashes). This does not affect content traceability, only the literal hash strings
   quoted in prose; worth a note for anyone trying to `git show` those hashes directly on this branch.
2. **File/hash verification**: independently re-computed SHA-256 for
   `2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_Circulation.{pdf,md}` and
   `OFFICIAL_SOURCE_MANIFEST.md` from the actual intake folder — all three match the values recorded
   in `00_RUN-MANIFEST.md` and `T-101-official-source-verification.md` exactly.
3. **Direct quote spot-check against the `.md` derivative** (`grep` on the actual file, not the
   specialists' transcriptions): confirmed the substance of the "East Asian ancestry... lower doses"
   quote, the "should be added" (COR 1) ezetimibe/PCSK9 language, the "no longer require that
   ezetimibe" sequencing-removal language, the ezetimibe 18%/25%, PCSK9 mAb 45–64%/"well tolerated and
   safe", inclisiran 48–52%/"well tolerated", and bempedoic acid 21–24%/17–18%/"statin-attributed side
   effects" language. All match in substance. **Important caveat surfaced by this check**: this
   document's `.md` derivative is extracted from a two-column PDF layout with visible
   line-interleaving artifacts (e.g. line 2014 reads "...the patient (mAbs) can lower LDL-C by 45% to
   64%, are well tolerated" — two unrelated column fragments concatenated) — this independently
   corroborates the project's own repeated finding (Decisions -08/-10, safety-pharmacology's and
   guideline-risk's search logs) that this source is genuinely artifact-prone under naive extraction,
   and validates the specialists' discipline of treating the numbered "Recommendations for [topic]"
   sections as authoritative over summary tables and over the `.md` derivative alone.
4. **The "2.4 mmol/L" resolution, re-examined independently**: this audit located line 369 of the
   `.md` derivative directly — it reads "...inhibitor may be considered. (2.4 mmol/L) is recommended
   to lower LDL-C and reduce ASCVD risk," which is visibly a concatenation of two unrelated sentence
   fragments (consistent with the same column-interleaving artifact class as finding 3 above), not a
   clean, isolated printed value. This corroborates — via a source independent of guideline-risk's own
   `-raw`-mode re-extraction — that "2.4 mmol/L" is not reliable, artifact-free source content.
   **One residual gap worth noting** (minor, not blocking): `03_DECISION-LOG.md` Decision -10 frames
   the root cause purely as "this project's own `pdftotext -layout` tooling's artifact," without
   acknowledging that the `.md` derivative — produced by a separate extraction pipeline the project
   does not control — independently shows the same "2.4 mmol/L" figure (safety-pharmacology's search
   log records finding it at the same location, describing it at the time as "a faithful, accurate
   transcription" of the `.md`, before guideline-risk's later `-raw`-mode check against the PDF's
   authoritative section superseded that framing). The final correction is still almost certainly
   right — the authoritative numbered-recommendations section is the correct thing to trust over any
   summary table or derivative, and this audit's own line-369 read confirms the `.md` value sits in an
   obviously garbled sentence — but the decision log's causal narrative ("our own tooling's artifact,
   not the source's") is *slightly* overstated in its specificity; a more precise framing would be
   "an artifact of this document's two-column layout, reproduced independently by at least two
   different extraction pipelines (this project's `pdftotext -layout` and the intake's own `.md`
   conversion), resolved by treating the authoritative recommendations section as ground truth." This
   does not change the correct final numbers (already fixed) and does not warrant reopening the
   decision — flagged as a precision nit for the record, not a correction requirement.
5. **Retraction grep pass**, run independently of (and before reading) `30_METHODS/shared/gate3-challenge-round.md`'s
   own claimed grep results, to avoid rubber-stamping the Director's self-check:
   - `grep -rn "51\.4\|45\.2" 40_SYNTHESIS/ 50_MANUSCRIPT/` — all 3 hits are in explicit
     retraction/do-not-cite/speaker-note-warning context. No live citation found.
   - `grep -rn "2\.4 mmol" 40_SYNTHESIS/ 50_MANUSCRIPT/` — all 6 hits are inside the correction
     narrative explaining the figure does not exist. No live citation found. (Confirmed no occurrence
     anywhere else in the run folder outside `03_DECISION-LOG.md`, `20_EVIDENCE/guideline-risk/`, and
     `30_METHODS/safety-pharmacology/search-log.md`, all of which are correction/search-process
     narrative, not live claims.)
   - `grep -rin "does not cause diabetes\|no DDI" 40_SYNTHESIS/ 50_MANUSCRIPT/ 20_EVIDENCE/` — all
     hits are inside "never write this" prohibition sentences.
   - `grep -rn "consistent with Taiwan STS" 40_SYNTHESIS/ 50_MANUSCRIPT/ 20_EVIDENCE/` — the only
     manuscript hit is on the "cannot say" list (Slide 12); the only evidence-file hit is inside
     safety-pharmacology's own correction note describing the erroneous attribution it removed. No
     live guideline-attribution use found.
   - `grep` for inclisiran across `40_SYNTHESIS/`/`50_MANUSCRIPT/` — every occurrence in a
     hard-outcome-status context carries the "no published hard-outcome trial" caveat; the one
     DDI-context pairing with PCSK9i (manuscript Slide 9) is evidence-appropriate, not a violation.
   This independent pass reaches the same conclusion as the Director's own Gate 3 grep pass — a
   genuine confirmation, not just an agreement of two unverified claims.

---

## Findings

### No material findings requiring correction

This run's synthesis and manuscript output are consistent, well-calibrated, and — notably — the
project's own specialists and Director surfaced and transparently corrected three separate numeric-
integrity issues *during* this run (K-924 cross-arm retraction, COR grading, and the "2.4 mmol/L"
non-existence finding) before this audit began, which is exactly the intended function of the
Challenge Round / Numeric Integrity Rule discipline this project runs on. All eight
previously-established traps (from the prior run's audit) plus this run's five new specific risk
areas named in this audit's brief were checked and none were found violated.

### Minor observations (no correction required)

1. **SUPERSEDED, see the correction addendum at the top of this file.** This observation originally
   said Decision -10's causal narrative was "slightly overstated in specificity" but that "the
   corrected numbers are right." That was wrong on the more important point: Decision -10's numbers
   were *not* right — "2.4 mmol/L" is genuinely printed source content, not an artifact, and Decision
   -10 has since been reversed by Decision 2026-09-01-14. This audit's own spot-check #4 (below)
   independently reached the same mistaken conclusion Decision -10 did, for the same underlying reason
   (relying on the artifact-prone `.md` derivative instead of independently re-extracting the PDF with
   a different tool). Left unedited below for the record; see the addendum for the correction and its
   process-failure account.
2. **Commit-hash provenance quirk**: `b7bf5fa`/`38f40a9` referenced in prose in `03_DECISION-LOG.md`/
   `05_STATUS.md` are pre-cherry-pick hashes on safety-pharmacology's own branch and do not resolve
   directly via `git show` on the consolidated Director branch. Cosmetic only — the content itself is
   correctly present and cited by path, not solely by hash.
3. **Carried-forward, already-honestly-flagged limitations** (not audit findings, restated here only
   for completeness since the audit brief asked about them specifically): Taiwan STS 2026's content
   claim remains `BLOCKED_FOR_SOURCE` and is correctly the most prominently-flagged unverified
   load-bearing assumption in the whole project (Slide 11, executive synthesis §6); inclisiran's
   hard-outcome gap is correctly and consistently flagged; the FDC-vs-high-intensity-statin
   head-to-head gap (Q6) and FDC-specific CKD dosing gap (Q7) are honestly stated as unresolved
   limitations rather than papered over with adjacent evidence.
4. **T-101 verification is appropriately hedged, not overclaimed**: every citation of the
   verification method this audit checked used calibrated language ("verification by independent
   corroboration," "not a byte-for-byte publisher re-download") rather than presenting DOI+Crossref
   verification as equivalent to a direct publisher download. This is a genuinely good practice this
   audit wants to note explicitly rather than only note its absence of violation.

---

## Final Gate recommendation (original — SUPERSEDED, see correction addendum at top of this file)

**This section is superseded. Current recommendation is `HOLD_FOR_CORRECTION`, stated in the
correction addendum at the top of this file — read that first.** Preserved below unmodified for the
record.

## `PASS_WITH_MINOR_ISSUES`

**Reasoning:** No numeric-integrity violations, no evidence-hierarchy misapplications, no conflation
of the project's known traps (RACING/pitavastatin, HIJ-PROPER subgroup overstatement, Taiwan STS
content-vs-bibliography, inclisiran hard-outcome status, T-101 overclaiming, or the "does not cause
diabetes"/"no DDI" prohibited phrasing) were found anywhere in `40_SYNTHESIS/` or `50_MANUSCRIPT/`,
verified via this audit's own independent greps and file/hash checks rather than by trusting the
Director's or specialists' self-reported checks alone. The three numeric-integrity corrections made
mid-run were each handled with full transparency (before/after values, stated reasoning, explicit
acknowledgment of superseding a PI instruction where applicable) — this is the Numeric Integrity Rule
functioning as intended, not a defect. The only items noted are a precision nit in one decision's
causal narrative (does not affect the corrected numbers) and a cosmetic pre-cherry-pick commit-hash
reference — neither rises to a level requiring correction before this synthesis can be treated as
`FINAL`. Per Runbook §36, `PASS_WITH_MINOR_ISSUES` may be marked `FINAL`.

**Recommend:** the Director may, at its own convenience and with no urgency, soften Decision -10's
causal wording per observation 1 above; no other action is required. This run's `40_SYNTHESIS/` and
`50_MANUSCRIPT/` outputs are ready to proceed to Final Gate.
