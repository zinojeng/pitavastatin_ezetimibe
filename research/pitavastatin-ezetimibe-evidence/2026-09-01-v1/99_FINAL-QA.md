# 99_FINAL-QA — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

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

1. **Decision -10's causal narrative for "2.4 mmol/L" is slightly overstated in specificity** — see
   spot-check #4 above. The corrected numbers are right; the stated root cause ("our own tooling's
   artifact") should more precisely say the artifact appears to be reproduced independently by at
   least two extraction pipelines, not uniquely this project's own. No action required unless this
   decision is revisited for another reason.
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

## Final Gate recommendation

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
