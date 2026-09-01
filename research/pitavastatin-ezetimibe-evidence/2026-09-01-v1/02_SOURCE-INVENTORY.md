# 02_SOURCE-INVENTORY — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

Specialists never edit this file directly (Decision 2026-08-31-05, carried forward) — they report
per-citation verification findings to the Director via the message schema (`CLAUDE.md` §6), and the
Director records them here.

This run's inventory is additive to `2026-08-31-v1/02_SOURCE-INVENTORY.md` (T-001–T-028 plus ~35
legacy citations). New entries continue the `T-0NN` numbering from where the prior run left off,
prefixed `T-1xx` to make the run boundary unambiguous at a glance. Nothing in the prior run's
inventory is edited here.

## Status legend

`UNVERIFIED` (recorded, not yet checked) · `VERIFICATION_IN_PROGRESS` · `VERIFIED` (independently
confirmed against a primary/lawful source) · `BLOCKED_FOR_SOURCE` · `SOURCE_CONFLICT` ·
`RETIRED` (superseded by a later, more specific entry).

## Candidate sources under active verification (Wave 0/1)

| ID | Source | Claimed DOI/locator | Status | Owner | Notes |
|---|---|---|---|---|---|
| T-101 | `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_Circulation.{pdf,md}` — "2026 ACC/AHA/AACVPR/ABC/ACPM/ADA/AGS/APhA/ASPC/NLA/PCNA Guideline on the Management of Dyslipidemia," Circulation. 2026;153:e1154–e1276 | DOI `10.1161/CIR.0000000000001423` | **`VERIFIED`** (2026-09-01, guideline-risk-intelligence) — see Decision 2026-09-01-04. Three independent, external corroborating checks: (1) `doi.org` resolves the DOI with a 302 redirect to a real `ahajournals.org` article path; (2) Crossref public API (`api.crossref.org`) metadata — title/journal/volume/publisher/author list — matches the PDF's own internal citation, including an independently-cross-validated publication date (2026-04-28) matching the running footer on every page; (3) systematic (not just spot-check) internal-coherence review across all 123 pages: consistent mg/dL↔mmol/L conversions, known-literature figures reproduced correctly, genuine per-page `ahajournals.org` download watermark, correct COR/LOE table formatting throughout. **Honest caveat, not chain-of-custody-verified:** `ahajournals.org` itself is Cloudflare-walled to this project's tools, so this is verification-by-independent-corroboration, not a literal byte-for-byte publisher re-download match. Evidence Hierarchy tag: `GUIDELINE/CONSENSUS`. | guideline-risk-intelligence | Local-only per `CLAUDE.md` §11 (gitignored) regardless of verification status — full text redistribution rights are a separate, unaddressed question from authenticity. Resolves prior-run citation #28's `BLOCKED_FOR_SOURCE` status — see new entry below. |
| T-102 | `inbox/2026-acc-aha-drive/` bundle overall (34 files + `MANIFEST.md`) — AI-assisted "2018 vs 2026 ACC/AHA Dyslipidemia Guidelines Comparison" draft set | n/a (secondary/derivative) | `UNVERIFIED` — per-file dedup and claim-level verification **deferred**, not started (Director's explicit Wave 1 priority ordering put T-101 verification and focus area 1 ahead of intake dedup; guideline-risk reports readiness to pick this up next). | guideline-risk-intelligence | Treat as `EXPERT INTERPRETATION`/`INSUFFICIENT EVIDENCE` at best until specific claims are checked. Never cite as "the official guideline" — T-101 now fills that role directly, reducing (but not eliminating) the need to rely on this bundle at all for guideline-wording claims. |
| T-103 | `.../adjudication_log_v2.md` (2 byte-identical copies) — 4 claimed corrections, each citing `markdown/1-s2.0-S0735109725102544.md` | Self-cited source file not present in intake | `RETIRED` — moot. guideline-risk-intelligence reached direct primary-source verification (T-101) without needing to chase this file; recommends treating Q3 as closed unless another role specifically needs it. | guideline-risk-intelligence | Not pursued further — see `04_OPEN-QUESTIONS.md` Q3 (closed as moot). |

## New entry: prior-run citation #28 resolved via co-publication

**T-104** — Cross-reference/resolution for `2026-08-31-v1/02_SOURCE-INVENTORY.md` T-028 (Blumenthal RS
et al., "2026 ACC/AHA guideline," DOI `10.1016/j.jacc.2025.11.016`, JACC — `BLOCKED_FOR_SOURCE` as of
prior-run closure). **T-028 itself is not edited** (additive-versioning discipline; the prior run is
closed) — this entry records the resolution as new information.

**Finding (2026-09-01, guideline-risk-intelligence):** T-028's JACC DOI and T-101's Circulation DOI
are a genuine simultaneous dual society-journal co-publication of the *same* guideline, not a citation
error. Verified via Crossref: both DOIs' author lists are identical in name and order (Blumenthal,
Morris, Gaudino, Johnson, ...). This is the same pattern the 2018 predecessor guideline used (cited
inside the 2026 guideline itself: Circulation 2019;139:e1082–e1143 / JACC 2019;73:3168–3209).

**Status:** T-028's underlying content is now `VERIFIED` and full-text-obtained **via its Circulation
co-publication (T-101)**, even though the JACC-side PDF itself is not separately in hand. Any claim
that was `BLOCKED_FOR_SOURCE` in the prior run specifically because citation #28 was unobtainable
should be re-examined against T-101's content in this run's `20_EVIDENCE/guideline-risk/` outputs —
this does not retroactively change the prior run's own closed record, but this run's synthesis may
now state the content directly where the prior run could only say "blocked."

## New per-focus-area entries

**T-105** — `20_EVIDENCE/guideline-risk/focus-area-1-guideline-wording.md` (guideline-risk-intelligence,
2026-09-01) — exact-quote extraction from T-101 with COR/LOE and page locators: 4-tier risk-stratified
absolute LDL-C/non-HDL-C targets (<100/<70/<55 mg/dL), ezetimibe add-on wording (COR 2a, with a
risk-tier-dependent "reasonable to add" vs "should be added" nuance), statin-intolerance/SAMS
positioning (incl. an explicit East-Asian pharmacogenetic dosing caution — routed to
safety-pharmacology-intelligence for its focus area 4), and the full target-attainment table.
**Notable negative/contrast finding:** T-101 (US ACC/AHA 2026) is explicitly **stepwise** (statin
first; add-on only if goal not met on maximally tolerated statin) — it does **not** use "early/upfront
combination therapy" language. This is a genuine, citable transatlantic contrast with ESC's 2025
Focused Update (upfront high-intensity statin + ezetimibe in the in-hospital ACS-intensification
context specifically — a different, narrower clinical scenario than general goal-directed therapy) —
see Decision 2026-09-01-05. Feeds the attack/defense section (focus area 5) directly: "not all major
guidelines uniformly endorse early/upfront combination" is a legitimate counter-argument, not an
error to paper over. Also explicit: T-101's SAMS/statin-intolerance content is analogous US context
only — it does **not** resolve the still-open Taiwan STS "ezetimibe as first add-on" `BLOCKED_FOR_SOURCE`
gap (carried forward from the prior run), which remains a distinct, unobtained document.

Still to populate (T-106 onward): Phase III/FDC trial RWE search results, new 2 mg-vs-4 mg data, any
newer HIJ-PROPER follow-up/re-analysis, intake bundle (T-102) dedup/verification, PCSK9-targeting/
bempedoic acid/inclisiran positioning trials for the attack/defense section.
