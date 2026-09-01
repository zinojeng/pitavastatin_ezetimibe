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

**Status:** OPEN — not yet searched this run. trials-efficacy-intelligence to determine at Wave 1
whether any RWE (registry, claims-database, or post-marketing observational study) exists beyond the
Phase III/FDC trial and the dose-comparison literature already known from the prior run.

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
   contribution (the "safety/DDI-grounds" scenarios where these are more defensible than FDC) are
   currently `EXPERT INTERPRETATION`, not independently sourced. **Director's call:** acceptable to
   carry as `EXPERT INTERPRETATION`-tagged through Wave 2/3 (the claim-safe taxonomy is designed
   exactly for this — an honestly-labeled inference is not a defect), but must be independently
   sourced (or re-tagged/softened) before `50_MANUSCRIPT/` treats it as more than a caveat. Flagged as
   a Wave 2 follow-up for safety-pharmacology or trials-efficacy, whichever has search bandwidth —
   not urgent for Wave 1 closure.

## Carried forward from the prior run (still open, relevant to this run's focus areas)

- Taiwan STS 2026 consensus: citation verified, but the specific "ezetimibe as first add-on" content
  claim remains `BLOCKED_FOR_SOURCE` (PI-confirmed not assumed resolvable) — directly relevant to
  this run's focus area 1; re-check whether T-101 (if verified) or any other new source closes this.
- No trial has been found closing the Level 3 (pitavastatin/ezetimibe-specific hard-outcome) evidence
  gap beyond HIJ-PROPER's non-superior overall primary endpoint — directly relevant to this run's
  focus area 3 and the attack/defense section (focus area 5). Re-confirm no newer trial exists as
  part of Wave 1/2 search, do not assume the prior run's negative finding is still current without
  re-checking.
