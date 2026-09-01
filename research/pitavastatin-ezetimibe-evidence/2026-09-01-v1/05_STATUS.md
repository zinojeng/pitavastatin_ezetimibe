# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

**Authoritative current-gate/wave pointer for this run.**

## QA REOPENED — Final Gate under revision (post-Decision 2026-09-01-13)

The Final Gate declared in Decision 2026-09-01-13 (`PASS_WITH_MINOR_ISSUES`) has been **reopened**
per Decision 2026-09-01-14: a factual error was found in how this run handled the "2.4 mmol/L" figure
(it IS genuinely printed in T-101 at page e1159, alongside a genuinely different "2.6 mmol/L" at page
e1199 — a real source-internal inconsistency, not an extraction artifact as Decision 2026-09-01-10
had wrongly concluded). PI caught this via independent `pdftotext` on the actual PDF; Director
independently re-verified via a third tool (PyMuPDF) before acting.

**Status of the correction:**
- [x] `03_DECISION-LOG.md` — Decision 2026-09-01-14 records the full correction, exact quotes/pages,
      and a process-failure account.
- [x] `02_SOURCE-INVENTORY.md` — T-106 entry added.
- [x] `40_SYNTHESIS/00_executive-synthesis.md` §2.2 — corrected.
- [x] `40_SYNTHESIS/02_evidence-traceability-table.md` — corrected.
- [x] `20_EVIDENCE/guideline-risk/focus-area-1-guideline-wording.md` — corrected by guideline-risk,
      confirmed with a **fourth** independent extraction method (isolated single-page `pdftotext -f 6
      -l 6`); full three-round correction history preserved visibly (Decision 2026-09-01-15).
- [ ] `99_FINAL-QA.md` — correction requested from the independent auditor (its own owned file;
      Director does not edit it directly), awaiting a revised Final Gate recommendation.
- [ ] `50_MANUSCRIPT/` — checked, does not contain the granular severe-hypercholesterolemia tier
      table, no correction needed there.

**Final Gate will be re-declared once the auditor's revised recommendation is received.** Branch
`worktree-pit-eze-run-2026-09-01` remains local-only, not pushed to `origin`, per the PI's explicit
instruction.

---

## Wave/Gate history

- **Wave 0 (Orientation):** Duplicate-Director collision detected and resolved before any specialist
  contact (Decision 2026-09-01-01) — the other Director session disclosed fully and stood down.
  Governance scaffold created; new Google Drive intake inventoried (35 files); the unplanned
  `inbox/2026-acc-aha-drive/official/` candidate primary source found and treated as unverified
  pending independent check (Decision 2026-09-01-03). `.gitignore` extended to exclude `inbox/`
  wholesale (Decision 2026-09-01-02).
- **Wave 1 (Source/Evidence Verification):** All three specialists dispatched. T-101 (the `official/`
  2026 ACC/AHA guideline text) independently **VERIFIED** via DOI resolution + Crossref metadata +
  123-page internal-coherence review (Decision 2026-09-01-04) — resolves the prior run's long-blocked
  citation #28 via a genuine dual co-publication (Decision 2026-09-01-05). K-924 matched-dose figures
  independently verified against primary full text (Decision 2026-09-01-09). Intake dedup complete
  (34→15 files). Two specialist self-corrections made transparently (COR grading, Decision
  2026-09-01-07; a 3-tier severe-hypercholesterolemia structure replacing a non-existent "2.4 mmol/L"
  figure that turned out to be an extraction artifact, not a source value — Decision 2026-09-01-10,
  which explicitly supersedes the PI's own "preserve 2.4 mmol/L" instruction once its factual premise
  no longer held). Three QA corrections routed and confirmed (Decision 2026-09-01-06). All three
  specialists' work consolidated onto the Director's branch via clean cherry-picks.
- **Gate 1: PASSED** (Decision 2026-09-01-11) — facts verified before interpretation.
- **Wave 2 (Evidence + Methods, incl. Challenge Round):** substantively completed as part of each
  specialist's combined Wave 1 + attack/defense dispatch (guideline-risk 5 attacks, trials-efficacy 4
  attacks, safety-pharmacology 3 attack categories) — see `01_attack-defense.md`.
- **Gate 2: PASSED** (Decision 2026-09-01-12) — conflicts resolved via Decision Taxonomy, open
  questions current.
