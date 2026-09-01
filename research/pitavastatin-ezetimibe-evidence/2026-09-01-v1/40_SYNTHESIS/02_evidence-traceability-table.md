# 02 Evidence Traceability Table — RUN 2026-09-01-v1 new/updated citations

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`

Additive to `2026-08-31-v1/40_SYNTHESIS/08_traceability-table.md` (not reproduced here). Lists only
citations that are **new this run** or whose status/figures **changed** this run. PMID/DOI/URL,
Evidence Hierarchy tag, and Claim-Safe Taxonomy tag given for each; reproducible search logs are in
each specialist's `30_METHODS/<role>/search-log.md`.

| ID | Citation | PMID/DOI | Status this run | Evidence Hierarchy | Claim-Safe Tag | Owner |
|---|---|---|---|---|---|---|
| T-101 | 2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the Management of Dyslipidemia. *Circulation*. 2026;153:e1154–e1276 | DOI `10.1161/CIR.0000000000001423` | **VERIFIED** (new this run — see Decision 2026-09-01-04) | GUIDELINE/CONSENSUS | guideline recommendation | guideline-risk |
| T-104 | Cross-reference resolving prior-run T-028 (Blumenthal RS et al., JACC, DOI `10.1016/j.jacc.2025.11.016`) | DOI `10.1016/j.jacc.2025.11.016` | Genuine dual co-publication with T-101 confirmed via Crossref (Decision 2026-09-01-05) | GUIDELINE/CONSENSUS | guideline recommendation | guideline-risk |
| K-924 | Tsujita K et al. *J Atheroscler Thromb*. 2023;30(11):1580-1600 | DOI `10.5551/jat.64006`, SHA-256 on file `2026-08-31-v1/10_DATA/trials-efficacy/fulltext-manifest.md` | Matched-dose LS-difference figures independently re-verified against primary full text this run (Decision 2026-09-01-09); cross-arm "−51.4% vs −45.2%" claim retracted, confirmed never a tested contrast | DIRECT EVIDENCE | LDL-C SURROGATE EFFICACY | trials-efficacy |
| TE-013 | Lu YW et al. *Acta Cardiol Sin*. 2026 (Taiwan post-PCI RWE cohort, N=120) | (prior run) | Reconfirmed as the *only* pitavastatin+ezetimibe FDC RWE found (Q5 answered) | OBSERVATIONAL EVIDENCE | observational signal | trials-efficacy |
| TE-016 | Yamaguchi J et al. "Baseline serum sitosterol level as predictor of adverse clinical events..." *Atherosclerosis*. 2018;274:139-145 | DOI `10.1016/j.atherosclerosis.2018.04.036`, PMID `29772482` | **New this run.** Identity cross-verified via research_hub/Crossref; quantitative content WebSearch-aggregated only, NOT independently fetched (403 on ScienceDirect, honestly reported) | hypothesis-generating / INSUFFICIENT EVIDENCE | SUBGROUP/HYPOTHESIS-GENERATING | trials-efficacy |
| TE-017 | HIJ-PROPER baseline-LDL-C-stratified statin-naive subgroup. *Scientific Reports*. 2021 | DOI `10.1038/s41598-021-87098-x`, PMC `PMC8021554` (open access) | **New this run.** N/cutoff HIGH confidence (2 independent tools agreed); HR/CI/p-value MODERATE confidence (single WebFetch source, PMC PDF anti-bot-blocked) | DIRECT EVIDENCE (for this pre-specified subgroup only) | SUBGROUP/HYPOTHESIS-GENERATING | trials-efficacy |
| — | REAL-CAD (Kimura T et al., pitavastatin 4mg vs 1mg, HR 0.81, 95% CI 0.69–0.95, P=0.01) | (prior run TE-012) | Reconfirmed/elevated this run as the strongest evidence *for* maximize-statin-first (Attack C) | DIRECT EVIDENCE (pitavastatin, not FDC) | SUPERIORITY (scope-limited) | trials-efficacy |
| — | CLEAR-Outcomes (Nissen SE et al., bempedoic acid). *NEJM*. 2023 | DOI `10.1056/NEJMoa2215024` | Confirmed this run for the hard-outcome comparator table (Attack F.1) | DIRECT EVIDENCE (bempedoic acid, not pitavastatin/ezetimibe) | SUPERIORITY (in its trial population) | trials-efficacy |
| — | FOURIER (evolocumab). *NEJM*. 2017 | DOI `10.1056/NEJMoa1615664` | Confirmed this run for the hard-outcome comparator table | DIRECT EVIDENCE (PCSK9i, not pitavastatin/ezetimibe) | SUPERIORITY | trials-efficacy |
| — | ODYSSEY OUTCOMES (alirocumab). *NEJM*. 2018 | DOI `10.1056/NEJMoa1801174` | Confirmed this run for the hard-outcome comparator table | DIRECT EVIDENCE (PCSK9i, not pitavastatin/ezetimibe) | SUPERIORITY | trials-efficacy |
| — | Inclisiran: VICTORION-2 Prevent (design paper), *Am Heart J*. 2026, DOI `10.1016/j.ahj.2026.107493`; ORION-4 (ISRCTN registry, 2018) | DOI as listed | **Confirmed gap this run (Q10):** no published hard-outcome results found, design/protocol papers only | LDL-C SURROGATE EFFICACY only; hard-outcome = INSUFFICIENT EVIDENCE | LDL-C SURROGATE EFFICACY | trials-efficacy |
| — | Li H, Li J 2026. *Br J Hosp Med*. (China retrospective cohort, pitavastatin 4mg vs atorvastatin 20mg, ≥60y, NODM 0% vs 10.29%, OR 0.212, p=0.018) | (as cited by safety-pharmacology) | Carried into synthesis this run for elderly-population positioning | OBSERVATIONAL EVIDENCE (single-center retrospective, non-randomized, non-equivalent doses) | OBSERVATIONAL SIGNAL | safety-pharmacology |
| — | AJBR 2024 candidate — "Optimizing LDL-C Reduction: High-Dose Pitavastatin Vs. Combination Therapy With Ezetimibe In Type II Diabetes" | DOI `10.53555/ajbr.v27i4s.7096` | **UNVERIFIED, not cited anywhere in synthesis** — title-only, HTTP 403 on abstract, Director's call (Q8) was to not chase further | INSUFFICIENT EVIDENCE | n/a — not cited | safety-pharmacology |
| — | T-101 §4.2.1.1 Statins Synopsis — East Asian pharmacogenetic caution (lines ~2015–2018) | (T-101, see above) | Independently re-verified by safety-pharmacology directly against the raw `.md` (not a relay) | GUIDELINE/CONSENSUS | GUIDELINE/CONSENSUS | safety-pharmacology |
| — | T-101 lines ~2011–2022 — PCSK9 mAb/inclisiran "well tolerated and safe," bempedoic acid statin-side-effect indication | (T-101, see above) | New this run; upgrades the tolerability/indication half of the PCSK9/inclisiran positioning claim from EXPERT INFERENCE to GUIDELINE/CONSENSUS (DDI-mechanism half stays EXPERT INFERENCE) | GUIDELINE/CONSENSUS (tolerability/indication only) | GUIDELINE/CONSENSUS | safety-pharmacology |
| — | Taiwan STS 2026 consensus — OA status | (same DOI as prior run, still not independently confirmed by number) | **New this run:** Unpaywall confirms genuine Gold OA/CC BY (resolves prior run's OA-badge discrepancy); full text remains Cloudflare-blocked regardless — content claim status unchanged, still BLOCKED_FOR_SOURCE | GUIDELINE/CONSENSUS (bibliographic only) — content claim INSUFFICIENT EVIDENCE | guideline recommendation (bibliographic), content unverified | guideline-risk |
| — | T-101 pages e1207–e1208 — "Recommendations for Secondary ASCVD Prevention," numbered recs #2/#3 (non-VHR, COR 2a B-R, ezetimibe/PCSK9 mAb/bempedoic acid genuinely equal) and #5/#6/#7 (VHR: ezetimibe and/or PCSK9 mAb COR 1 LOE A; bempedoic acid and inclisiran separately COR 2a LOE B-R, inclisiran further constrained to patients unable to tolerate/access PCSK9 mAb or preferring less-frequent dosing) | (T-101, see above) | **New this run (POST-FINAL-GATE correction, Decision 2026-09-01-17):** corrects an over-generalization that all VHR add-on options were equally graded. Director independently verified via PyMuPDF against the full text of both pages before correcting. | GUIDELINE/CONSENSUS | guideline recommendation | Director (correction routed to guideline-risk for its own evidence file) |

## Retracted this run — do not cite

- **K-924 "−51.4% vs −45.2%" cross-dose point-estimate comparison**, previously used as a "direct
  head-to-head, add-ezetimibe beats dose-doubling" claim. Confirmed never a prespecified/tested
  contrast (Decision 2026-09-01-06/-09). Use the matched-dose LS-difference figures (−11.9%/−12.7%)
  instead.
- **"non-HDL-C <100 mg/dL (2.4 mmol/L)" as the CONTROLLING value for the severe-hypercholesterolemia
  Tier 2 (HeFH/additional risk factors, no clinical ASCVD) recommendation** — do not use `2.4 mmol/L`
  as the value to cite. **CORRECTION (Decision 2026-09-01-14, post-Final-Gate):** this figure is
  genuinely printed in T-101 itself (page e1159, "Table 1. 2018 vs 2026" summary table) — it is
  **not** an extraction artifact, contrary to what an earlier version of this run's record (Decision
  2026-09-01-10) claimed. It coexists with a second, genuinely printed value at page e1199 (the
  authoritative numbered recommendation): `2.6 mmol/L`. This is a genuine source-internal printing
  inconsistency (most plausibly a typo in the summary table). **`2.6 mmol/L` controls** (matches the
  authoritative section and the document's convention everywhere else `<100 mg/dL` appears); `2.4
  mmol/L` is retained as an annotated source anomaly, not silently dropped. The LDL-C target itself
  (`<70 mg/dL` for Tier 2) is unambiguous and unaffected. See `00_executive-synthesis.md` §2.2 and
  `03_DECISION-LOG.md` Decision 2026-09-01-14 for the full corrected account, exact page numbers, and
  quotes.
- **"Consistent with Taiwan STS 2026"** as a guideline-attribution for any mechanistic/expert-
  inference argument. Taiwan STS's specific content claim remains `BLOCKED_FOR_SOURCE` — any such
  argument must be tagged `EXPERT INFERENCE`, not `GUIDELINE/CONSENSUS`.
- **"T-101 places ezetimibe, PCSK9 mAb, and bempedoic acid on equal COR/LOE footing" as a blanket
  claim covering both risk tiers.** **CORRECTION (Decision 2026-09-01-17, post-Final-Gate):** true
  only for the non-VHR tier (COR 2a, LOE B-R, all three). At the VHR tier, ezetimibe and PCSK9 mAb
  are COR 1/LOE A (no preference between those two specifically); bempedoic acid and inclisiran are
  separately COR 2a/LOE B-R, with inclisiran further explicitly constrained. Do not cite "no
  guideline preference among ezetimibe/PCSK9/bempedoic/inclisiran" for the VHR population — the
  correct, narrower claim is "no guideline preference for ezetimibe over PCSK9 mAb specifically."
