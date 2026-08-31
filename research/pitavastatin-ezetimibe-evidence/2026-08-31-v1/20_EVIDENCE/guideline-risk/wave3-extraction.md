# Wave 3 — guideline-risk-intelligence

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: guideline-risk-intelligence · Wave: 3 (Synthesis wave, dispatched by Director per PI
authorization; this role's assignment is source acquisition, not synthesis authorship)

**Model confirmation:** this session runs Claude Sonnet 5, per the PI requirement stated in the
Director's task assignment.

**Resume note:** this is a continuing session (not a fresh resume) — governance files, the Wave 2
challenge round (`30_METHODS/shared/wave2-challenge-round.md`, read this Wave via `git show` on the
Director's commit without merging it into this branch — see note below), and prior Wave 1/2 outputs
were already in context. Confirmed via `ListAgents` that the Director and peers are reachable.

**On the shared challenge-round file:** `30_METHODS/shared/wave2-challenge-round.md` does not exist
on this role's own branch (it's a Director-owned file living on the Director's/main integration
line) — read via `git show <commit>:<path>` for its content without merging or writing to it, per
this role's file-ownership scope (own paths only). Its "Guideline angle" finding #2 — that Taiwan
STS 2026's "ezetimibe as first add-on" claim remains uncorroborated against primary text — is
directly relevant to this role's still-blocked T-005 and is noted here for continuity, not re-solved
this Wave (no new access route was found or attempted for T-005 itself; per the Director's Wave 3
instructions, that specific source stays exactly as recorded pending PI decision).

## Task 1: citation #29 (Chen PS et al. 2022 high-risk focused update) — full text obtained

Source: `20_EVIDENCE/guideline-risk/fulltext/Chen_2022_Taiwan-highrisk-focused-update.pdf`
(gitignored). Full citation confirmed against parsed text: Po-Sheng Chen, Meng Lee, Sung-Chun Tang,
Po-Hsun Huang, Hung-I Yeh, Charles Jia-Yin Hou, I-Chang Hsieh, Jiunn-Tay Lee, Jiann-Shing Jeng,
Yi-Heng Li, "2022 focused update of the 2017 Taiwan lipid guidelines for high risk patients:
Coronary artery disease, peripheral artery disease and ischemic stroke." *J Formos Med Assoc*, DOI
`10.1016/j.jfma.2022.03.001`, PMID 35410823. **Obtained via the same `tas.org.tw` mirror pattern
that worked for #30/#35** — `https://www.tas.org.tw/upload/files/1-s2_0-S0929664622001036-main.pdf`,
`HTTP 200`, `application/pdf`, no Cloudflare wall. Retrieved 2026-08-31T02:35:08Z (UTC). SHA-256
(PDF): `92646e438f5ddab7c9aceec4c91774e3b72bf1493f94d0f9cdc0517a8df0d00b`. License confirmed in-text:
CC BY-NC-ND (identical statement to #30/#35's mirrors). Parsed cleanly with
`mcp__llamaparse__parse_pdf_to_markdown` (20-page "article in press" proof, matching the pii-only
citation pattern seen before). Parsed markdown SHA-256:
`d2c488519659c2e4f6ee88e819b42c39e364702cd1aaf689b4c3161d700ccb53`.

**Evidence Hierarchy tag: GUIDELINE / CONSENSUS.** Verbatim excerpts, exact COR/LOE tags preserved:

> **CAD/ACS:** "The LDL-C target is < 70 mg/dL in patients with CAD/ACS (COR I, LOE B)." / "In
> addition to ACS plus diabetes, CAD/ACS at very high risk, including those with recent MI
> (<12 months), ≥2 prior MIs, multivessel CAD, or concomitant PAD (including extremity or carotid
> artery), a lower target of LDL-C < 55 mg/dL can be considered (COR IIa, LOE B)."
>
> **PAD:** "The LDL-C target is < 70 mg/dL in patients with symptomatic PAD... (COR I, LOE B)." /
> "In symptomatic PAD with CAD or carotid stenosis, a lower target of LDL-C < 55 mg/dL may be
> considered (COR IIa, LOE B)."
>
> **Ischemic stroke/TIA:** "it is reasonable to control LDL-C target < 70 mg/dL... (COR IIa, LOE
> B)." / "**it is reasonable to combine statin with ezetimibe to achieve LDL-C < 70 mg/dL (COR IIa,
> LOE B).**" / "adding a PCSK9 inhibitor is reasonable if LDL-C > 70 mg/dL under combined maximally
> tolerated statins plus ezetimibe (LOR IIa, LOE B)." *(source prints "LOR IIa" here, not "COR
> IIa" — SOURCE_VALUE = "LOR IIa, LOE B" as printed; FLAG = POSSIBLE_ERROR, most likely a
> typesetting typo for "COR IIa" given every other recommendation in this same document uses "COR",
> but reproduced exactly per the Numeric Integrity Rule — ACTION = NEEDS_ANALYST, do not silently
> correct.)*