- **Wave 3 (Synthesis):** `40_SYNTHESIS/00_executive-synthesis.md` (zh-TW integrated evidence brief),
  `01_attack-defense.md`, `02_evidence-traceability-table.md`, and
  `50_MANUSCRIPT/pitavastatin-ezetimibe-positioning-slides.md` (PI-authorized this run) all written.
- **Gate 3: PASSED** (Decision 2026-09-01-12) — Director Challenge Round, four-angle review verified
  with actual `grep` passes (`30_METHODS/shared/gate3-challenge-round.md`), not memory alone.
- **Wave 4 (Independent Audit):** fresh, independent auditor sub-agent (not a fork of the Director's
  session), read-only except `99_FINAL-QA.md`, audited the fully consolidated branch. Zero material
  findings; two minor non-blocking observations, one already corrected (Decision 2026-09-01-13).
- **Final Gate: `PASS_WITH_MINOR_ISSUES`.**

## Specialist summary

| Specialist | Contribution |
|---|---|
| `pit-eze-guideline-risk` | Verified T-101 as primary source; extracted exact 2026 ACC/AHA wording (goal-directed targets, ezetimibe add-on, statin-intolerance positioning); found the stepwise-vs-upfront-combination contrast; deduped/verified the intake bundle; caught and fixed two of its own extraction errors transparently; re-checked Taiwan STS/ESC 2025/Taiwan Lp(a) access (all still blocked, STS's OA status newly confirmed); wrote 5-point guideline-side attack/defense contribution. |
| `pit-eze-trials-efficacy` | Independently verified K-924 matched-dose figures; confirmed no new pitavastatin+ezetimibe FDC RWE beyond TE-013; reconfirmed the HIJ-PROPER Level 3 gap remains open; found two new HIJ-PROPER-adjacent substudies with honest confidence caveats; confirmed inclisiran's hard-outcome-trial gap; wrote 4-point trial-side attack/defense contribution incl. the REAL-CAD-based maximize-statin-first case. |
| `pit-eze-safety-pharmacology` | Built the clinical positioning case (glycemic, DDI, polypharmacy, elderly/Asian/Taiwan, CKD, adherence); caught and fixed a numeric-integrity issue in its own K-924 framing after Director QA; removed an incorrect Taiwan-STS guideline-attribution after Director QA; independently re-verified T-101 quotes rather than trusting a relay; wrote 3-category safety-side attack/defense contribution. |

## Required durable outputs — delivered

- `00_RUN-MANIFEST.md`, `01_RESEARCH-CHARTER.md`, `02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md`
  (13 decisions), `04_OPEN-QUESTIONS.md` (10 items, most resolved/closed, remainder honestly open),
  `05_STATUS.md` (this file), `90_CROSS-SESSION-LOG/` (full message-schema record).
- Reproducible search logs and exact extraction/evidence tables with PMID/DOI/URL + Evidence
  Hierarchy tags: `10_DATA/`, `20_EVIDENCE/`, `30_METHODS/` per specialist.
- Integrated zh-TW evidence brief: `40_SYNTHESIS/00_executive-synthesis.md`.
- Slide-ready clinical positioning/defense document: `50_MANUSCRIPT/
  pitavastatin-ezetimibe-positioning-slides.md`.
- Limitations/open gaps: `04_OPEN-QUESTIONS.md` + `40_SYNTHESIS/00_executive-synthesis.md` §9.
- Independent QA/final-gate report: `99_FINAL-QA.md`.

## Known limitations carried into FINAL (stated honestly, not resolved — see full detail in
`00_executive-synthesis.md`)

- Taiwan STS 2026's "ezetimibe as first add-on" content claim remains `BLOCKED_FOR_SOURCE` — this
  project's single largest unverified-but-load-bearing framing claim.
- No direct pitavastatin/ezetimibe-FDC-vs-high-intensity-statin-monotherapy trial exists (Q6).
- FDC-specific CKD dosing data remains entirely absent (Q7).
- Two new HIJ-PROPER substudies (TE-016, TE-017) need full-text independent verification if tool
  access improves (Q9) — currently carried with explicit MODERATE-confidence caveats.
- Inclisiran has no published hard-outcome trial (Q10).
- Taiwan health-insurance FDC coverage/co-pay data was not investigated this run.
