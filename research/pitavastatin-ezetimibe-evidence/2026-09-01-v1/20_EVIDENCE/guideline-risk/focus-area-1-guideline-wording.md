# Focus area 1 — exact 2026 ACC/AHA guideline wording

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Owner: guideline-risk-intelligence · Wave 1, Priority 2

Source: `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_
Circulation.pdf` — **VERIFIED** this Wave, see `T-101-official-source-verification.md`. All quotes
below were pulled from `pdftotext -layout` output of the **PDF itself** (not the `.md` derivative),
per Decision 2026-09-01-03's requirement to spot-check against the PDF to rule out conversion errors.
Locator = approximate line number in the `pdftotext -layout` extraction (a working artifact, not
committed) plus the guideline's own printed page number (e.g., "e1239") and section number where
visible — cite the page number in any downstream synthesis, not the pdftotext line number, which is
tool-specific and not stable.

**Methods caution, revised after a third correction round (Decision 2026-09-01-14 — supersedes the
"does not exist" conclusion below in §1/§5, which was itself wrong):** this document's "Table 1.
[2018 vs 2026] Continued" summary comparison tables (used for §1's original severe-hypercholesterolemia
quote) are **column-merge-prone under `pdftotext -layout`**, which produced a real, confirmed COR-grade
error (§3). But the `2.4 mmol/L` figure this role twice concluded was purely an extraction artifact
(first as a "likely typo," then as "does not exist anywhere in the actual text") **is genuinely
printed at page e1159 of the summary table, as a complete, coherent, non-garbled sentence** — this
role independently re-confirmed it a third time via `pdftotext -f 6 -l 6` (isolating that single
physical page, ruling out any cross-page content bleed), after the PI and Director each independently
confirmed it with two other tools (raw `pdftotext` on the PI's side, PyMuPDF on the Director's). **The
correct account is: T-101 is genuinely internally inconsistent between its own summary table (e1159:
`2.4 mmol/L`) and its authoritative numbered-recommendations section (e1199: `2.6 mmol/L`) for the
same Tier 2 recommendation** — a source-internal discrepancy, not a tooling artifact, and not
something to drop from the record. **Process lesson, stated plainly:** a "this value does not exist"
conclusion needs the same independent scrutiny as the inconsistency it claims to resolve — this role's
own `-raw`-mode check only searched the authoritative section, not the summary table itself, so it
could not have found the very value it was concluding was absent. **Continuing to treat the numbered
"Recommendations for [topic]" sections as controlling for which figure to build synthesis on** (per
the guideline's own more detailed, risk-stratum-specific drafting), **but the summary table's
divergent figure is now recorded, not discarded.**

**Evidence Hierarchy tag for everything below: GUIDELINE / CONSENSUS.**
**Claim-safe taxonomy tag: guideline recommendation** (per this run's focus-area-6 taxonomy) — these
are formal Class-of-Recommendation (COR) / Level-of-Evidence (LOE) statements from a multi-society
clinical practice guideline, not trial results themselves; cite the underlying trials separately
when a recommendation's supportive text names them.

## 1. Goal-directed LDL-C treatment (absolute targets, not just % reduction)

The guideline is explicitly structured around **absolute LDL-C and non-HDL-C goals**, stratified by
risk category (Section 4.2.4–4.2.7, "2018 vs 2026" comparison table, page ~e1155 onward):

**Severe hypercholesterolemia (LDL-C ≥190 mg/dL) is actually a three-tier structure, not two** —
corrected this round from the authoritative "Recommendations for Severe Hypercholesterolemia With
LDL-C ≥190 mg/dL" section (page ~e1199), not the error-prone summary comparison table:

> **Tier 1 — primary prevention, without HeFH/subclinical atherosclerosis/additional ASCVD risk
> factors, without clinical ASCVD (COR 1, LOE B-NR):** "...the addition of ezetimibe, a PCSK9 mAb,
> and/or bempedoic acid is recommended to achieve a goal of LDL-C <100 mg/dL (2.6 mmol/L) and a
> non–HDL-C goal of <130 mg/dL (3.4 mmol/L) and to reduce ASCVD risk."

> **Tier 2 — with HeFH, subclinical atherosclerosis, or additional ASCVD risk factors, without
> clinical ASCVD (COR 1, LOE B-R):** "...the addition of ezetimibe, a PCSK9 mAb, and/or bempedoic
> acid to achieve a goal of LDL-C <70 mg/dL (1.8 mmol/L) and non–HDL-C <100 mg/dL (**2.6 mmol/L**) is
> recommended to lower LDL-C and reduce ASCVD risk." (page e1199, numbered recommendation #4 of the
> "Recommendations for Severe Hypercholesterolemia" section — treated as controlling; see the
> flagged discrepancy immediately below.)
>
> **Source-internal inconsistency, confirmed genuine (Decision 2026-09-01-14) — not a tooling
> artifact:** the same recommendation, printed in T-101's own "Table 1. 2018 vs 2026" summary
> comparison table at page **e1159**, reads: "...the addition of ezetimibe, a PCSK9 mAb and/or
> bempedoic acid to achieve a goal of LDL-C <70 mg/dL (1.8 mmol/L) and non–HDL-C <100 mg/dL
> (**2.4 mmol/L**) is recommended to lower LDL-C and reduce ASCVD risk." — a complete, coherent
> sentence, independently confirmed by this role via an isolated single-page extraction
> (`pdftotext -f 6 -l 6`, ruling out cross-page contamination), and separately by the PI (raw
> `pdftotext`) and the Director (PyMuPDF) before this correction was requested. **SOURCE_VALUE
> (summary table, e1159) = `2.4 mmol/L`; SOURCE_VALUE (authoritative section, e1199) = `2.6 mmol/L`;
> FLAG = SOURCE_INTERNAL_INCONSISTENCY; ACTION = NEEDS_PI** if this figure is ever needed at a
> precision finer than "the mg/dL target is unambiguous" — do not silently prefer one over the
> other without saying so, and do not drop the `2.4 mmol/L` value from the record (an earlier version
> of this file wrongly concluded it "does not exist anywhere in the actual text" — that conclusion is
> itself now corrected, see the Methods caution above). For this project's purposes, the `<70 mg/dL`
> LDL-C target is unaffected and unambiguous either way; only the non-HDL-C mmol/L co-goal is
> disputed between the source's own two internal presentations.

> **Tier 3 — with clinical ASCVD (COR 1, LOE B-R):** "...the addition of ezetimibe, a PCSK9 mAb,
> and/or bempedoic acid is recommended to achieve a goal of LDL-C <55 mg/dL (1.4 mmol/L) and
> non–HDL-C <85 mg/dL (2.2 mmol/L) to lower LDL-C and reduce ASCVD risk."

**Correction history for this passage (kept for transparency, not condensed away):** this role's
*first* extraction pass (pulled from the summary comparison table only) conflated Tiers 1 and 2 into
a single row and additionally mis-set the LDL-C figure; the Director's QA catch (Decision
2026-09-01-08) correctly flagged the resulting `2.4 mmol/L` as internally inconsistent within that
one row. This role's *second* pass over-corrected by concluding, after checking only the
authoritative section, that `2.4 mmol/L` "does not exist anywhere in the actual text" — wrong, per
the third round above; it exists, genuinely, in the summary table specifically. The three-tier
structure itself (Tier 1/2/3 split) was correctly identified in the second pass and remains correct;
only the characterization of the `2.4 mmol/L` figure as fully fictitious was wrong, now fixed.

