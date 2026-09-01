---
marp: true
paginate: true
---

# Pitavastatin + Ezetimibe FDC
## Clinical Positioning and Honest Defense

**Treat the target, not the dose.**

PROJECT: pitavastatin-ezetimibe-evidence · RUN 2026-09-01-v1
Final Gate: **PASS_WITH_MINOR_ISSUES** (independent audit complete)

<!-- Speaker note: every number in this deck is traceable to the project's 20_EVIDENCE/40_SYNTHESIS files and can be cited directly during Q&A. This deck deliberately retains honest limitations and defense sections — they are not cut for narrative flow. -->

---

## Reframing the Core Question

**"Should we treat the statin dose, or treat the LDL target?"**

- The 2026 ACC/AHA guideline (DOI `10.1161/CIR.0000000000001423`, independently verified this run) structures treatment around **absolute LDL-C/non-HDL-C targets**
- Four risk-stratified targets: <100 / <70 / <55 mg/dL, each with a paired non-HDL-C co-goal
- Not "relative percent reduction" but "at goal or not"
- **Honest verification-method limitation**: `ahajournals.org` is Cloudflare-walled to this project's tools,
  so T-101's verification is **verification by independent corroboration** (DOI resolution 302 redirect,
  Crossref metadata match, systematic 123-page internal-coherence review) — **not** a byte-for-byte
  re-download from the publisher; this limitation must be disclosed honestly, never stated as a
  word-for-word match against the publisher's original file

<!-- Speaker note: GUIDELINE/CONSENSUS. Full traceability: 40_SYNTHESIS/00_executive-synthesis.md §2.1, §3; Decision 2026-09-01-04. If asked "did you actually read the full original text," explain the three independent corroboration methods and the Cloudflare limitation honestly — don't overstate it as a word-for-word comparison. -->

---

## Severe Hypercholesterolemia (LDL-C≥190 mg/dL): Three-Tier Absolute Targets

T-101 sets a **three-tier** structure for this population (not a single target), cross-verified by three independent extraction tools:

| Tier | LDL-C target | non-HDL-C target | COR/LOE |
|---|---|---|---|
| Tier 1: no ASCVD/HeFH/subclinical atherosclerosis/other risk factors | <100 mg/dL (2.6 mmol/L) | <130 mg/dL (3.4 mmol/L) | 1, B-NR |
| Tier 2: with HeFH/subclinical atherosclerosis/other risk factors, no clinical ASCVD | <70 mg/dL (1.8 mmol/L) | <100 mg/dL (**2.6 mmol/L**, see note below) | 1, B-R |
| Tier 3: with clinical ASCVD | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1, B-R |

