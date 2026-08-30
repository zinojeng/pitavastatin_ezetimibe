# Evidence Map — guideline-risk-intelligence (Wave 1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: guideline-risk-intelligence · Wave: 1 (Source/Evidence Verification)

Every claim below carries a mandatory Evidence Hierarchy tag per `CLAUDE.md` §7:
`DIRECT EVIDENCE | INDIRECT EVIDENCE | GUIDELINE / CONSENSUS | OBSERVATIONAL EVIDENCE |
MECHANISTIC SUPPORT | INSTITUTIONAL PRACTICE | EXPERT INTERPRETATION | INSUFFICIENT EVIDENCE`.

**Wave 1 scope note:** this is a source-identity/citation-existence map, not yet a full evidence
extraction. Numbers/wording below are drawn from (a) `Tonvasca_2026.md`'s own printed text (already
flagged unverified pending Wave 2 full-text cross-check against the primary document) or (b)
abstracts returned by verification searches. Full-text extraction and exact-wording confirmation
against primary PDFs is Wave 2 work — see `30_METHODS/guideline-risk/fulltext-manifest.md`.

## Search Protocol item 1 — Target-based therapy & 2025–2026 guideline landscape

**Claim (from `pitavastatin topic.md`):** 2026 ACC/AHA reintroduces absolute LDL-C/non-HDL-C
treatment goals, refined by PREVENT-ASCVD/CAC/Lp(a)/ApoB; very-high-risk secondary-prevention
LDL-C goal <55 mg/dL. ESC 2025 Focused Update supports in-hospital ACS lipid-lowering
intensification, including upfront high-intensity statin + ezetimibe when high-intensity monotherapy
alone is predicted insufficient.

- **Source located and citation-verified:** 2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA
  Guideline on the Management of Dyslipidemia (Blumenthal RS et al., JACC 2026;87(19):2624-2757,
  DOI `10.1016/j.jacc.2025.11.016`). — **GUIDELINE / CONSENSUS.** The specific numeric claims (the
  <55 mg/dL very-high-risk goal, and the exact PREVENT/CAC/Lp(a)/ApoB risk-refinement mechanics) are
  **not yet independently extracted from the primary document** by this role — Wave 1 confirms the
  document's identity/DOI only. Do not treat the <55 mg/dL figure as confirmed against the primary
  source until Wave 2 full-text extraction is done; it currently traces only to `pitavastatin
  topic.md` (PI notes, not a citable source per se) and to secondary commentary sources (see below).
- **Source located and citation-verified:** 2025 Focused Update of the 2019 ESC/EAS Guidelines for
  the management of dyslipidaemias (Mach F et al., Eur Heart J 2025, DOI `10.1093/eurheartj/ehaf190`;
  parallel Atherosclerosis publication DOI `10.1016/j.atherosclerosis.2025.120479`). —
  **GUIDELINE / CONSENSUS.** Same caveat: the specific "upfront high-intensity statin + ezetimibe at
  index hospitalization when high-intensity monotherapy alone is predicted insufficient" wording is
  from `pitavastatin topic.md`'s paraphrase, **not yet independently confirmed against the primary
  ESC document's exact text** — Wave 2 task.
- **Secondary/commentary sources found** (not primary guideline text, useful for Wave 2/3
  interpretation of the "goals" reframing, not yet verified in full): "The return of 'goals' in the
  2026 ACC/AHA/Multisociety guideline on the management of dyslipidemia" (J Clin Lipidol 2026, DOI
  `10.1016/j.jacl.2026.06.006`); "The 2026 ACC/AHA/Multisociety Guideline on the Management of
  Dyslipidemia—Best evidence and practices aligned" (J Clin Lipidol 2026, DOI
  `10.1016/j.jacl.2026.04.023`). — **EXPERT INTERPRETATION** (commentary on a guideline, not the
  guideline itself — do not cite these as if they were the ACC/AHA document's own wording).
- **Base guideline this update amends, also newly located this Wave:** 2019 ESC/EAS Guidelines for
  the management of dyslipidaemias (Mach F et al., Eur Heart J 2020;41(1):111-188, DOI
  `10.1093/eurheartj/ehz455`) — **GUIDELINE / CONSENSUS**, useful as the pre-2025-update baseline.

## Search Protocol item 2 — Taiwan STS (Suboptimally Tolerable Statins) 2026 consensus

**Claim (from `pitavastatin topic.md`):** the 2026 Taiwan Society of Lipid and Atherosclerosis
consensus distinguishes STS from formal statin intolerance; positions ezetimibe as first add-on for
high/very-high risk and early combination for extremely-high risk, before bempedoic acid/
PCSK9-targeting therapy.

- **Source located and citation-verified:** "2026 Taiwan society of lipids and atherosclerosis
  consensus statement for the identification and management of patients receiving suboptimally
  tolerable statins" (Wu YJ et al., J Formos Med Assoc 2026, DOI `10.1016/j.jfma.2026.04.111`, PMID
  42055832). — **GUIDELINE / CONSENSUS.** This is a **society consensus statement, not a
  hard-outcome trial** — per `CLAUDE.md` §7's explicit trap warning, any downstream synthesis must
  not cite this as CV-outcome evidence.