> **Diabetes, no established ASCVD, 40–75y (revised 2026, COR 1):** "...moderate-intensity statin
> therapy is indicated to achieve ≥30% to 49% reduction in LDL-C and a goal of LDL-C <100 mg/dL
> (2.6 mmol/L) and non–HDL-C <130 mg/dL (3.4 mmol/L) to reduce ASCVD risk."

> **Diabetes with multiple ASCVD risk factors (revised 2026, COR 2a):** "...reasonable to prescribe
> high-intensity statin therapy to achieve ≥50% reduction in LDL-C and a goal of LDL-C <70 mg/dL
> (1.8 mmol/L) and non–HDL-C <100 mg/dL (2.6 mmol/L) to reduce ASCVD risk."

> **Secondary ASCVD prevention, not at very high risk (revised 2026, COR 1):** "...high-intensity
> statin therapy should be initiated to achieve ≥50% reduction in LDL-C and a goal of LDL-C
> <70 mg/dL (1.8 mmol/L) and non–HDL-C <100 mg/dL to reduce the risk of recurrent ASCVD events."

> **Clinical ASCVD at very high risk (new 2026, COR 1, LOE A):** "In adults with clinical ASCVD*
> who are at very high risk (Figure 10 and Figure 11), high-intensity statin therapy should be
> initiated to achieve a ≥50% reduction in LDL-C and a goal LDL-C <55 mg/dL (1.4 mmol/L)..." (page
> ~e1156, numbered recommendation #4 in the Secondary ASCVD Prevention section)

