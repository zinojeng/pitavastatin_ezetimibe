# 04_OPEN-QUESTIONS — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

Additive to `2026-08-31-v1/04_OPEN-QUESTIONS.md`. Open items from that run are not repeated here
unless this run's new material bears on them directly (noted where relevant).

## Q1 — Is `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_..._Circulation.{pdf,md}` a genuine,
verifiable primary source?

**Status:** ✅ **RESOLVED — `VERIFIED`** (2026-09-01, guideline-risk-intelligence; Decision
2026-09-01-04). Three independent, external corroborating checks (doi.org 302 redirect to a real
`ahajournals.org` path; Crossref public-API metadata match incl. an independently-cross-validated
publication date; systematic 123-page internal-coherence review). Honest caveat retained: this is
verification by independent corroboration, not a byte-for-byte publisher re-download match (
`ahajournals.org` itself is Cloudflare-walled to this project's tools). Tagged `GUIDELINE/CONSENSUS`
in `02_SOURCE-INVENTORY.md` T-101.

## Q2 — Relationship between DOI `10.1161/CIR.0000000000001423` (Circulation, new) and DOI
`10.1016/j.jacc.2025.11.016` (JACC, prior run's citation #28)

**Status:** ✅ **RESOLVED — genuine co-publication, not a citation error** (2026-09-01,
guideline-risk-intelligence; Decision 2026-09-01-05). Crossref author lists for both DOIs are
identical in name and order — the same dual-journal pattern the 2018 predecessor guideline used.
Prior run's T-028 (`BLOCKED_FOR_SOURCE`) is not edited (closed run), but this run treats its content
as obtained via T-101 — see `02_SOURCE-INVENTORY.md` T-104.

## Q3 — Is `markdown/1-s2.0-S0735109725102544.md` (the intake's own self-cited "raw guideline
source") obtainable or real?

**Status:** ✅ **CLOSED as moot** (2026-09-01). With T-101 independently verified via a cleaner path
(DOI/Crossref), chasing this file is unnecessary for this run's purposes. Not pursued further.

## Q4 — How should the intake's own evidence-tier scheme interact with `CLAUDE.md` §7?

**Status:** OPEN, low priority, Director's provisional answer already recorded in
`00_RUN-MANIFEST.md`/`01_RESEARCH-CHARTER.md`: **not adopted** as this project's taxonomy; may be
recorded as a provenance cross-reference only. Revisit only if a specialist finds a case where this
provisional answer causes real friction.

## Q5 — Real-world evidence (RWE) for pitavastatin/ezetimibe FDC (focus area 2)

**Status:** ✅ **ANSWERED** (2026-09-01, trials-efficacy-intelligence). No new pitavastatin+ezetimibe
FDC RWE found beyond the prior run's TE-013 (Lu 2026, Taiwan post-PCI cohort) — still the only one.
An atorvastatin/ezetimibe FDC RWE abstract (ACC 2026) shows the drug class accumulating RWE elsewhere
while pitavastatin specifically does not yet — noted as a fair limitation, not chased further.

## Q6 — No direct pitavastatin/ezetimibe-FDC-vs-high-intensity-statin-monotherapy trial

**Status:** OPEN, confirmed gap (2026-09-01, safety-pharmacology-intelligence, focus area 4). Neither
RACING (rosuvastatin, not pitavastatin) nor K-924 (internal pitavastatin dose comparison only)
directly supports positioning claim (b) — FDC vs. high-intensity statin monotherapy — head-to-head.
This is an honest limitation to state explicitly in `40_SYNTHESIS/` and the attack/defense section,
not to paper over with adjacent evidence. No action requested — recorded for the Final QA/limitations
section.

## Q7 — FDC-specific CKD dosing remains unaddressed (carried forward, reconfirmed)

**Status:** OPEN, unchanged from the prior run — reconfirmed by safety-pharmacology-intelligence this
run (no new source found). Record as a persistent limitation, not a search failure.

## Q8 — Two new-search candidates from safety-pharmacology needing a Director/PI call

**Status:** OPEN.
1. "Optimizing LDL-C Reduction: High-Dose Pitavastatin Vs. Combination Therapy With Ezetimibe In Type
   II Diabetes" (AJBR 2024, DOI `10.53555/ajbr.v27i4s.7096`) — directly on-topic title, but abstract
   returned HTTP 403; no content obtained or cited. **Director's call:** low priority to chase further
   — title-only relevance is not worth spending scarce lawful-access budget on unless another role
   independently surfaces full text through a different route. Do not cite anything from this beyond
   its existence as an unverified candidate.
2. PCSK9-targeting/inclisiran DDI mechanistic claims used in safety-pharmacology's attack/defense
   contribution — **partially resolved (2026-09-01)**. safety-pharmacology independently re-verified
   T-101 directly (grepped the raw `.md`, not a relay of guideline-risk's extraction) and confirmed,
   at T-101 lines 2011–2022, guideline text describing PCSK9 mAb/inclisiran as "well tolerated and
   safe" and bempedoic acid's indication for statin-attributed side effects. **The
   tolerability/indication claim is upgraded to `GUIDELINE/CONSENSUS`.** The DDI-*mechanism* claims
   (OATP1B1/CYP3A4-level comparisons) remain `EXPERT INTERPRETATION` — T-101 says nothing at that
   mechanistic level, and safety-pharmacology explicitly did not let the tolerability upgrade bleed
   into the DDI-mechanism claims. Still deferred to Wave 2, not urgent for Wave 1 closure.

## Carried forward from the prior run (still open, relevant to this run's focus areas)

- Taiwan STS 2026 consensus: citation verified, but the specific "ezetimibe as first add-on" content
  claim remains `BLOCKED_FOR_SOURCE` (PI-confirmed not assumed resolvable) — directly relevant to
  this run's focus area 1; re-check whether T-101 (if verified) or any other new source closes this.
- No trial has been found closing the Level 3 (pitavastatin/ezetimibe-specific hard-outcome) evidence
  gap beyond HIJ-PROPER's non-superior overall primary endpoint — directly relevant to this run's
  focus area 3 and the attack/defense section (focus area 5). Re-confirm no newer trial exists as
  part of Wave 1/2 search, do not assume the prior run's negative finding is still current without
  re-checking.

## Q9 — Two new HIJ-PROPER-adjacent substudies need independent fetch/verification before Wave 3

**Status:** OPEN. Yamaguchi 2018 (Atherosclerosis) — WebSearch-aggregated only, `NEEDS_ANALYST` before
citing HR/CI. Sci Rep 2021 (PMC8021554) — N/cutoff HIGH confidence, HR/CI MODERATE (PMC PDF
anti-bot-blocked, same issue as the prior run). Try again at Wave 2 if tool access improves; otherwise
carry into synthesis with the confidence caveats already attached, not silently upgraded.

## Q10 — Inclisiran lacks a published hard-outcome trial

**Status:** OPEN, confirmed gap (trials-efficacy, focus area 5). Only design/protocol papers found
(VICTORION-2 Prevent, ORION-4). Must not be grouped with CLEAR-Outcomes/FOURIER/ODYSSEY OUTCOMES as
"hard-outcome-proven" in the attack/defense section — record as a distinct, currently
surrogate/mechanistic-only case for inclisiran specifically.