**Algorithm (Figure 1, transcribed from the flowchart, not altered):** "Established diagnosis of
CAD/ACS, PAD or ischemic stroke/TIA" → moderate- or high-intensity statin, or moderate-intensity
statin plus ezetimibe, based on baseline LDL-C/clinical condition → if LDL-C not <70 mg/dL, escalate
to high-intensity or maximally tolerated statin **plus ezetimibe** → if still not <70 mg/dL, add a
PCSK9 inhibitor → if <70 mg/dL is met and the patient has a "high risk condition" (ACS+diabetes,
recent MI, ≥2 prior MIs, multivessel CAD, or concomitant PAD), <55 mg/dL can additionally be
considered.

**This directly confirms and specifies** what `pitavastatin topic.md`/`CLAUDE.md` describe generally
as this citation's domain (CAD/PAD/ischemic-stroke LDL-C targets) with the guideline's own exact
numbers, COR/LOE grades, and — notably — an explicit statin+ezetimibe combination step built into
its primary treatment algorithm, not just a rescue option.

**Incidental cross-references worth noting, not independently re-verified beyond what's printed
here:** this document's own reference list cites the 2019/2020 ESC/EAS guideline (Mach F et al., Eur
Heart J 2020;41:111-88 — matches #34 exactly, corroborating that DOI/citation string a second time)
and the REAL-CAD trial (Taguchi I et al., Circulation 2018;137:1997-2009 — a pitavastatin
dose-comparison hard-outcome trial, trials-efficacy's domain, already known to the project per the
Wave 2 challenge round as T-016) as its own evidentiary basis for the CAD/ACS <70 mg/dL target.

## Task 2: T-008 (111年健康促進統計年報 / Statistics of Health Promotion 2022) — full text obtained, with an important near-miss caught

**Access path (all direct-site attempts failed first):**
1. Direct fetch of `hpa.gov.tw`'s CMS pages (`Pages/List.aspx?nodeid=4617`,
   `Pages/Detail.aspx?nodeid=268&pid=18596`) via `curl`, with and without browser headers — **HTTP
   403** every time, no Cloudflare-style challenge header (a different WAF than the earlier
   Cloudflare-walled sites, but equally blocking).