- **Abstract-level content directly cross-checked against the topic file's framing** (abstract text
  captured via Tavily extract of the publisher page, not yet full-text-verified against the complete
  PDF): the consensus's own abstract states a **tiered strategy that is more specific than the topic
  file's paraphrase** — extremely-high-risk patients: early combination of **ezetimibe AND
  bempedoic acid specifically** (not just "early combination" generically), escalating to
  PCSK9-inhibition-based agents if LDL-C <55 mg/dL is not achieved; high/very-high-risk: ezetimibe
  first-line add-on, then bempedoic acid, then PCSK9-targeted agents. The consensus explicitly
  integrates the 2025 Taiwan cholesterol management pathway (citation #27,
  `10.6314/JIMT.202412_35(6).04`). This refinement (naming bempedoic acid specifically in the
  extremely-high-risk tier) should be carried into `40_SYNTHESIS/` precisely — do not flatten it back
  to the topic file's more generic "early combination" phrasing.
- Evidence tag for the whole finding: **GUIDELINE / CONSENSUS**. It does **not** independently
  establish that pitavastatin/ezetimibe FDC specifically improves outcomes — it only establishes
  where ezetimibe-containing combinations sit in a Taiwan-specific treatment algorithm for patients
  who cannot sustain guideline-intensity statin monotherapy.

## Search Protocol item 10 — Residual risk incl. Lp(a) (guideline positioning)

**Claim (from `pitavastatin topic.md`):** 2026 ACC/AHA — screen Lp(a) once in adulthood, ≥50 mg/dL or
≥125 nmol/L as risk-enhancer; ESC 2025 — >50 mg/dL or >105 nmol/L; Taiwan Lp(a) consensus (2026)
exists.

- **Source located and citation-verified:** "2026 Consensus and review of Lipoprotein(a) from Taiwan
  Society of Lipid and Atherosclerosis: Molecular pathogenesis, epidemiology, clinical implications,
  and advances in diagnostic strategies" (Cheng CY et al., J Formos Med Assoc 2026, DOI
  `10.1016/j.jfma.2026.03.073`, PMID 41881723). — **GUIDELINE / CONSENSUS** for its consensus
  component; note per its own title this document is explicitly framed as *consensus and review*, so
  parts of it (molecular pathogenesis, epidemiology) are properly **EXPERT INTERPRETATION /
  MECHANISTIC SUPPORT** rather than formal practice recommendations — Wave 2 full-text read should
  separate the document's recommendation statements from its narrative-review content before any
  claim from it is tagged as GUIDELINE/CONSENSUS in `40_SYNTHESIS/`.
