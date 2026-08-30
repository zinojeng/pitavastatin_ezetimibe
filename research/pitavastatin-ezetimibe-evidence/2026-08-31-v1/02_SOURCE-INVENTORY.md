# 02_SOURCE-INVENTORY — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

Answers: *what sources do we actually have, and what is their verification status?*
Wave 0 scope: catalog what already exists in the legacy inputs. **No new literature search has been
performed** — that is Wave 1/2 work, owned by the three specialists per `CLAUDE.md` §5.

Columns: `source_id` | filename/title | date | version | source type | relevance | verified? |
superseded? | notes

## LEGACY MANUSCRIPTS / SLIDES

| source_id | title | date | version | type | relevance | verified? | superseded? | notes |
|---|---|---|---|---|---|---|---|---|
| L-001 | `pitavastatin topic.md` | 2026-08-31 (file mtime) | v1 (only version) | PI topic/angle notes | Primary — defines the Search Protocol and framing (goal-directed therapy, STS, HIJ-PROPER phenotype angle, three-level evidence hierarchy) | N/A (primary PI input, not a citable literature source) | No | Root legacy file, read-only. See `CLAUDE.md` §1. |
| L-002 | `Tonvasca_2026.md` — "Optimizing Long-Term Lipid Control With Statin Combination Therapy" (Tonvasca® 同抑脂 slide deck source, 童綜合醫院 曾耀賢 醫師, dated 2026.09.02 in-file) | 2026-08-31 (file mtime); in-file date 2026.09.02 | v1 (only version) | Existing slide-deck source content (~2811 lines; markers `TRO-2026-001`/`TON-2026-004` suggest pharma-provided medical-affairs slide source) | Primary — contains ~30+ pre-assembled citations across polypharmacy epidemiology, DDI mechanisms, guideline recommendations (2025 Taiwan lipid pathway, 2026 ACC/AHA, 2023 TSC CCS, 2025 ADA), Phase III pitavastatin/ezetimibe FDC trial data, and a meta-analysis (Sydhom et al. 2024) on low/moderate-statin+ezetimibe vs high-intensity monotherapy | **Not yet verified** — every citation in this file is an unverified legacy claim until independently re-verified against PubMed/Crossref/publisher in Wave 1 (see `CLAUDE.md` §1) | No | Root legacy file, read-only. Only first ~1794 of ~2811 lines read in full during Wave 0 (file is large); remainder to be read by the owning specialist(s) in Wave 1 before verification work begins — do not assume Wave 0's partial read is a complete inventory of its citations. |
| L-003 | `Claude_Code_Cross-Session_Research_完整建議與經驗_Runbook.md` | 2026-08-31 (file mtime) | v1 (only version) | Cross-session research methodology (not clinical evidence) | Governance source only — not a clinical evidence source | N/A | No | Root legacy file, read-only. Durable copy at `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`. |

## CITATIONS EMBEDDED IN L-002 (`Tonvasca_2026.md`) — inventoried, not yet verified

The following distinct citations were identified during the Wave 0 partial read of L-002 (lines
1–1794 of ~2811). This is a **preliminary catalog for Wave 1 verification assignment**, not a
verified bibliography — do not cite any of these as confirmed until Wave 1 marks them verified.
Assigned owner = the specialist whose domain (CLAUDE.md §2) covers the claim.