**Honest Tier 2 non-HDL-C note (must not be omitted)**: the guideline's authoritative numbered
recommendation (page e1199, rec #4) prints **2.6 mmol/L** — consistent with the standard conversion for
100 mg/dL and with every other "<100 mg/dL" appearance in the document; this table adopts that value.
But the same guideline's own "Table 1. 2018 vs 2026" summary comparison table (page e1159) **genuinely,
completely, without any break** prints the same recommendation's non-HDL-C target as **2.4 mmol/L** —
this is a printing inconsistency **internal to the source publication itself** (most plausibly a typo in
the summary table), **not** an artifact of any extraction tool used by this project — so it is retained
as an annotation, not discarded, as a source anomaly. The LDL-C target itself (<70 mg/dL) matches at
both locations and is unaffected.

<!-- Speaker note: GUIDELINE/CONSENSUS. This finding took three rounds of correction to finalize (Decision 2026-09-01-08→10→14) — the correction process itself is a live demonstration of the Numeric Integrity Rule, and can be honestly cited in Q&A as evidence of methodological rigor. -->

---

## Level 1 Evidence: LDL-Lowering Efficacy (Strong)

- Pitavastatin/ezetimibe FDC internationally reproduced: Taiwan/Australia/NZ (Chou 2022, Clin Ther), Japan (K-924, Tsujita 2023)
- K-924 matched-dose LS-difference (independently verified):
  - combo 2/10 vs pitava 2mg: **−11.9%** (95% CI −15.2 to −8.7)
  - combo 4/10 vs pitava 4mg: **−12.7%** (95% CI −15.9 to −9.4)
- **"−51.4% vs −45.2%" has been retracted** — never a prespecified statistical comparison in this trial, do not cite it

<!-- Speaker note: DIRECT EVIDENCE / LDL-C SURROGATE EFFICACY. If asked about the old cross-arm number, honestly explain it was retracted and cite the figures above instead. -->

---

## Level 2 Evidence: Strategy-Level CV Outcome (Not Pitavastatin-Specific)

- RACING: rosuvastatin 10mg + ezetimibe 10mg vs high-intensity monotherapy
- 3-yr MACE **9.1% vs 9.9%** (non-inferior)
- **Explicit disclosure: this is rosuvastatin evidence, not pitavastatin evidence**
- Strategy-level indirect support, not FDC-specific direct evidence

<!-- Speaker note: INDIRECT EVIDENCE / NONINFERIORITY. "This isn't your drug" is a fair challenge — just acknowledge it honestly; that's exactly the distinction this project deliberately marks. -->

---

## Level 3 Evidence: Pitavastatin/Ezetimibe-Specific Hard Outcome (Honest: Not Yet Proven)

- HIJ-PROPER overall primary endpoint: 32.8% vs 36.9%, **HR 0.89 (95% CI 0.76–1.04, P=0.152)** — did not reach statistical superiority
- Two hypothesis-generating subgroup signals (**must not be merged into one claim**):
  - Sitosterol/absorber-phenotype: **HR 0.71** (MODERATE confidence)
  - Baseline-LDL-C stratification (high-LDL-C group): **HR 0.72**, interaction **P=0.012**
- This project has not yet found FDC-specific, proven hard-outcome superiority evidence

<!-- Speaker note: this is the core honest limitation of this presentation — state it proactively, don't avoid it. The two subgroups are stratified by different variables and must be presented independently. -->

---

## Guideline Support: Scope and Limits (POST-FINAL-GATE corrected)

**Very-high-risk (VHR) secondary prevention** (T-101 page e1208):
- Ezetimibe **and/or** PCSK9 mAb: **COR 1, LOE A** (no preference between the two)
- Bempedoic acid: a separate, lower **COR 2a, LOE B-R**
- Inclisiran: **COR 2a, LOE B-R**, limited to patients unable to tolerate/access PCSK9 mAb or with a clear preference for less-frequent dosing

**Non-VHR**: ezetimibe / PCSK9 mAb / bempedoic acid **genuinely equal** (COR 2a, LOE B-R)

<!-- Speaker note: GUIDELINE/CONSENSUS, statin-agnostic, must not be cited as pitavastatin-specific evidence. At VHR, there is no guideline preference for ezetimibe over PCSK9 mAb specifically — this is a limitation any "ezetimibe preferred" argument must disclose; but there IS a formal preference for ezetimibe/PCSK9 mAb over bempedoic acid/inclisiran (COR 1 vs 2a). -->

---

## Taiwan / East Asian Population Positioning

- T-101's own statement: East Asian populations "may be more prone to side effects due to inherited drug metabolism effects; thus, initial treatment should be with lower doses"
  - This is a statin-**class**, general statement, **not** pitavastatin-specific
- Li 2026 (China retrospective cohort, pitavastatin 4mg vs atorvastatin 20mg, ≥60y): NODM **0% vs 10.29%** (OR 0.212)
  - Single-center, observational, non-randomized, small sample

<!-- Speaker note: the guideline passage is GUIDELINE/CONSENSUS; Li 2026 is an OBSERVATIONAL SIGNAL and cannot independently support a conclusion. -->

---

## Three Safety Pillars: Glycemic / DDI / CKD

- **Glycemic**: pitavastatin, relative to other commonly used high-potency statins, **may have a more favorable glycemic profile** — never write "does not cause diabetes"
- **DDI**: **low CYP3A4 dependence** — never write "no interactions"; OATP1B1-pathway risk (cyclosporine contraindicated, gemfibrozil to be avoided) still applies
- **CKD**: pitavastatin monotherapy is the most conservative dosing among all listed statins (1mg starting/2mg ceiling); **FDC-specific CKD data remains lacking**

<!-- Speaker note: always keep calibrated language such as "relative to..." and "may" — this is a mandatory language rule for this project, in force since RUN 2026-08-31-v1. -->

---

## Adherence and Real-World Evidence

- FDC vs. separate prescriptions: LDL-C reduction difference **−28.4% vs −19.4%** (p<0.0001, Katzmann 2022)
  - **This study has no direct adherence measurement** — "the FDC improves adherence" is an inference chain, not direct proof
- Pitavastatin+ezetimibe FDC-specific RWE: **currently only one study, TE-013** (Taiwan post-PCI, N=120, single-arm, two centers)
  - The evidence base remains thin

<!-- Speaker note: LDL-C SURROGATE EFFICACY / OBSERVATIONAL SIGNAL. If asked "is the RWE adequate," honestly answer that only one study currently exists. -->

---

## Defense: When NOT to Choose Pitavastatin/Ezetimibe FDC

| Scenario | More appropriate alternative |
|---|---|
| Established statin intolerance | Ezetimibe monotherapy + bempedoic acid, or PCSK9-targeting therapy |
| Known high-risk OATP1B1 polypharmacy (cyclosporine, gemfibrozil) | PCSK9-targeting therapy or inclisiran |
| Ongoing dialysis (ESRD/HD) | PCSK9-targeting therapy (a conservative option, not proven safer) |
| Seeking a hard-outcome-proven alternative | Bempedoic acid (CLEAR-Outcomes), PCSK9i (FOURIER/ODYSSEY OUTCOMES) |

**Exception**: Inclisiran has **no** published hard-outcome trial — it should not be listed alongside bempedoic acid/PCSK9i as an equally "proven" alternative

<!-- Speaker note: this is a deliberately retained honest defense slide — raise it proactively during Q&A rather than waiting for a challenger to bring it up. -->

---

## Defense: Is "Maximize the Statin Dose First" Outdated?

**No** — this is a reasonable position with direct pitavastatin-specific evidence support:

- REAL-CAD (pitavastatin 4mg vs 1mg): **HR 0.81** (95% CI 0.69–0.95, P=0.01) — statistically significant
- The 2026 ACC/AHA guideline itself still uses "statin first" as its Class 1 recommendation structure (stepwise, not upfront combination)
- **Honest limitation**: this project found no direct head-to-head trial of pitavastatin/ezetimibe FDC vs.
  high-intensity statin monotherapy — RACING is the rosuvastatin version, K-924 is an internal
  pitavastatin dose comparison; neither is direct evidence for this specific comparison
- The real question is not "has combination replaced dose maximization" but: when a patient can tolerate dose escalation, can the FDC make the transition faster and more comfortable

<!-- Speaker note: REAL-CAD = SUPERIORITY, but limited to the pitavastatin dose-intensity question, not the FDC. FDC vs. dose maximization direct comparison = EXPERT INFERENCE, no direct data (04_OPEN-QUESTIONS.md Q6). -->

---

## The Largest Unverified Load-Bearing Claim: Taiwan STS 2026

- Taiwan STS (Suboptimally Tolerable Statins) 2026 consensus — "repositioning ezetimibe as the preferred first-line add-on for high/very-high-risk patients" — is the core organizing concept of this project's overall framing
- **Reconfirmed this run: its specific content claim remains `BLOCKED_FOR_SOURCE`** (Cloudflare-blocked, unrelated to its OA licensing status — confirmed as genuine Gold OA/CC BY, but full text still cannot be retrieved)
- **This project's own self-assessment: this is the single largest unverified-but-load-bearing claim** — more consequential than any individual trial-level evidence gap

<!-- Speaker note: this slide must be retained in any formal presentation — never omitted for narrative flow. If asked about the specific content of the Taiwan STS recommendation, honestly answer: the bibliographic information has been verified to exist, but this project has not obtained independently verifiable full text of the specific content. -->

---

## Conclusion: A Defensible Positioning Statement

**Can be said:**
- Pitavastatin/ezetimibe FDC has robust, internationally reproduced LDL-C-lowering evidence (Level 1)
- The 2026 ACC/AHA guideline supports the statin+ezetimibe combination strategy as a COR 1, LOE A recommendation for the VHR population (statin-agnostic)
- Pitavastatin's low CYP3A4 dependence and relatively favorable glycemic profile give it a reasonable pharmacological positioning in specific polypharmacy/East Asian contexts

**Cannot be said:**
- "The FDC has been proven to reduce cardiovascular events" (Level 3 not yet achieved)
- "The guideline recommends ezetimibe as the preferred add-on" (the guideline lists options in parallel, without preferring ezetimibe)
- "Pitavastatin does not cause diabetes" / "has no drug interactions"
- "Consistent with Taiwan STS 2026" for any specific content claim not yet independently verified

<!-- Speaker note: this slide is the overall summary — any abridged version of this deck must retain all four "cannot be said" points. -->