- The specific numeric thresholds (2026 ACC/AHA's ≥50 mg/dL/≥125 nmol/L; ESC 2025's >50 mg/dL/
  >105 nmol/L) are, at Wave 1, traceable only to `pitavastatin topic.md`'s own paraphrase, not yet
  independently confirmed against the primary ACC/AHA or ESC documents' exact wording — **flag as
  INSUFFICIENT EVIDENCE (not yet independently verified) until Wave 2 full-text extraction**,
  notwithstanding that both primary documents are now correctly identified and citation-verified
  (see item 1 above and `T-007`/#28 in the citation table). Also worth noting for Wave 2: the 2018
  AHA/ACC guideline (citations #17/#18, already in scope) already used a Lp(a) risk-enhancer
  threshold of ≥50 mg/dL or 125 nmol/L per its Executive Summary abstract text captured during this
  Wave's PubMed search — if the 2026 update repeats the identical threshold, that continuity itself
  is a citable point for Wave 2/3, not an error.

## Cross-cutting items verified but not yet assigned to a single Search Protocol item

- **2018 AHA/ACC Guideline on the Management of Blood Cholesterol** (Grundy SM et al., Circulation
  2019 — Executive Summary PMID 30565953 / full report PMID 30586774) — **GUIDELINE / CONSENSUS.**
  Foundational US guideline predating the 2026 update; useful in `40_SYNTHESIS/` as the historical
  baseline the 2026 ACC/AHA document supersedes/extends. Its Executive Summary abstract (captured in
  full during PubMed verification) already states the very-high-risk ASCVD LDL-C threshold of
  70 mg/dL for adding ezetimibe and the Lp(a) risk-enhancer threshold (≥50 mg/dL/125 nmol/L) — useful
  continuity anchor for the 2026 update's more aggressive <55 mg/dL goal.
- **2021 EAS Task Force statement on combination lipid-modifying therapy** (Averna M et al.,
  Atherosclerosis 2021;325:99-109) — **GUIDELINE / CONSENSUS** (a European Atherosclerosis Society
  Task Force practical-guidance statement, not a formal ESC/EAS joint guideline; distinguish from the
  2019/2025 ESC/EAS guideline documents in any downstream citation).
- **2023 Taiwan Society of Cardiology CCS guideline** (Ueng KC et al., Acta Cardiol Sin 2023;39(1):
  4-96) — **GUIDELINE / CONSENSUS.** Per `CLAUDE.md` §2.2, this is the source for the "upfront
  combination" recommendation in chronic coronary syndrome — content not yet extracted (Wave 2 task).
- **2022 Taiwan lipid guidelines, two companion documents** — Chen PS et al. (high-risk/secondary
  prevention: CAD, PAD, ischemic stroke; J Formos Med Assoc 2022;121(8):1363-1370) and Huang PH et
  al. (primary prevention; J Formos Med Assoc 2022;121(12):2393-2407) — both **GUIDELINE /
  CONSENSUS**, both citation-verified this Wave (the Huang PH one newly found in the previously
  unread remainder — see `citation-verification-table.md` §B).
- **ADA Standards of Care in Diabetes—2025, Ch. 10 Cardiovascular Disease and Risk Management**
  (Diabetes Care 2025;48(Suppl 1):S207-S238) — **GUIDELINE / CONSENSUS.** Search Protocol item 1's
  ADA-2025 lipid-target reference; content not yet extracted.
- **Polypharmacy epidemiology** (Halli-Tierney AD 2019 — US definition/framework; Meng LC 2023 —
  Taiwan/Japan cross-national prevalence data) — **OBSERVATIONAL EVIDENCE** (Meng LC; a cross-sectional
  claims-database study) and **EXPERT INTERPRETATION** (Halli-Tierney AD; an AFP clinical review, not
  primary data) respectively. Neither is guideline-level evidence — do not upgrade either to
  GUIDELINE/CONSENSUS in downstream synthesis. Meng LC's headline number as captured in its abstract:
  Taiwan 2019 polypharmacy (5–9 drugs) prevalence 35.4%, hyper-polypharmacy elsewhere defined
  ≥10 drugs — **this abstract-level figure has not been cross-checked against what `Tonvasca_2026.md`
  itself claims this source shows**; Wave 2 task for whichever role owns the specific slide claim.
- **FOURIER Asian subgroup** (Keech AC et al., Circ J 2021;85(11):2063-2070) — **DIRECT EVIDENCE**
  for evolocumab (a PCSK9 inhibitor) efficacy/safety in an Asian subpopulation of a large RCT — **but
  indirect/background evidence only** for this project's pitavastatin/ezetimibe question; this trial
  does not involve pitavastatin or ezetimibe. Use only for background risk-reduction-in-Asians
  context, never as if it were direct pitavastatin/ezetimibe trial evidence.
- **111 年健康促進統計年報 (Taiwan HPA 2022 statistical report)** — **INSTITUTIONAL PRACTICE /
  unverified government statistic** — not independently verified this Wave (see
  `unresolved-questions.md`).

## Known evidence-strength traps applicable to this Wave's findings (per `CLAUDE.md` §7)

- Taiwan STS 2026 and Taiwan Lp(a) 2026 are both **GUIDELINE/CONSENSUS**, not direct CV-outcome
  trial evidence — confirmed applicable to both newly located documents above.
- The 2026 ACC/AHA and 2025 ESC/EAS Focused Update are both **GUIDELINE/CONSENSUS** — their absolute
  LDL-C/Lp(a) thresholds are guideline recommendations, not newly generated trial results, and must
  not be presented as if they were primary RCT findings when they are synthesized statements over the
  underlying trial base.
