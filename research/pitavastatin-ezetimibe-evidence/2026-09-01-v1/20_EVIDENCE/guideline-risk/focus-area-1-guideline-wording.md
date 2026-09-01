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

**Evidence Hierarchy tag for everything below: GUIDELINE / CONSENSUS.**
**Claim-safe taxonomy tag: guideline recommendation** (per this run's focus-area-6 taxonomy) — these
are formal Class-of-Recommendation (COR) / Level-of-Evidence (LOE) statements from a multi-society
clinical practice guideline, not trial results themselves; cite the underlying trials separately
when a recommendation's supportive text names them.

## 1. Goal-directed LDL-C treatment (absolute targets, not just % reduction)

The guideline is explicitly structured around **absolute LDL-C and non-HDL-C goals**, stratified by
risk category (Section 4.2.4–4.2.7, "2018 vs 2026" comparison table, page ~e1155 onward):

> **Severe hypercholesterolemia, LDL-C ≥190 mg/dL, with clinical ASCVD (new in 2026, COR 1):** "...
> who are on maximally tolerated statin therapy, the addition of ezetimibe, a PCSK9 mAb, or
> bempedoic acid is recommended to achieve a goal of LDL-C <55 mg/dL (1.4 mmol/L) and non–HDL-C
> <85 mg/dL (2.2 mmol/L) to lower LDL-C and reduce ASCVD risk."

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

> **At very high risk, on maximally tolerated statin (COR 2a):** "...ezetimibe and/or a PCSK9 mAb
> **should be added** (selected based on the degree of LDL-C lowering needed and patient preference)
> to achieve a goal of LDL-C <55 mg/dL (1.4 mmol/L) and non–HDL-C <85 mg/dL (2.2 mmol/L)..." — note
> the stronger "should be added" phrasing (vs. "reasonable to add" for the lower-risk tier), though
> both are COR 2a — a wording nuance worth preserving exactly, not smoothing into identical language.

> **Ezetimibe's own efficacy figure (synopsis text, page ~e1229 area):** "Ezetimibe lowers LDL-C
> levels by a mean of 18% (25% incremental reduction when added to statin therapy) and has a low
> incidence of side effects."

> **Severe hypercholesterolemia (LDL-C ≥190) without clinical ASCVD (COR 1, new 2026):** "...the
> addition of ezetimibe, a PCSK9 mAb and/or bempedoic acid to achieve a goal of LDL-C <70 mg/dL
> (1.8 mmol/L) and non–HDL-C <100 mg/dL (2.4 mmol/L) is recommended..."

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
| Severe hypercholesterolemia (LDL-C≥190) + clinical ASCVD | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1 |
| Severe hypercholesterolemia (LDL-C≥190), no clinical ASCVD | <70 mg/dL (1.8 mmol/L) | <100 mg/dL (2.4 mmol/L) | 1 |
| CAC ≥1000 AU | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1 |

All figures transcribed exactly as printed (Numeric Integrity Rule) — note the 2.4 vs 2.2 mmol/L
non-HDL-C figures for the two ≥190-mg/dL rows are **printed differently in the source itself**
(2.4 mmol/L for the no-ASCVD row, 2.2 mmol/L for the with-ASCVD row) — not a transcription error on
this role's part, reproduced exactly as the guideline itself states it; flagging only because the
two numbers are easy to assume are typos of each other and conflate — they are not, per the source.

## Summary

- Focus area 1 substantively fulfilled: exact, COR/LOE-graded, page-locatable quotes obtained for
  goal-directed treatment, ezetimibe add-on, statin-intolerance positioning, and high/very-high-risk
  target attainment, all from a now-verified primary source.
- One deliberately-flagged negative finding: "early/upfront combination therapy" is not this
  guideline's own framing — it is sequential/add-on. This is a citable, real transatlantic contrast,
  not a gap in this role's search.
- The Taiwan STS "ezetimibe as first add-on" gap (carried forward from the prior run) is **not**
  resolved by this source — it is a different, still-unobtained document. Explicitly not conflated.
