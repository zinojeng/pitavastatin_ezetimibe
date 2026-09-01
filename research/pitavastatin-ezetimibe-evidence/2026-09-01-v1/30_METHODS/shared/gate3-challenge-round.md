# Gate 3 — Director Challenge Round (internal-consistency check)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Per `CLAUDE.md` §4: "Gate 3 Director internal-consistency check," run after Wave 3 synthesis
(`40_SYNTHESIS/`, `50_MANUSCRIPT/`) and before Wave 4 independent audit. This is the Director's own
adversarial self-review across the four angles used in the prior run's Wave 2/3 challenge rounds
(guideline/trials/safety/methods), applied here to this run's synthesis output specifically.

---

## 1. Guideline angle

- [x] Every T-101 quote in `00_executive-synthesis.md`/`01_attack-defense.md` traces to
  `focus-area-1-guideline-wording.md` verbatim, not paraphrased into something stronger. Spot-checked
  the severe-hypercholesterolemia 3-tier table, the VHR ezetimibe COR 1/LOE A grade, and the
  East-Asian pharmacogenetic quote — all match source wording exactly.
- [x] "Guideline does not endorse early/upfront combination" is stated consistently across
  `00_executive-synthesis.md` §3, `01_attack-defense.md` Attack A/C, and `50_MANUSCRIPT/` Slide 5 —
  no drift toward a stronger claim in any one location.
- [x] The Taiwan STS gap is stated with equal prominence in all three synthesis documents (§6 of the
  executive synthesis, Attack A is not where it's discussed but it's not needed there; it has its own
  dedicated Slide 11 in the manuscript) — not softened in the "presentation-facing" document relative
  to the "internal" one. **This was a specific risk to check**: presentation/manuscript output is
  exactly where a load-bearing caveat could get quietly dropped for narrative flow. Confirmed it was
  not dropped — Slide 11 exists and is explicitly marked "must be kept in any formal presentation."
- [x] T-101 is never cited as pitavastatin-specific or FDC-specific anywhere in synthesis — checked
  every T-101 reference in all three `40_SYNTHESIS/` files and the manuscript.

## 2. Trials angle

- [x] RACING is tagged `INDIRECT EVIDENCE` everywhere it appears (executive synthesis §1/§7, attack
  A/B/C, manuscript Slide 3) — never presented as pitavastatin-specific.
- [x] HIJ-PROPER's overall non-significant result (HR 0.89, P=0.152) is stated before either subgroup
  finding in every document that discusses it — subgroups are never presented first in a way that
  could imply the overall result was positive.
- [x] TE-016 and TE-017 are kept as two distinct, non-conflated subgroup axes everywhere — checked
  `00_executive-synthesis.md` §5 explicitly separates them with a warning not to merge them; Slide 4
  of the manuscript preserves this separation.
- [x] The K-924 retraction (−51.4% vs −45.2%) is recorded as "do not cite" in the traceability table
  and does not appear anywhere in `40_SYNTHESIS/` or `50_MANUSCRIPT/` — grepped for "51.4" and "45.2"
  across all Wave 3 output, no hits outside the traceability table's own "retracted" section.
- [x] REAL-CAD is correctly scoped as pitavastatin-specific-but-not-FDC everywhere it's cited, and its
  statistical significance (P=0.01) is stated accurately, not inflated.

## 3. Safety/pharmacology angle

- [x] "May have a more favorable glycemic profile" / "low CYP3A4-dependent interaction liability"
  calibrated language is used verbatim, not paraphrased into a stronger claim, in every document
  (executive synthesis §8, attack D, manuscript Slide 7).
- [x] The CAPITAIN FPG +4% finding and the Katzmann 2022 no-direct-adherence-measurement limitation
  are both carried into the attack/defense section and not silently dropped — checked they appear in
  `01_attack-defense.md` D.1 and E respectively, and are echoed (in compressed form) in the manuscript.
- [x] The OATP1B1-vs-CYP3A4 distinction (the "most easily attacked" DDI nuance, per
  safety-pharmacology's own framing) is preserved with its full mechanistic explanation, not
  compressed into "low DDI" anywhere.
- [x] The East-Asian pharmacogenetic quote is correctly scoped as statin-class-general, not
  pitavastatin-specific, in every citation — checked executive synthesis §8 and manuscript Slide 6
  both carry the "does not name pitavastatin specifically" caveat.

## 4. Methods/numeric-integrity angle

- [x] All three numeric-integrity corrections this run (K-924 cross-arm retraction, the
  2.4-mmol/L-does-not-exist finding, the Taiwan-STS-attribution removal) are documented in the
  traceability table's "retracted, do not cite" section, not just buried in the decision log.
- [x] The 3-tier severe-hypercholesterolemia table appears identically (same numbers, same tier
  structure) in `00_executive-synthesis.md` §2.2 and `focus-area-1-guideline-wording.md` §5 —
  cross-checked line by line, no transcription drift introduced during synthesis.
- [x] Every specialist's confidence-level caveats (MODERATE on TE-016 quantitative content, MODERATE
  on TE-017's HR/CI, EXPERT INFERENCE tags throughout the safety/attack-defense material) survived
  into synthesis without being silently upgraded to HIGH/DIRECT — spot-checked each instance against
  the source specialist document.
- [x] `50_MANUSCRIPT/`'s "cannot say" list (Slide 12) directly enumerates the specific overclaim
  patterns this project has guarded against since the prior run (does-not-cause-diabetes, no-DDI,
  guideline-prefers-ezetimibe, CV-event-reduction-proven) — not a generic disclaimer, but the actual
  traps this project has caught in practice.

## 5. One deliberate cross-check not on the standard four-angle list

**Checked whether the PI's own "preserve the 2.4 mmol/L source-typo annotation" instruction was
handled transparently rather than silently overridden.** Confirmed: Decision 2026-09-01-10 explicitly
states the supersession and its reasoning (the factual premise changed — 2.4 mmol/L was found not to
exist in the source at all, making "preserve as source-typo" inapplicable), and
`00_executive-synthesis.md` §2.2 repeats this explanation in the synthesis itself rather than silently
using the corrected figures without explanation. This is flagged again in this Director's next report
to the PI/user, not left to be discovered only by reading the decision log.

## Verification method note

The checkmarks above were not asserted on memory alone — the retraction/calibrated-language claims
were verified with actual `grep` passes across `40_SYNTHESIS/` and `50_MANUSCRIPT/` after drafting:
`grep -n "51\.4\|45\.2"` (every hit is in explicit retraction/do-not-cite context, never asserted as
a live figure), `grep -n "2\.4 mmol"` (every hit is in the correction-narrative explaining why the
figure doesn't exist, never presented as a real value), `grep -in "does not cause diabetes\|no DDI"`
(every hit is inside a "never write this" instruction, never used as an actual claim), and a count
confirming both TE-016 and TE-017 are referenced (3 times each) in the executive synthesis with their
distinct subgroup axes intact.

## Outcome

**No inconsistencies found requiring correction.** Gate 3 declared **PASSED**. Proceeding to Wave 4
(independent audit).