> **CAC ≥1000 AU (new 2026, COR 1):** "...treatment with LDL-C–lowering therapies with
> consideration of statin therapy as first-line is recommended to achieve a ≥50% reduction in
> LDL-C and a goal of LDL-C <55 mg/dL (1.4 mmol/L) and non–HDL-C <85 mg/dL (2.2 mmol/L)."

**This directly, exactly confirms `pitavastatin topic.md`'s and `CLAUDE.md` §2.2's claim of a
"very-high-risk secondary prevention goal <55 mg/dL"** — now traced to verbatim guideline text with
its formal COR/LOE grade, not a paraphrase. Note the guideline actually specifies **four** distinct
absolute-goal tiers depending on risk category (<100, <70, <55 mg/dL, each paired with a specific
non-HDL-C co-goal) — do not flatten this to a single number in synthesis.

## 2. Early / upfront combination therapy — an important negative-but-precise finding

**This guideline does NOT appear to use the specific phrase "early combination therapy" or
"upfront combination" as a named recommendation the way the prior run found the 2025 ESC/EAS
Focused Update does** (via the Katzmann & Laufs 2026 secondary-review corroboration,
`2026-08-31-v1/20_EVIDENCE/guideline-risk/wave2-item6-extraction.md` §C). Searched systematically
(`grep -i "early combination\|upfront combination\|combination therapy"`) — the phrase "combination
therapy" appears only in narrative/synopsis prose (e.g., "More recent studies of combination
therapy have reinforced the concept that 'lower is better'...", page ~e1239 synopsis text), not as
a formal recommendation heading or COR/LOE-graded statement recommending combination therapy
*at treatment initiation* for treatment-naïve patients.

**Instead, the 2026 ACC/AHA guideline's structure is stepwise/sequential**, not upfront-combination:
Class 1 recommends **statin monotherapy first** (moderate- or high-intensity, by risk category), and
separate Class 2a recommendations add ezetimibe/PCSK9 mAb/bempedoic acid **"on maximally tolerated
statin therapy"** only when the absolute goal is not yet met — i.e., statin-first-then-add-on, not
simultaneous initiation. This is a **genuine, citable transatlantic guideline-philosophy contrast**
directly relevant to this run's focus area 1 and the attack/defense section (focus area 5): the 2026
US guideline is more conservative/sequential on combination timing than what the prior run found
attributed to the 2025 ESC/EAS Focused Update. **Flagging explicitly so this is not accidentally
smoothed over in synthesis — do not present "guidelines recommend early combination therapy" as a
transatlantic consensus; it is, on this Wave's evidence, an ESC-specific (not yet independently
primary-verified either, see the prior run's own caveat) vs. ACC/AHA-stepwise distinction.**

## 3. Ezetimibe add-on — exact recommendation language, with population stratification