| # | Citation (as printed in L-002) | Topic | Assigned owner (Wave 1) |
|---|---|---|---|
| 1 | Halli-Tierney AD, et al. Am Fam Physician. 2019;100(1):32-38. | Polypharmacy definition | guideline-risk |
| 2 | Meng LC, et al. Arch Gerontol Geriatr. 2023;115:105100. | Taiwan elderly polypharmacy prevalence | guideline-risk |
| 3 | Davies LE, et al. J Am Med Dir Assoc. 2020;21(2):181-187. | Polypharmacy adverse outcomes | safety-pharmacology |
| 4 | Borodo SB, et al. Bull Natl Res Cent. 2022;46:178. | Polypharmacy adverse outcomes | safety-pharmacology |
| 5 | Goldberg RM, et al. Am J Emerg Med. 1996;14(5):447-450. | ADE risk by drug count | safety-pharmacology |
| 6 | Rai GS, Rozario CJ. Anaesth Intensive Care Med. 2023;24:4. | DDI mechanisms overview | safety-pharmacology |
| 7 | Huang W, et al. Front Pharmacol. 2025;16:1618701. | DDI mechanisms overview | safety-pharmacology |
| 8 | Kellick KA, et al. J Clin Lipidol. 2014;8(3 Suppl):S30-S46. | Statin DDI (CCB, warfarin) | safety-pharmacology |
| 9 | Fravel MA, Ernst M. Curr Hypertens Rep. 2021;23(3):14. | Statin+CCB / statin+warfarin DDI | safety-pharmacology |
| 10 | May M, Schindler C. Ther Adv Endocrinol Metab. 2016;7(2):69-83. | DDI mechanisms | safety-pharmacology |
| 11 | Zanchi A, et al. Swiss Med Wkly. 2012;142:w13629. | DDI mechanisms | safety-pharmacology |
| 12 | Sica DA. J Clin Hypertens (Greenwich). 2004;6(10 Suppl 2):24-30. | DDI mechanisms | safety-pharmacology |
| 13 | Ehelepola NDB, et al. Case Rep Med. 2017;2017:8383251. | Statin+CCB rhabdomyolysis case | safety-pharmacology |
| 14 | Engell AE, et al. Br J Clin Pharmacol. 2021;87(2):694-699. | Statin+warfarin INR/bleeding | safety-pharmacology |
| 15 | Harężlak T, et al. Adv Ther. 2022;39(1):140-147. | ACEI/ARB+diuretic+NSAID AKI | safety-pharmacology |
| 16 | Casiglia E, Tikhonoff V. Hypertension. 2017;70(1):42-43. | Antidiabetic+β-blocker hypoglycemia masking | safety-pharmacology |
| 17 | Grundy SM, et al. Circulation. 2019;139(25):e1046-e1081. | 2018 ACC/AHA cholesterol guideline (part 1) | guideline-risk |
| 18 | Grundy SM, et al. Circulation. 2019;139(25):e1082-e1143. | 2018 ACC/AHA cholesterol guideline (part 2) | guideline-risk |
| 19 | Boekholdt SM, et al. J Am Coll Cardiol. 2014;64(5):485-494. | On-statin LDL-C vs CV event risk | trials-efficacy |
| 20 | Chiang CE, et al. J Atheroscler Thromb. 2016;23(5):567-587. | CEPHEUS study (LDL-C goal attainment) | trials-efficacy |
| 21 | Gitt AK, et al. Atherosclerosis. 2017;266:158-166. | DYSIS-II study | trials-efficacy |
| 22 | Yeh YT, et al. PLoS One. 2017;12(10):e0186861. | T-SPARCLE study (Taiwan) | trials-efficacy |
| 23 | Chien SC, et al. J Formos Med Assoc. 2019;118(10):1385-1392. | Statin discontinuation outcomes | safety-pharmacology |
| 24 | Keech AC, et al. Circ J. 2021;85(11):2063-2070. | FOURIER Asian subgroup baseline statin intensity | guideline-risk |
| 25 | Masana L, et al. Curr Cardiol Rep. 2020;22(8):66. | Combination LLT mechanism synergy | trials-efficacy |
| 26 | Sydhom P, et al. BMC Cardiovasc Disord. 2024;24(1):660. | Meta-analysis: low/mod-statin+eze vs HI-statin (lipids, clinical outcomes, safety, NODM) | trials-efficacy (efficacy/outcomes) + safety-pharmacology (NODM/AE) — joint |
| 27 | 李貽恒、石崇良. 內科學誌. 2024;35:426-430. (2025 台灣血脂管理臨床路徑共識; DOI 10.6314/JIMT.202412_35(6).04.04) | 2025 Taiwan lipid clinical pathway consensus | guideline-risk |
| 28 | Blumenthal RS, et al. J Am Coll Cardiol. Published online March 13, 2026. doi:10.1016/j.jacc.2025.11.016. | 2026 ACC/AHA guideline (PREVENT equations, primary/secondary prevention algorithms) | guideline-risk |
| 29 | Chen PS, et al. J Formos Med Assoc. 2022;121(8):1363-1370. | 2022 focused update, 2017 Taiwan lipid guideline (high-risk patients) | guideline-risk |
| 30 | Ueng KC, et al. Acta Cardiol Sin. 2023;39(1):4-96. | 2023 TSC chronic coronary syndrome guideline (upfront combination) | guideline-risk |
| 31 | Averna M, et al. Atherosclerosis. 2021;325:99-109. | 2021 EAS guideline (upfront combination) | guideline-risk |
| 32 | American Diabetes Association Professional Practice Committee. Diabetes Care. 2025;48(1 Suppl 1):S207-S238. | 2025 ADA lipid targets for DM | guideline-risk |
| 33 | Chou MT, et al. Clin Ther. 2022;44(10):1272-1281 (also cited as S0149-2918(22)00286-7). | Phase III pitavastatin/ezetimibe FDC trial (Taiwan/Australia/NZ) | trials-efficacy |

