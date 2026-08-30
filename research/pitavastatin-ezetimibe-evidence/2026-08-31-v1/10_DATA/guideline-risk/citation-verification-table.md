# Citation Verification Table — guideline-risk-intelligence (Wave 1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: guideline-risk-intelligence · Wave: 1 (Source/Evidence Verification)

Scope: every citation in `02_SOURCE-INVENTORY.md`'s "CITATIONS EMBEDDED IN L-002" table assigned to
`guideline-risk`, plus new citations found while reading the previously-unread remainder of
`Tonvasca_2026.md` (lines 1795–2811), plus the Search Protocol's named-but-unlocated guideline
targets (T-005, T-006, T-007). Per the Numeric Integrity Rule (CLAUDE.md §9), every printed value is
reproduced exactly as it appears in `Tonvasca_2026.md`; nothing is silently corrected.

Verification method: DOI resolution (Crossref `get_crossref_paper_by_doi` / `search_crossref`),
PubMed/Europe PMC record match (`search_pubmed`, `search_europepmc`), and — for two items —
`research_hub` (openalex/crossref aggregation). No Sci-Hub tool was invoked (CLAUDE.md §10; see
`unresolved-questions.md` for a compliance note about `research_hub`'s `download_paper`).

## A. Citations assigned to guideline-risk in 02_SOURCE-INVENTORY.md

| # | As printed in `Tonvasca_2026.md` (SOURCE_VALUE, verbatim) | Verification result | Matched record | Confidence |
|---|---|---|---|---|
| 1 | Halli-Tierney AD, et al. Am Fam Physician. 2019;100(1):32-38. | **VERIFIED** — title "Polypharmacy: Evaluating Risks and Deprescribing," authors Halli-Tierney AD, Scarbrough C, Carroll D; journal/year match. Volume/issue/page string not independently re-returned by the API (PubMed record gave no page field) but author/title/journal/year match is unambiguous. | PMID 31259501 | HIGH |
| 2 | Meng LC, et al. Arch Gerontol Geriatr. 2023;115:105100. | **VERIFIED — exact.** Title "Medication overload: A closer look at polypharmacy and potentially inappropriate medications among older people in Taiwan and Japan." DOI `10.1016/j.archger.2023.105100` — volume 115, article/page 105100, year 2023 all match exactly. | PMID 37499332, DOI 10.1016/j.archger.2023.105100 | HIGH |
| 17 | Grundy SM, et al. Circulation. 2019;139(25):e1046-e1081. | **VERIFIED** — this is the 2018 AHA/ACC blood-cholesterol guideline **Executive Summary**. Title/author list/journal/year match (Circulation 2019;139(25), consistent with the printed volume/issue). Exact page string (e1046-e1081) not independently re-confirmed via API (no page field returned) but is the well-documented citation for this Executive Summary. | PMID 30565953, DOI 10.1161/CIR.0000000000000624 | HIGH |
| 18 | Grundy SM, et al. Circulation. 2019;139(25):e1082-e1143. | **VERIFIED** — this is the 2018 AHA/ACC blood-cholesterol guideline **full-text report** (companion to #17, same author list, same issue). Journal/year/issue match; page string (e1082-e1143) not independently re-confirmed via API. | PMID 30586774, DOI 10.1161/CIR.0000000000000625 | HIGH |
| 24 | Keech AC, et al. Circ J. 2021;85(11):2063-2070. | **VERIFIED** — title "Efficacy and Safety of Long-Term Evolocumab Use Among Asian Subjects - A Subgroup Analysis of ... FOURIER Trial," journal Circ J, year 2021 match. Volume/issue/page (85(11):2063-2070) not independently re-confirmed via API (no page field returned). | PMID 33980763, DOI 10.1253/circj.CJ-20-1051 | HIGH |
| 27 | 李貽恒、石崇良. 內科學誌. 2024;35:426-430. (2025 台灣血脂管理臨床路徑共識; DOI 10.6314/JIMT.202412_35(6).04.04) | **VERIFIED with a DOI discrepancy — FLAG = POSSIBLE_ERROR.** Article located: 李貽恒, 石崇良, "2025台灣血脂管理臨床路徑共識" (2025 Consensus on Clinical Pathway of Blood Cholesterol Management in Taiwan), 內科學誌 (J Intern Med Taiwan) 2024;35(6):426-430. The **correct DOI per the publisher/journal (TSIM) is `10.6314/JIMT.202412_35(6).04`** (single `.04` suffix) — the source printed `10.6314/JIMT.202412_35(6).04.04` (duplicated `.04`). SOURCE_VALUE (as printed) = `10.6314/JIMT.202412_35(6).04.04`; independently located correct DOI = `10.6314/JIMT.202412_35(6).04`. Title, authors, journal, volume, issue, and page range all otherwise match. ACTION = NEEDS_ANALYST/NEEDS_PI per Numeric Integrity Rule — do not silently correct in any downstream file; Director to log in `03_DECISION-LOG.md`. | Located via WebSearch (TSIM/Airiti listings); DOI not independently Crossref-resolvable (Taiwan journal, not Crossref-indexed) | MODERATE (title/journal/pages high confidence; DOI string is the flagged discrepancy) |
| 28 | Blumenthal RS, et al. J Am Coll Cardiol. Published online March 13, 2026. doi:10.1016/j.jacc.2025.11.016. | **VERIFIED — DOI exact match.** Title "2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the Management of Dyslipidemia." Crossref record: JACC vol 87, issue 19, pages 2624–2757, Crossref `published_date` = 2026-05-01. **Note (not corrected):** the source's "Published online March 13, 2026" is an epub-ahead-of-print date; Crossref's registered `published_date` here is the print-issue date (2026-05-01) — these commonly differ for AHA/ACC guidelines and this is not treated as an error, just an unreconciled date type, logged for completeness. **Also found:** a parallel Circulation-side DOI for the same dual-published guideline, `10.1161/cir.0000000000001423` (via `research_hub`/openalex) — not yet independently Crossref-verified; record as an additional citable co-publication, not a substitute. | DOI 10.1016/j.jacc.2025.11.016 (Crossref-confirmed); companion DOI 10.1161/cir.0000000000001423 (openalex, unconfirmed via Crossref) | HIGH (JACC DOI); MODERATE (Circulation companion DOI) |
| 29 | Chen PS, et al. J Formos Med Assoc. 2022;121(8):1363-1370. | **VERIFIED — exact.** Title "2022 focused update of the 2017 Taiwan lipid guidelines for high risk patients: Coronary artery disease, peripheral artery disease and ischemic stroke." Authors: Po-Sheng Chen, Meng Lee, Sung-Chun Tang, Po-Hsun Huang, Hung-I Yeh, Charles Jia-Yin Hou, I-Chang Hsieh, Jiunn-Tay Lee, Jiann-Shing Jeng, Yi-Heng Li. Crossref: J Formos Med Assoc, vol 121, issue 8, pages 1363-1370 — matches printed citation exactly. | PMID 35410823, DOI 10.1016/j.jfma.2022.03.001 | HIGH |
| 30 | Ueng KC, et al. Acta Cardiol Sin. 2023;39(1):4-96. | **VERIFIED.** Title "2023 Guidelines of the Taiwan Society of Cardiology on the Diagnosis and Management of Chronic Coronary Syndrome." Acta Cardiologica Sinica, volume 39, issue 1, January 2023, pages 4-96 — matches printed citation. | PMID 36685161 | HIGH |
| 31 | Averna M, et al. Atherosclerosis. 2021;325:99-109. | **VERIFIED — exact.** Title "Practical guidance for combination lipid-modifying therapy in high- and very-high-risk patients: A statement from a European Atherosclerosis Society Task Force." Crossref: Atherosclerosis, vol 325, pages 99-109, published 2021-05-01 — matches printed citation exactly. | DOI 10.1016/j.atherosclerosis.2021.03.039 | HIGH |
| 32 | American Diabetes Association Professional Practice Committee. Diabetes Care. 2025;48(1 Suppl 1):S207-S238. | **VERIFIED — exact.** Title "10. Cardiovascular Disease and Risk Management: Standards of Care in Diabetes—2025." Crossref: Diabetes Care, volume 48, issue Supplement_1, pages S207-S238 — matches printed citation exactly ("(1 Suppl 1)" in source = Crossref's "Supplement_1"). | DOI 10.2337/dc25-s010 | HIGH |

## B. New citations found in the previously-unread remainder (`Tonvasca_2026.md` lines 1795–2811) relevant to guideline-risk domain

Per `04_OPEN-QUESTIONS.md`'s NEEDS_ANALYST item and Decision 2026-08-31-02, the unread remainder has
now been read in full by this role. Two guideline-relevant citations were found in the footnote list
at line 2803 (numbered 6 and 7 in that footnote block) that were **not previously catalogued** in
`02_SOURCE-INVENTORY.md`:

| Citation (as printed, footnote # in L-002's final slide) | Verification result | Matched record |
|---|---|---|
| 6. Mach F, et al. Eur Heart J. 2020;41(1):111-188. | **VERIFIED — exact.** "2019 ESC/EAS Guidelines for the management of dyslipidaemias: lipid modification to reduce cardiovascular risk." Eur Heart J 2020;41(1):111-188 — matches exactly. This is the **base 2019 ESC/EAS guideline** that the 2025 Focused Update (item C below) amends. | PMID 31504418, DOI 10.1093/eurheartj/ehz455 |
| 7. Huang PH, et al. J Formos Med Assoc. 2022;S0929-6646(22)00215-7. | **VERIFIED and disambiguated.** The pii string resolves to a **distinct companion guideline** to citation #29 above (same Taiwan lipid-guideline update wave, different scope): "2022 Taiwan lipid guidelines for primary prevention," Po-Hsun Huang (lead author) et al., J Formos Med Assoc 2022;121(12):2393-2407. This is **not** a duplicate of #29 (Chen PS et al., the *high-risk/secondary-prevention* focused update) — the two are sister publications: #29 covers ASCVD/high-risk patients, this one covers primary prevention. Flagging this disambiguation explicitly since both share heavily overlapping author lists (Huang PH, Yeh HI, Li YH appear on both). | DOI 10.1016/j.jfma.2022.05.010 |

Also present in the remainder but **not guideline-risk domain** (noted here only as a pointer for the
Director to route to the correct owner; not verified by this role): Saito Y 2009 (ADR incidence,
safety-pharmacology), Corsini A 2011 (metabolism/DDI, safety-pharmacology), Lin YW 2024 / Su M 2025 /
van Driel ML 2016 / Religioni U 2025 (adherence epidemiology — domain ambiguous between
guideline-risk and safety-pharmacology; not claimed by this role), Wei Q 2023 / Katzmann JL 2022
(FDC efficacy/adherence — trials-efficacy domain), "111 年健康促進統計年報" (Taiwan Health Promotion
Administration statistical annual report — government/institutional statistics source, not an
indexed academic citation; flagged separately below), and a patent-embedded citation (Min Yu et al.,
Lipids Health Dis 2020;19:1 — trials-efficacy domain, ezetimibe+statin vs double-dose statin
meta-analysis, found inside the US patent text, not the slide body itself).

**"111 年健康促進統計年報"** (Republic-of-China year 111 = 2022, Taiwan Health Promotion
Administration statistical annual report) — cited for national hypertension/hyperglycemia/
hyperlipidemia prevalence (63%/28%/40% in elderly). This is a government statistical report, not
academic literature; not resolvable via PubMed/Crossref/paper-search. **INSTITUTIONAL PRACTICE /
GUIDELINE-CONSENSUS-adjacent primary statistic** — would need direct retrieval from the Health
Promotion Administration (國民健康署) website to verify the exact figures. Logged as
`NEEDS_SOURCE` in `unresolved-questions.md`.

## C. Search Protocol targets located (previously "Not yet located" in 02_SOURCE-INVENTORY.md)

| Target ID | Search Protocol item | Result | Citation |
|---|---|---|---|
| T-007 | Item 1 — ESC 2025 Focused Update (in-hospital ACS lipid-lowering intensification) | **LOCATED.** "2025 Focused Update of the 2019 ESC/EAS Guidelines for the management of dyslipidaemias." Mach F, Koskinas KC, Roeters van Lennep JE, Tokgözoğlu L, Badimon L, Baigent C, Benn M, Binder CJ, Catapano AL, De Backer GG, Delgado V, Fabin N, Ference BA, Graham IM, Landmesser U, Laufs U, Mihaylova B, Nordestgaard BG, Richter DJ, Sabatine MS. **Dual-published**: Eur Heart J (PMID 40878289, DOI `10.1093/eurheartj/ehaf190`) and Atherosclerosis (PMID 40885687, DOI `10.1016/j.atherosclerosis.2025.120479`); an Italian-language translation also exists (PMID 41143316). Full-text ACS in-hospital intensification wording **not yet extracted** — that is a Wave 2 evidence-extraction task; Wave 1 confirms only that the document exists and is correctly identified. | PMID 40878289 / DOI 10.1093/eurheartj/ehaf190 |
| T-005 | Item 2 — Taiwan STS (Suboptimally Tolerable Statins) 2026 consensus | **LOCATED.** "2026 Taiwan society of lipids and atherosclerosis consensus statement for the identification and management of patients receiving suboptimally tolerable statins." Wu YJ, Yeh CF, Hsu CY, Lin CF, Huang CC, Tang SC, Huang YC, Lin CY, Yu CH, Huang CY, Wang CY, Huang PH, Yeh HI, Li YH, Liu PY. J Formos Med Assoc, 2026. Open access, CC-licensed (confirmed via publisher page — see `fulltext-manifest.md`). Abstract confirms the topic file's framing almost verbatim: tiered strategy — extremely-high-risk → early combination ezetimibe + bempedoic acid, escalate to PCSK9 if LDL-C <55 mg/dL not met; high/very-high-risk → ezetimibe first-line add-on, then bempedoic acid, then PCSK9; integrates the 2025 Taiwan cholesterol pathway (citation #27 above). | PMID 42055832, DOI 10.1016/j.jfma.2026.04.111 |
| T-006 | Item 10 — Taiwan Lp(a) 2026 consensus | **LOCATED.** "2026 Consensus and review of Lipoprotein(a) from Taiwan Society of Lipid and Atherosclerosis: Molecular pathogenesis, epidemiology, clinical implications, and advances in diagnostic strategies." Cheng CY, Wu YJ, Yeh CF, Huang PH, Hsu CY, Lin TH, Wang YC, Wang CY, Wang CY, Huang YC, Shyu KG, Hsieh IC, Yang KC, Wu YW, Lin WW, Lin CF, Chen PS, Tsai IH, Pan WH, Lu TM, Kuo SE, Sheu WH, Leu HB, Huang CY, Huang CC, Lee JK, Tang SC, Liu PY. J Formos Med Assoc, 2026. **Note:** this is framed as a *review + consensus*, not a pure clinical-practice-recommendation consensus — worth precise handling when tagging Evidence Hierarchy (see `evidence-map.md`). | PMID 41881723, DOI 10.1016/j.jfma.2026.03.073 |

Also confirmed via `research_hub` (openalex/crossref), not yet independently Crossref-verified by this
role, two **secondary/commentary** sources directly useful for the "treat the statin dose vs treat
the LDL target" framing (Search Protocol item 1) — flagged for Wave 2, not cited as primary evidence
yet:
- "The return of 'goals' in the 2026 ACC/AHA/Multisociety guideline on the management of
  dyslipidemia," J Clin Lipidol 2026, DOI `10.1016/j.jacl.2026.06.006`.
- "The 2026 ACC/AHA/Multisociety Guideline on the Management of Dyslipidemia—Best evidence and
  practices aligned," J Clin Lipidol 2026, DOI `10.1016/j.jacl.2026.04.023`.

## Summary counts

- Assigned citations verified: **11/11** (9 exact/high-confidence matches; 1 with a flagged DOI
  transcription discrepancy [#27]; 1 with a flagged epub-vs-print date note [#28], not an error).
- New citations found in the previously-unread remainder and resolved: **2** (Mach F 2019 ESC/EAS
  base guideline; Huang PH 2022 Taiwan primary-prevention companion guideline).
- Search Protocol guideline targets located this Wave: **3/3** (T-005 Taiwan STS 2026, T-006 Taiwan
  Lp(a) 2026, T-007 ESC 2025 Focused Update) — all previously "Not yet located" in
  `02_SOURCE-INVENTORY.md`.
- Numeric Integrity flags requiring Director/PI action: **1** (citation #27 DOI discrepancy).