2. `WebFetch` on the same URL failed with an SSL certificate error.
3. Located the correct detail page (title confirmed "健康促進統計年報" — "Statistics of Health
   Promotion") via a Wayback Machine snapshot of `Pages/Detail.aspx?nodeid=268&pid=18596`, and
   extracted the actual file-serving link from that snapshot's HTML:
   `Pages/ashx/GetFile.ashx?lang=c&type=1&sid=e8373f1313c944d0a19af337da55f4f9`.
4. **Important near-miss, caught and discarded:** the Wayback Machine's `/wayback/available` API,
   queried for that exact `GetFile.ashx?...sid=e8373f13...` URL, returned a "closest match" snapshot
   with a **different `sid` parameter** (`dcba2792...`). I fetched it anyway to check, and it turned
   out to be a **721-page cancer registry report** (癌症登記報告, by ICD-O-3 site code) — an
   entirely different HPA publication, not T-008. **This was never copied into the repo, is not
   referenced anywhere as if it were T-008, and its temp file has been deleted.** Flagging this
   explicitly, in the same spirit as the Wave 2 WebFetch-confabulation catch: an "available" match
   from a lookup API is not the same as an exact match, and I verified content identity (via the
   PDF's own title page and cover text) before treating anything as the real source, which is what
   caught this one.
5. **Successful route:** retried the *exact* `GetFile.ashx?...sid=e8373f13...` URL **directly against
   `hpa.gov.tw` itself** (not via Wayback) — this specific file-serving endpoint is **not** behind the
   same WAF that blocks the `Pages/*.aspx` CMS pages. `HTTP 200`, `application/pdf`, genuine 218-page
   document. Title page confirmed: "中華民國111年 健康促進統計年報 / Statistics of Health Promotion
   2022 / 衛生福利部國民健康署" (Health Promotion Administration, Ministry of Health and Welfare,
   R.O.C.) — this **is** T-008.

Source: `20_EVIDENCE/guideline-risk/fulltext/HPA_2022_111nian-Statistics-of-Health-Promotion.pdf`
(gitignored). Retrieved 2026-08-31T02:39:24Z (UTC), directly from `hpa.gov.tw`. SHA-256:
`7fafac32ca74295dd69349ad4d730a53a533ddc85aeef24c54b00cb96615423a`. 218 pages. Given the size, full
LlamaParse was not run on the whole document (impractical/unnecessary) — extracted the specific table
via local `pdftotext -layout` (a lighter-weight, exact-text extraction tool, not an AI-summarization
step, so no hallucination risk of the kind flagged in Wave 2) and located the exact table by grep.

**Evidence Hierarchy tag: INSTITUTIONAL PRACTICE / government statistical report** (this is a
national statistical survey report, not a clinical guideline or consensus statement — distinguish
from GUIDELINE/CONSENSUS in any downstream tagging).

**Exact match confirmed — Table 1-2-3 (page 30 of the PDF, "20歲以上人口三高盛行率" / "Prevalence
of Hypertension, Hyperglycemia/Diabetes, and Hyperlipidemia among Individuals Aged 20 and Over"),
age-stratified row for **65歲以上 / 65 and above**, survey period 民國107-111年 (2018–2022):**

| Condition | Both sexes | Male | Female |
|---|---|---|---|
| 高血壓 Hypertension | **63.0%** | 63.9% | 62.3% |
| 高血糖/糖尿病 Hyperglycemia/Diabetes | **28.2%** | 27.6% | 28.7% |
| 高血脂 Hyperlipidemia | **40.0%** | 34.6% | 44.6% |

**This is an exact, primary-source-verified match** to the figures printed in `Tonvasca_2026.md`'s
closing slide ("台灣高齡者的三高盛行率高，已成常態 (高血壓 63%、高血糖 28%、高血脂 40%)") — 63.0%→63%,
28.2%→28% (rounded), 40.0%→40%. The rounding from 63.0/28.2/40.0 to 63/28/40 in the slide is
consistent with ordinary presentation rounding, not a numeric error — noted for completeness per the
Numeric Integrity Rule, not flagged as a discrepancy.

**Exact operational definitions (verbatim, source's own methodology section):**

> "高血壓：收縮壓≧140mmHg 或舒張壓≧90mmHg，或回答有服用降血壓藥物。" (Hypertension: systolic BP
> ≥140mmHg or diastolic BP ≥90mmHg, or self-reported use of antihypertensive medication.)
>
> "高血糖/糖尿病：空腹8小時以上血糖值≧126mg/dL，或服用降血糖藥物。" (Hyperglycemia/diabetes: fasting
> [≥8h] glucose ≥126mg/dL, or use of glucose-lowering medication.)
>
> "高血脂：膽固醇≧240mg/dL 或三酸甘油酯≧200mg/dL，或服用降血脂藥物。" (Hyperlipidemia: cholesterol
> ≥240mg/dL or triglycerides ≥200mg/dL, or use of lipid-lowering medication.)

**Provenance/methodology note carried from the source, worth preserving for `40_SYNTHESIS/`:**
"Source：Nutrition and Health Survey in Taiwan, HPA... Note: Due to the COVID-19 pandemic in 2021,
the survey was interrupted. Therefore, data from 2021 and 2022 need to be combined for analysis,
with the analysis period spanning from 2018 to 2022." — i.e., the "107-111年" (2018-2022) period in
the table is a merged 5-year window specifically because of a COVID-related survey gap, not an
ordinary reporting period — worth keeping this caveat attached to the figure if cited.

## Task 3: OpenEvidence-relay bounded discovery pass — not executable this Wave

Per the Director's item 4 ("if your session has a working OpenEvidence relay, ONE bounded discovery
pass authorized"): checked `mcp__openevidence__oe_health` first (a local, no-network-cost check).
Result: `"healthy":false`, `"daemon":"up"`, **`"extension_connected":false`** — the relay daemon is
running but the browser extension it depends on is not connected/polling. Per the tool's own
description, `oe_ask` requires "the relay extension to be connected" — since it is not, I did not
attempt `oe_ask` (which would either fail outright or, worse, silently queue against a disconnected
extension). **No OpenEvidence discovery pass was performed this Wave** — this is an honest "tool
unavailable," not a skipped task. If the extension becomes connected in a future session, this
remains available as a one-time, discovery-only pass on T-005/T-006/#34 per the Director's original
authorization.

## Summary for the Director

- Task 1 (citation #29): **complete.** Full primary-source COR/LOE-graded text obtained via the same
  `tas.org.tw` mirror pattern that worked for #30/#35, plus one Numeric-Integrity flag (a "LOR IIa"
  vs "COR IIa" apparent typo in the source, preserved as printed).
- Task 2 (T-008): **complete**, with a genuine near-miss caught and discarded along the way (a
  Wayback "closest match" that turned out to be a different 721-page document, verified and rejected
  before use). Exact, primary-source-confirmed match to the closing-slide figures in
  `Tonvasca_2026.md`, plus the exact operational case definitions and a COVID-era methodology
  caveat.
- Task 3 (OpenEvidence bounded pass): **not executable** — relay daemon up, browser extension not
  connected. T-005/T-006/#34 remain exactly as recorded (`BLOCKED_FOR_SOURCE`), per the Director's
  instruction not to weaken that status without a genuinely obtained primary source.