**Not yet reached in the Wave 0 partial read** (lines 1795–2811 of L-002, ~36% of the file) — likely
to contain further AE/safety detail for the Phase III FDC trial and possibly additional sections;
must be read in full by trials-efficacy-intelligence and/or safety-pharmacology-intelligence at the
start of Wave 1, and any citations found there added to this table.

## RCTs / META-ANALYSES / SYSTEMATIC REVIEWS — named in `pitavastatin topic.md` but not yet located

These are named directly in the PI's topic notes (L-001) and are **Wave 1 priority acquisition
targets** for trials-efficacy-intelligence; no source has been located or verified for them yet.

| source_id | title (as referenced) | relevance | verified? | notes |
|---|---|---|---|---|
| T-001 | HIJ-PROPER (pitavastatin+ezetimibe vs pitavastatin alone, ACS hard-outcome trial) | Level 3 evidence anchor; sitosterol/absorber-phenotype subgroup | Not yet located | Primary-outcome figures already quoted in L-001 (32.8% vs 36.9%, HR 0.89, 95% CI 0.76–1.04, P=0.152; phenotype subgroup HR 0.71) — these are **PI-supplied figures in the topic notes, not yet independently verified against the primary publication**. |
| T-002 | RACING trial (rosuvastatin+ezetimibe vs high-intensity statin, incl. DM subgroup) | Level 2 evidence; strategy-question trial | Not yet located | Figures quoted in L-001 (3-yr MACE 9.1% vs 9.9%; DM subgroup MACE 10.0% vs 11.3%; intolerance-related discontinuation 4.8% vs 8.2% overall, 5.2% vs 8.7% in DM subgroup) — likewise unverified PI-supplied figures. |
| T-003 | 2024 systematic review/meta-analysis, pitavastatin NODM risk vs atorvastatin/rosuvastatin | Search Protocol item 3 (glycemic outcomes) | Not yet located | Referenced generically in L-001 ("2024 systematic review/meta-analysis 納入 RCT 與 observational studies"); specific citation not given — Wave 1 task to identify. |
| T-004 | 2 mg vs 4 mg dose-comparison studies (incl. add-ezetimibe vs dose-escalation) | Search Protocol item 5 | Not yet located | No specific citation given in L-001; Wave 1/2 literature search target. |
| T-005 | Taiwan STS (Suboptimally Tolerable Statins) 2026 consensus, Taiwan Society of Lipid and Atherosclerosis | Search Protocol item 2 | Not yet located | Named in L-001 without a formal citation; likely very recent (2026) — Wave 1 task to locate the primary publication. |
| T-006 | Taiwan Lp(a) consensus (2026) | Search Protocol item 10 | Not yet located | Named in L-001 without a formal citation; Wave 1 task. |
| T-007 | ESC 2025 Focused Update (in-hospital ACS lipid-lowering intensification) | Search Protocol item 1 | Not yet located | Named in L-001 without a formal citation; Wave 1 task. |

## GUIDELINES — status summary

All guideline sources needed for Search Protocol item 1 (2026 ACC/AHA, ESC 2025 Focused Update) and
item 2 (Taiwan STS 2026) are either only partially cited (2026 ACC/AHA — see #28 above, verified
citation string exists but primary document not yet fetched) or not yet located (ESC 2025, Taiwan
STS 2026, Taiwan Lp(a) 2026). This is expected at Wave 0 — see `04_OPEN-QUESTIONS.md`.

## SUPPLEMENTARY FILES / TABLES / SLIDES

None beyond L-002 identified as of Wave 0.

## PRIMARY DATA / NEW ANALYSIS / OLD ANALYSIS

Not applicable — this project is a literature/evidence review, not an original-data analysis
(Runbook §2.1 type B, not type A).

---

*This table is additive across Waves — new rows get appended as sources are found; existing rows'
`verified?`/`superseded?` columns get updated in place with a pointer to the `03_DECISION-LOG.md`
entry that changed them. Never delete a row; mark it `superseded?` instead.*