> **Not at very high risk, on maximally tolerated statin (COR 2a, LOE B-R):** "...it is reasonable
> to add ezetimibe, a PCSK9 mAb, or bempedoic acid (selection depending on degree of LDL-C lowering
> needed and patient preference) to achieve a goal of LDL-C <70 mg/dL (1.8 mmol/L) and non–HDL-C
> <100 mg/dL to reduce the risk of ASCVD events." — and, in the same risk tier but framed for the
> <55 mg/dL tier context: "...to achieve a goal LDL-C <55 mg/dL (1.4 mmol/L) and non–HDL-C
> <85 mg/dL (2.2 mmol/L) and to reduce the risk of ASCVD events."

> **At very high risk, on maximally tolerated statin (COR 1, LOE A):** "In adults with clinical
> ASCVD who are at very high risk and on maximally tolerated statin therapy, ezetimibe and/or a
> PCSK9 mAb **should be added** (selected based on the degree of LDL-C lowering needed and patient
> preference) to achieve a goal of LDL-C <55 mg/dL (1.4 mmol/L) and non–HDL-C <85 mg/dL
> (2.2 mmol/L) to reduce risk of ASCVD events." (Recommendation #5 of the Secondary ASCVD Prevention
> — Very High Risk section, page ~e1208.) **Correction note (caught during T-102 intake
> cross-referencing, not left silently fixed):** this role's initial Wave 1 pass mis-transcribed
> this recommendation's grade as COR 2a — a `pdftotext -layout` column-alignment artifact (the grade
> marker for a multi-line recommendation in this guideline's two-column table sits near the middle
> of the item's text block, and an earlier, narrower extraction window cut across two adjacent
> items). Re-extracted with a wider context window and re-confirmed against the surrounding
> recommendations #4 (COR 1 A) and #6 (COR 2a B-R, bempedoic add-on) as anchors — #5 is
> unambiguously **COR 1, LOE A**. The intake's `00_quick_reference_card.md` had this correct
> ("Ezetimibe（VHR ASCVD，statin 後）| ... | 1, A（排序要求取消）") — independent cross-referencing
> against secondary material is exactly what caught this, which is itself a useful argument for not
> skipping the intake-dedup task even once a primary source is verified. The non-very-high-risk
> tier's add-on recommendation (below) remains correctly COR 2a, LOE B-R — so the "should be added"
> vs "reasonable to add" wording contrast tracks a genuine COR 1 vs COR 2a difference after all, just
> not the one originally stated.

> **Not at very high risk, on maximally tolerated statin, restated for clarity:** COR 2a, LOE B-R
> (as quoted above) — genuinely weaker than the very-high-risk tier's COR 1, consistent with the
> "should be added" (VHR, COR 1) vs "reasonable to add" (non-VHR, COR 2a) wording distinction.

> **Sequencing requirement removed (synopsis text, page ~e1208, directly answers a "why the change"
> question relevant to focus area 1):** "Since the '2018 Guideline for the Management of Blood
> Cholesterol' was published, extended safety data for PCSK9 mAb have been reported, and the cost
> has decreased substantially. Accordingly, **the revised recommendations no longer require that
> ezetimibe be added to statin therapy prior to initiating a PCSK9 mAb**, and consideration of
> therapy may be based on degree of LDL-C required and patient preference." This is a distinct
> finding from "early/upfront combination therapy" (§2 above, still not this guideline's framing) —
> it is a **removed sequencing constraint**, not a new combination-first recommendation. Both are
> real, but they are not the same claim; keep them separate in synthesis.

> **Ezetimibe's own efficacy figure (synopsis text, page ~e1229 area):** "Ezetimibe lowers LDL-C
> levels by a mean of 18% (25% incremental reduction when added to statin therapy) and has a low
> incidence of side effects."

> **Severe hypercholesterolemia (LDL-C ≥190) without clinical ASCVD** — see §1 above (Tier 1 and
> Tier 2 quotes, including the confirmed-genuine e1159-vs-e1199 `2.4`-vs-`2.6` mmol/L source-internal
> inconsistency) for the exact, current wording; not repeated here to avoid a second copy drifting
> out of sync again, which is exactly what happened once already at this location — see that
> section's correction history before citing either mmol/L figure from this passage elsewhere.

## 4. Statin intolerance / SAMS positioning (this guideline's analogue to Taiwan STS — NOT a substitute for it)

**Important scope note, stated up front:** this is the **2026 US ACC/AHA guideline's own**
statin-intolerance framework — it does **not** verify or substitute for the still-`BLOCKED_FOR_SOURCE`
Taiwan STS 2026 consensus's own specific claim (from `CLAUDE.md` §2.2 / the prior run) that Taiwan
STS "repositions ezetimibe as first add-on for high/very-high risk." That remains a distinct,
Taiwan-specific document this role has not obtained. What follows is genuinely useful **analogous,
independent US-guideline context**, not a resolution of that specific open gap.

> "Although most patients tolerate statin therapy, approximately 10% of patients may not tolerate
> maximum dose daily statin therapy in real-world populations." (page ~e1238–39 area, synopsis)

> "Nonstatin medications may be needed in addition to statin therapy to further lower LDL-C or **as
> an alternative treatment for patients with statin intolerance.**" (Section 4.2.1.2 synopsis, page
> ~e1229 area)

