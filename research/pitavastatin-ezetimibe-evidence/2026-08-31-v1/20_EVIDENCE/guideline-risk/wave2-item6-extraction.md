# Wave 2, item 6 — Numeric-threshold / combination-therapy full-text extraction

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: guideline-risk-intelligence · Wave: 2 continuation (item 6 of the Director's assignment, plus
a substantive advance on item 4 via an alternate lawful route)

**Method note:** after items 1–2 (2026 ACC/AHA, ESC 2025 Focused Update, Taiwan STS 2026) were
confirmed `BLOCKED_FOR_SOURCE` via Cloudflare-walled publisher sites (see
`wave2-fulltext-extraction.md`), I checked PMC linkage for the remaining item-6 targets using NCBI's
public `elink` API (`dbfrom=pubmed&db=pmc&linkname=pubmed_pmc` — the "this article has its own PMC
copy" link type, distinct from the much larger "cited-by" link list) before attempting any download.
This is a fast, free, lawful way to know *in advance* whether a document has an OA PMC copy, rather
than guessing and hitting more Cloudflare walls. Three of five item-6 targets had a genuine PMC copy;
two did not.

## Result matrix

| Document | PMC copy found? | Outcome |
|---|---|---|
| 2023 TSC CCS guideline (Ueng KC et al., Acta Cardiol Sin 2023;39(1):4-96) | **Yes — PMC9829849** | **Obtained, parsed, extracted (below)** |
| ADA Standards of Care 2025, Ch.10 (citation #32) | **Yes — PMC11635050** | **Obtained, parsed, extracted (below)** |
| Katzmann JL, Laufs U. "Choosing the Right Non-Statin Therapy..." Curr Atheroscler Rep 2026 (secondary review citing the 2025 ESC/EAS Focused Update) | **Yes — PMC12945982** (found via a targeted search for reviews of the ESC 2025 update, not originally on the Director's list — see below) | **Obtained, parsed, extracted (below)** |
| Taiwan Lp(a) 2026 consensus/review (T-006, PMID 41881723) | No (`elink` returned no `pubmed_pmc` entry) | Still `BLOCKED_FOR_SOURCE` |
| 2019 ESC/EAS base guideline (#34, PMID 31504418) | No (`elink` returned no `pubmed_pmc` entry) | Still `BLOCKED_FOR_SOURCE` |
| 2022 Taiwan primary-prevention guideline (#35) | No PMC copy (`elink` confirmed empty, PMID 35715290) — **but found on the Taiwan Society's own direct-hosted mirror** (`tas.org.tw`, no Cloudflare wall) | **Obtained, parsed, extracted (below, section D)** |

## A. 2023 TSC CCS guideline — exact recommendation text (PRIMARY SOURCE, DIRECT extraction)

Source: `20_EVIDENCE/guideline-risk/fulltext/Ueng_2023_TSC-CCS-guideline.pdf` (gitignored).
SHA-256 (PDF): `98b559d4a4b053742d348041b2764d4df21df42157f4552e95fcba05eeb2af32`.
Retrieved via `https://europepmc.org/articles/PMC9829849?pdf=render`, 2026-08-30 (UTC), HTTP 200,
`application/pdf`, 93 pages — matches the citation's own printed page range (4-96). Parsed cleanly
with `mcp__llamaparse__parse_pdf_to_markdown`; parsed markdown SHA-256:
`40238efd70208358807a0b2526fbae6a91ce82f93e7ba64fa364ef21bb2a4dcc`.

**Evidence Hierarchy tag: GUIDELINE / CONSENSUS.** All text below is copied verbatim from the parsed
PDF (Numeric Integrity Rule — nothing paraphrased or corrected), with the guideline's own
Class-of-Recommendation (COR) / Level-of-Evidence (LOE) tags preserved exactly as printed:

> "Moderate-intensity statin plus ezetimibe can be used as the first-line treatment, especially if
> patient's general condition is not suitable for or cannot tolerate high-intensity statin." — **COR
> IIa, LOE B**
>
> "PCSK9 inhibitor is considered if LDL-C target is not achieved after combination therapy of
> high-intensity statin and ezetimibe, or statin intolerance occurs." — **COR I, LOE B**
>
> "Earlier initiation of PCSK9 inhibitor should be considered if LDL-C target is not achieved after
> statin plus ezetimibe therapy in CCS patients with extreme risk conditions." — **COR IIa, LOE B**
>
> "In extreme risk CCS patients, upfront combination treatment of high intensity statins first with
> ezetimibe and then a PCSK9 inhibitor to achieve the target < 50 mg/dl should be considered." —
> **COR IIa, LOE A**

**This directly and independently confirms CLAUDE.md §2.2's characterization** of the 2023 TSC CCS
guideline as containing an "upfront-combination recommendation" — now verified against the guideline's
actual text with its formal recommendation grading, not merely inferred from a secondary description.

**Exact LDL-C target numbers (verbatim, do not round or convert):**

> "In general, the LDL-C target is < 70 mg/dl in CCS all patients. In particular, new LDL-C target
> < 50 mg/dl is recommended for CCS patients at extreme risk, defined as clinical settings with a
> history of recent ACS, multiple prior MIs, MVD, post-ACS plus diabetes, or polyvascular disease
> with concomitant PAD."

**Important — do not conflate this with the ACC/AHA <55 mg/dL figure elsewhere in this project.**
The Taiwan TSC CCS extreme-risk target is explicitly **< 50 mg/dl**, a different number from the
2026 ACC/AHA very-high-risk secondary-prevention goal of <55 mg/dL referenced in `pitavastatin
topic.md` and the ADA 2025 goal of <55 mg/dL (section B below) — three distinct guideline bodies,
three (two identical, one different) numbers, for overlapping but not identical risk populations.
Keep these separate in `40_SYNTHESIS/`.

**LDL-C-lowering efficacy table (guideline's own summary, sourced from the underlying RCT base —
tag GUIDELINE/CONSENSUS for the recommendation context, but the % figures themselves trace to trial
evidence the guideline is summarizing, not new guideline-generated data):**

| Regimen (as printed) | LDL-C reduction (as printed) |
|---|---|
| Ezetimibe | ≈ 15-20% |
| High-intensity statin plus ezetimibe | ≈ 65% |
| PCSK9 inhibitor plus high-intensity statin plus ezetimibe | ≈ 85% |

**Rationale text worth preserving for `40_SYNTHESIS/`'s "treat the dose vs treat the target" framing
(Search Protocol item 1):**

> "Current international guidelines still recommend using high-intensity statin monotherapy before
> considering combination therapy. Based on the rule of 'the earlier, the better', upfront
> combination therapy should be the new standard of care to achieve the LDL-C target..."

This is the TSC CCS guideline **explicitly contrasting itself against** the more conservative
international norm — useful, citable framing for exactly the reorientation question
`pitavastatin topic.md` raises, sourced now to the primary Taiwan document itself.

## B. ADA Standards of Care 2025, Ch.10 — exact recommendation text (PRIMARY SOURCE, confirms citation #32)

Source: `20_EVIDENCE/guideline-risk/fulltext/ElSayed_2025_ADA-Ch10-CVD-RiskMgmt.pdf` (gitignored).
SHA-256 (PDF): `2433e54080c3415ab7966c7eddd78c4810356b9aa662b627bd6e27608f512bba`. Retrieved via
`https://europepmc.org/articles/PMC11635050?pdf=render`, 2026-08-30 (UTC), HTTP 200,
`application/pdf`. Parsed markdown SHA-256:
`2345f369ce2e2612e9eb7c37940929d99bb1ec710de767196ebf7af40dc63155`.

**Evidence Hierarchy tag: GUIDELINE / CONSENSUS.** Verbatim excerpts, ADA's own numbered
recommendations preserved exactly:

> "**10.22** For people with diabetes aged 40–75 years at higher cardiovascular risk, especially
> those with multiple additional ASCVD risk factors and an LDL cholesterol ≥70 mg/dL
> (≥1.8 mmol/L), it may be reasonable to add ezetimibe or a PCSK9 inhibitor to maximum tolerated
> statin therapy. **B**"
>
> "**10.28** For people with diabetes and ASCVD, treatment with high-intensity statin therapy is
> recommended to obtain an LDL cholesterol reduction of ≥50% from baseline and an LDL cholesterol
> goal of <55 mg/dL (<1.4 mmol/L). Addition of ezetimibe or a PCSK9 inhibitor with proven benefit in
> this population is recommended if this goal is not achieved on maximum tolerated statin therapy.
> **B**"
>
> "**10.33** Statin plus fibrate combination therapy has not been shown to improve ASCVD outcomes and
> is generally not recommended. **A**"
>
> "**10.34** Statin plus niacin combination therapy has not been shown to provide additional
> cardiovascular benefit above statin therapy alone, may increase the risk of stroke with additional
> side effects, and is generally not recommended. **A**"

This **fully confirms** citation #32's content (Wave 1 had only citation-verified the DOI/journal/
pages; this Wave now confirms the actual recommendation text). Note ADA's <55 mg/dL secondary-
prevention-with-diabetes goal happens to numerically match the 2026 ACC/AHA figure cited in the topic
file, but these are two **separate, independent** guideline statements (ADA's own Grade B
recommendation vs. the not-yet-directly-verified ACC/AHA figure) — cite them separately, do not treat
one as confirming the other's exact wording.

## C. Katzmann & Laufs 2026 review — secondary corroboration of the (still-blocked) ESC 2025 Focused Update

Source: `20_EVIDENCE/guideline-risk/fulltext/Katzmann_Laufs_2026_CurrAtherosclerRep_sequencing.pdf`
(gitignored). Full citation: Katzmann JL, Laufs U. "Choosing the Right Non-Statin Therapy for the
Right Patient - How To Sequence Advanced Lipid-Lowering Therapies." *Curr Atheroscler Rep* 2026.
DOI `10.1007/s11883-026-01390-7`, PMID 41746457, PMCID PMC12945982. Open access. SHA-256 (PDF):
`209b99f99496fbe484f68d2be94c79c92a012c14b380d8a6e7a0fc35b4253e76`. Retrieved via
`https://europepmc.org/articles/PMC12945982?pdf=render`, 2026-08-30 (UTC), HTTP 200.

**Evidence Hierarchy tag: EXPERT INTERPRETATION** (this is a review/commentary, not the guideline
itself — it cites the actual 2025 ESC/EAS Focused Update as its own reference [1], which remains
`BLOCKED_FOR_SOURCE` for direct verification). Treat everything below as **secondary paraphrase with
citation attribution to the primary document**, not as independently confirmed primary-guideline
wording — flagged exactly this way, not silently upgraded.

> "The recently updated ESC/EAS guidelines on the management of dyslipidemias incorporate important
> novel recommendations on early combination lipid-lowering treatment after acute coronary syndrome
> (ACS) and the management of rare dyslipidemias [1, 2]."
>
> "...the 2025 update of the ESC/EAS dyslipidemia guidelines now endorses a concept of **upfront
> combination lipid-lowering therapy with a statin and ezetimibe in treatment-naïve patients with
> ACS, in whom target achievement with statin monotherapy, based on the expected LDL-C reduction, is
> unlikely**. Furthermore, patients hospitalized with ACS who were already on lipid-lowering
> treatment should undergo intensification of treatment to further lower LDL-C [1]."
>
> "The LDL-C treatment targets remained unchanged in the 2025 update of the ESC/EAS dyslipidemia
> guidelines: for patients at very-high or extreme risk, LDL-C targets of < 1.4 mmol/L and
> < 1.0 mmol/L, respectively, are recommended [1]." (≈ <55 mg/dL and <39 mg/dL if converted — **not
> converting here**, printed exactly as the source states it, in mmol/L; unit conversion, if wanted
> downstream, should be a separate, explicitly-labeled step, not silently folded into the quote.)
>
> "...bempedoic acid is recommended as additional treatment to statins and ezetimibe if the LDL-C
> target is not attained (level of evidence: C) [1]."

**This is the closest available lawful substitute for the still-blocked ESC 2025 Focused Update
itself**, and its substance — upfront statin+ezetimibe combination in treatment-naïve ACS patients
predicted unlikely to reach target on monotherapy — **matches `pitavastatin topic.md`'s own
paraphrase of the ESC 2025 update almost exactly**. This meaningfully de-risks (but does not fully
replace) the earlier `INSUFFICIENT EVIDENCE` flag on that specific claim in the Wave 1 evidence map —
recommend downgrading that flag to "corroborated via secondary review, primary text still not
directly obtained" rather than leaving it at full INSUFFICIENT EVIDENCE.

**Important caution — do not misattribute a stale comparison.** The review states: "no upfront
combination therapy is recommended in the US guidelines," citing its own reference [40] — **I traced
reference [40] and confirmed it is the *2018* AHA/ACC guideline (Grundy SM et al., JACC 2019, DOI
10.1016/j.jacc.2018.11.003 — the JACC-side companion of this project's citations #17/#18), not the
2026 ACC/AHA guideline.** This review was written in a way that could be misread as describing the
*current* US guideline; it is not verified whether the *2026* ACC/AHA guideline retained, softened,
or changed that upfront-combination-therapy stance. Do not carry the "no upfront combination therapy
in the US" claim into `40_SYNTHESIS/` as if it describes the *current* 2026 ACC/AHA position — that
remains unverified pending direct access to the 2026 guideline text.

**Incidental new citation found in this source, flagged for whichever role owns it:** "Leosdottir M,
Schubert J, Brandts J, et al. Early Ezetimibe Initiation After Myocardial Infarction Protects Against
Later Cardiovascular Outcomes in the SWEDEHEART Registry. J Am Coll Cardiol 2025;85:1550–1564." — a
large-registry **OBSERVATIONAL EVIDENCE** source on ezetimibe timing post-MI, directly relevant to
trials-efficacy's Search Protocol items 5/8/9, not independently verified beyond what's printed in
this review's reference list.

## D. 2022 Taiwan primary-prevention guideline (#35) — exact recommendation text (PRIMARY SOURCE)

Source: `20_EVIDENCE/guideline-risk/fulltext/Huang_2022_Taiwan-primary-prevention-guideline.pdf`
(gitignored). Full citation confirmed against the parsed text: Huang PH, Lu YW, Tsai YL, Wu YW, Li HY,
Chang HY, Wu CH, Yang CY, Tarng DC, Huang CC, Ho LT, Lin CF, Chien SC, Wu YJ, Yeh HI, Pan WH, Li YH,
"on behalf of the expert committee for the Taiwan Lipid Guidelines for Primary Prevention." *J Formos
Med Assoc* (in press at time of this PDF — see note below). DOI `10.1016/j.jfma.2022.05.010`, PMID
35715290. No PMC deposit (`elink` confirmed empty). **Obtained instead from the Taiwan Society of
Lipids and Atherosclerosis's own direct-hosted mirror**,
`https://www.tas.org.tw/upload/files/1-s2_0-S0929664622002157-main%20(1).pdf` — a different host from
`sciencedirect.com`/`ahajournals.org`/`academic.oup.com`, not behind the same Cloudflare bot-wall
(`HTTP 200`, `content-type: application/pdf`, no challenge headers). Retrieved 2026-08-30T21:19:35Z
(UTC). SHA-256 (PDF): `e18cf414bf3ea20e3d8a4467baf38300fde31fd3bedc3c095f5947b392567efc`. Parsed
cleanly; parsed markdown SHA-256: `b7de41285d71dc0b7618d3059c389b87bdfaa89b1ebc8f142488b0a1d44cd583`.

**Provenance note:** the PDF's own header reads "ARTICLE IN PRESS" — this is an uncorrected-proof
version (28 pages in proof layout, not yet paginated to the final 121(12):2393-2407 print range),
which is consistent with, and explains, why `Tonvasca_2026.md` cites this paper by its `pii` (an
in-press identifier) rather than by final print pagination (see `citation-verification-table.md`
§B). Title, full author list, and journal match the target citation exactly — this is confirmed to
be the same paper, an earlier-stage version of it.

**Evidence Hierarchy tag: GUIDELINE / CONSENSUS.** Verbatim excerpts, guideline's own COR/LOE tags
preserved exactly:

> "For subjects with DM, non-dialysis CKD, or LDL-C ≥190 mg/dL, this guideline suggests the LDL-C
> level for initiation of therapy and treatment target is 100 mg/dL... Since the baseline LDL-C level
> is high, moderate-to high-intensity statins combined with ezetimibe is recommended for subjects
> with LDL-C ≥190 mg/dL."
>
> "In subjects with DM, non-dialysis CKD, LDL-C ≥190 mg/dL, immediate lipid lowering therapy should
> be started and the LDL-C target is <100 mg/dL. **(COR I, LOE B)**"
>
> "In subjects with LDL-C ≥190 mg/dL, moderate-to high-intensity statins combined with ezetimibe is
> recommended. **(COR I, LOE B)**"
>
> "In subjects with ≥2 risk factors and LDL-C ≥115 mg/dL, non-pharmacological therapy should be
> initiated and the LDL-C target is <115 mg/dL. **(COR IIa, LOE C)**"
>
> "In subjects with 1 risk factor and LDL-C ≥130 mg/dL, non-pharmacological therapy should be
> initiated and the LDL-C target is <130 mg/dL. **(COR IIa, LOE C)**"
>
> "In subjects without any risk factor, this guideline suggests that the LDL-C level for initiation
> of therapy and treatment target is 160 mg/dL based on the experts' consensus."

**Four distinct, risk-stratified LDL-C targets for primary prevention in this Taiwan guideline: <100
mg/dL (DM/CKD/LDL-C≥190), <115 mg/dL (≥2 risk factors), <130 mg/dL (1 risk factor), <160 mg/dL (0 risk
factors).** These are all **primary-prevention** targets — do not conflate with the secondary-
prevention/high-risk numbers from #29, the TSC CCS guideline (<70/<50 mg/dL), the ADA 2025 figures
(<70/<55 mg/dL), or the ACC/AHA <55 mg/dL figure — four different guidelines, four different risk
tiers, several overlapping numbers that are easy to cite in the wrong context if not kept straight in
`40_SYNTHESIS/`.

**Also notable — direct international comparison in the guideline's own text:** "This recommended
LDL-C level is close to the 2019 ESC lipid guidelines suggesting the LDL-C target <116 mg/dL in the
low risk individuals... lower than that in the Japanese and Korean lipid guidelines where the LDL-C
target is <140 mg/dL for moderate risk in Japan and <130 mg/dL for those with 2 or more major risk
factors in Korea." Useful international-context color for `40_SYNTHESIS/`, sourced to the primary
document.

## Summary for the Director

- Item 6 (numeric-threshold confirmation): **3 of 5 targets fully completed with primary-source
  verbatim text** (2023 TSC CCS, ADA 2025 Ch.10, #35 the 2022 Taiwan primary-prevention guideline —
  the last found via the Taiwan Society's own direct-hosted PDF mirror, `tas.org.tw`, which sits
  outside the Cloudflare wall that blocks `sciencedirect.com` directly); **2 of 5 remain blocked**
  (T-006 Taiwan Lp(a) 2026, #34 the 2019 ESC/EAS base guideline — neither has a PMC copy; for T-006
  specifically, both a WebSearch of `tas.org.tw`'s indexed uploads and a direct pii-pattern-matched
  URL guess on the same mirror that worked for #35 and #29 were tried and came back empty/404 — the
  document does not appear to be mirrored there, at least not yet or not under that filename pattern;
  no equivalent mirror exists for #34, an ESC/EAS rather than Taiwan-society document).
- Item 4 (ezetimibe combination-timing wording): **substantively advanced**, though not from the
  three originally-named documents. The 2023 TSC CCS guideline supplies primary-source, COR/LOE-
  graded combination-timing text; the Katzmann & Laufs 2026 review supplies secondary corroboration
  of the still-blocked ESC 2025 Focused Update's own combination-timing stance.
- New citations surfaced, not yet claimed by any role: SWEDEHEART registry (Leosdottir M et al.,
  JACC 2025) — trials-efficacy domain.
- New caution logged: do not let the Katzmann & Laufs review's "no upfront combination in US
  guidelines" line be misread as describing the *current* 2026 ACC/AHA position — its citation is to
  the superseded 2018 guideline.