> "Other LDL-C–lowering therapies such as ezetimibe and PCSK9i are generally well tolerated." (SAMS
> section, page ~e1239)

> On new-onset diabetes risk (relevant to this project's own calibrated-language rule, `CLAUDE.md`
> §2.4 — cited here as guideline-level corroboration for the *already-adopted* project phrasing, not
> as new instruction to change it): "Evidence indicates that statins slightly increase the risk of
> developing new-onset diabetes in individuals with predisposing risk factors... a small number of
> patients with predisposing risk factors cross the threshold to incident diabetes sooner after
> statin therapy is initiated... potential new-onset diabetes is not a contraindication to statin
> therapy or indication for statin discontinuation." — the guideline's own 2024 CTT meta-analysis
> citation: "a small clinically insignificant increase in HbA1C of 0.06% to 0.08% after statin
> therapy is started in patients with diabetes."

**Flagging for safety-pharmacology-intelligence** (not writing to their owned paths myself, per file
ownership) — this section also contains exact hepatic-safety figures ("serious hepatotoxicity occurs
in approximately 1 in 100,000 individuals treated with statins"; "~3% of patients with
aminotransferase elevation experience persistent elevation of >3× ULN") and a specific East-Asian
pharmacogenetic caution ("Certain populations (especially East Asian ancestry) may be more prone to
side effects due to inherited drug metabolism effects; thus, initial treatment should be with lower
doses," Section 4.2.1.1 Synopsis) directly relevant to their domain (focus area 4) — will mention in
my cross-session report rather than duplicate their extraction work.

## 5. High/very-high-risk target attainment — summary table

| Risk category | LDL-C goal | non-HDL-C goal | COR (representative) |
|---|---|---|---|
| Diabetes, no ASCVD, standard risk | <100 mg/dL (2.6 mmol/L) | <130 mg/dL (3.4 mmol/L) | 1 |
| Diabetes, multiple ASCVD risk factors | <70 mg/dL (1.8 mmol/L) | <100 mg/dL (2.6 mmol/L) | 2a |
| Clinical ASCVD, not very high risk | <70 mg/dL (1.8 mmol/L) | <100 mg/dL | 1 |
| Clinical ASCVD, **very high risk** | **<55 mg/dL (1.4 mmol/L)** | **<85 mg/dL (2.2 mmol/L)** | 1 |
| Severe hypercholesterolemia (LDL-C≥190), no ASCVD/HeFH/subclinical atherosclerosis/other risk factors (Tier 1) | <100 mg/dL (2.6 mmol/L) | <130 mg/dL (3.4 mmol/L) | 1, B-NR |
| Severe hypercholesterolemia (LDL-C≥190), with HeFH/subclinical atherosclerosis/additional risk factors, no clinical ASCVD (Tier 2) | <70 mg/dL (1.8 mmol/L) | <100 mg/dL (**2.6 mmol/L** per e1199, controlling; source's own summary table at e1159 prints **2.4 mmol/L** for the same row — genuine source-internal inconsistency, see §1) | 1, B-R |
| Severe hypercholesterolemia (LDL-C≥190) + clinical ASCVD (Tier 3) | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1, B-R |
| CAC ≥1000 AU | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1 |

**Table correction history** — the three-tier structure (replacing an earlier, wrong two-tier
version) is correct and stands. The Tier 2 non-HDL-C figure went through two rounds of correction:
first flagged as internally inconsistent (Decision 2026-09-01-08), then this role wrongly concluded
`2.4 mmol/L` "does not exist" anywhere in the source (it does — page e1159's summary table — see the
full account and Decision 2026-09-01-14 in §1 above). The mg/dL target (`<100 mg/dL`) is unambiguous
either way and safe to use in `40_SYNTHESIS/`; the mmol/L co-figure is a genuine, still-unreconciled
source-internal discrepancy and should be cited as such, not resolved to a single number, unless the
PI settles it.

## Summary

- Focus area 1 substantively fulfilled: exact, COR/LOE-graded, page-locatable quotes obtained for
  goal-directed treatment, ezetimibe add-on, statin-intolerance positioning, and high/very-high-risk
  target attainment, all from a now-verified primary source.
- One deliberately-flagged negative finding: "early/upfront combination therapy" is not this
  guideline's own framing — it is sequential/add-on. This is a citable, real transatlantic contrast,
  not a gap in this role's search.
- The Taiwan STS "ezetimibe as first add-on" gap (carried forward from the prior run) is **not**
  resolved by this source — it is a different, still-unobtained document. Explicitly not conflated.
- **Self-correction, made during T-102 intake cross-referencing (see §3):** the very-high-risk
  ezetimibe/PCSK9 add-on recommendation's grade was initially mis-transcribed as COR 2a; re-extraction
  with a wider context window confirms it is **COR 1, LOE A** — a materially stronger recommendation
  than first reported. Also newly extracted: the guideline explicitly states the 2018→2026 revision
  **removed the requirement that ezetimibe precede a PCSK9 mAb** — a distinct, real finding from
  "early combination therapy" (which this guideline still does not recommend), not a walk-back of
  §2's negative finding.
- **Second self-correction (Decision 2026-09-01-08 and its follow-up):** the Director's QA catch on
  an internally-inconsistent `2.4 mmol/L` figure led to discovering this role's original severe-
  hypercholesterolemia extraction had conflated two distinct recommendation tiers into one
  non-existent hybrid. Re-extracted against the guideline's authoritative numbered recommendations
  section: severe hypercholesterolemia is genuinely a **three-tier** structure (§1), not two — this
  part of the correction was and remains right.
- **Third correction, reopening part of the second (Decision 2026-09-01-14):** this role's second
  pass additionally concluded the `2.4 mmol/L` figure itself "does not exist anywhere in the actual
  text" — **wrong**. It exists, genuinely and coherently, in T-101's own summary comparison table at
  page e1159, while the authoritative numbered-recommendations section (page e1199) prints `2.6
  mmol/L` for the same Tier 2 recommendation. This is a real **source-internal inconsistency**, not
  a `pdftotext` artifact of any kind — independently confirmed by three separate extraction tools
  across three people/roles (this role's `pdftotext -f 6 -l 6`, the PI's raw `pdftotext`, the
  Director's PyMuPDF) before this correction was made. **Process lesson recorded for this role's own
  future practice:** concluding a disputed value "does not exist" requires checking the same location
  the value was originally reported at, not just the location believed to be authoritative — this
  role's `-raw`-mode recheck only searched the authoritative section (e1199), so it structurally could
  not have found the value it went on to declare absent. Credit to safety-pharmacology's original
  root-cause hypothesis for prompting the earlier, still-valuable three-tier-structure correction, and
  to the PI/Director's independent re-verification for catching this role's own overcorrection.
