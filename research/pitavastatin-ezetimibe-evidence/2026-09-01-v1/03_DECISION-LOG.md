# 03_DECISION-LOG — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

Continues the decision-numbering convention from `2026-08-31-v1/03_DECISION-LOG.md` (which reached
Decision 40) but restarts the counter under this RUN_ID's own date prefix for clarity, per that run's
own additive-versioning precedent. Append-only.

---

### Decision 2026-09-01-01 — Duplicate-Director collision resolved by stand-down, not by silent merge

**Context:** At Wave 0 orientation, `ListAgents` showed a second live `pit-eze-research-director
[853c1a]` session (`busy`), concurrent with fresh restarts of all three specialist peers — strong
evidence the same PI directive reached two channels.

**Decision:** Per Golden Rule 1 (never silently substitute for/duplicate a peer), this Director
(`[5aa219]`) held all writes and sent a `CONFLICT` cross-session message before creating any file.
`[853c1a]` responded with full disclosure (working in isolated worktree `worktree-wave0-init`, two
draft files only, no specialist contact, nothing committed/pushed) and stood down unconditionally,
including a commitment not to push its branch or contact specialists. A follow-up `ListAgents` showed
`[853c1a]` no longer listed (session ended).

**Resolution:** `[5aa219]` proceeds as sole Research Director for `2026-09-01-v1`, writing the
manifest/charter fresh (not pulling `[853c1a]`'s draft) to keep authorship of Director-owned
governance files unambiguous. No specialist received conflicting task assignments — the collision
was caught and resolved before either Director dispatched real work, which is the intended outcome
of the health-check protocol (`CLAUDE.md` §13).

**Evidence Hierarchy tag:** n/a (governance/process decision, not a clinical claim).
**Decision Taxonomy:** n/a (control-plane resolution, not an evidentiary decision).

---

### Decision 2026-09-01-02 — `inbox/` excluded from git tracking wholesale

**Context:** The new Google Drive intake (`inbox/2026-acc-aha-drive/`, 35 files) plus an unplanned
`official/` subfolder (a 16.9 MB PDF + 697 KB `.md` derivative claiming to be the actual 2026 ACC/AHA
guideline) were found untracked in the working tree. The existing `.gitignore` only excluded
`**/*.pdf`/`**/*.PDF`, not `.md` derivatives or the small intake drafts.

**Decision:** Added a new `.gitignore` section excluding `inbox/` entirely, extending the existing
full-text/licensing principle (`CLAUDE.md` §11: full text is local-only until redistribution rights
are verified) to the intake folder as a whole, since intake material is explicitly unverified
secondary material per the PI's own instruction. Only curated, verified extractions written into
`10_DATA/`/`20_EVIDENCE/` by specialists are tracked — never the raw intake files themselves.

**Note:** this edit was first (mistakenly) applied to the shared checkout's `.gitignore` before this
session isolated into its own worktree (a background-job isolation guard blocked a subsequent file
creation but had already allowed this edit through). The same edit was then correctly reapplied
inside the isolated worktree. The stray uncommitted edit in the shared checkout is content-identical
and harmless (adds `inbox/` to a gitignore, touches no tracked research content) — flagged
transparently here and to the PI/user rather than silently left unmentioned; it can be committed,
reverted, or ignored without consequence when this branch is later consolidated.

**Evidence Hierarchy tag:** n/a. **Decision Taxonomy:** n/a (governance).

---

### Decision 2026-09-01-03 — `official/` guideline file treated as unverified candidate primary source, not fact

**Context:** `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_
Circulation.{pdf,md}` appeared in the intake folder, timestamped 2026-09-01 10:50–10:52 (after this
run's authorization message), with an accompanying `OFFICIAL_SOURCE_MANIFEST.md` claiming it is the
official *Circulation* 2026;153:e1154–e1276 publication, DOI `10.1161/CIR.0000000000001423`.

**Decision:** Despite Director's Wave 0 spot-check finding it highly plausible (matching SHA-256/
line-count self-report, realistic PDF-extraction artifacts, correct internal self-citation, and
topical — though not line-exact — agreement with 3–4 of the intake's own `adjudication_log_v2.md`
claimed corrections), **this file is NOT treated as verified.** Per the Tool-Confabulation Caution
(`CLAUDE.md` §9) and the Numeric Integrity Rule, "looks real" is not "independently confirmed."
guideline-risk-intelligence is assigned, as Wave 1 priority #1, to: (a) attempt DOI resolution via
doi.org/Crossref/PubMed (lawful metadata tools only — `research_hub` search tools, not
`download_paper`), (b) spot-check a sample of quoted recommendations against the **PDF**, not just
the `.md` derivative (to rule out conversion-introduced errors), (c) explicitly investigate whether
this DOI and the prior run's still-`BLOCKED_FOR_SOURCE` `10.1016/j.jacc.2025.11.016` are two genuine
co-publication DOIs for the same joint guideline or a citation error, and (d) report findings via the
standard message schema for the Director to record in `02_SOURCE-INVENTORY.md` — never to silently
treat the file as authoritative in the meantime.

**Evidence Hierarchy tag:** `INSUFFICIENT EVIDENCE` (pending verification) — not yet eligible for any
higher tag. **Decision Taxonomy:** `NEEDS_ANALYST` (routed to guideline-risk-intelligence).

---

### Decision 2026-09-01-04 — T-101 (`official/` guideline text) upgraded `UNVERIFIED` → `VERIFIED`

**Context:** guideline-risk-intelligence completed the Decision 2026-09-01-03 tasking and reported
back with three independent, externally-corroborated checks (not self-report of the file's own claims):
(1) `doi.org` resolves DOI `10.1161/CIR.0000000000001423` with a 302 redirect to a real
`ahajournals.org` article path — an unregistered/fake DOI 404s at the resolver, it does not redirect;
(2) Crossref's public API independently returned title/journal/volume/publisher/author-list matching
the PDF's internal citation, including a specific publication date (2026-04-28) matching the running
footer on every one of 123 pages; (3) systematic (not sampled) internal-coherence review across all
123 pages found no errors in repeated unit conversions, correctly reproduced known-literature figures,
a genuine per-page publisher download watermark, and correct COR/LOE formatting throughout.

**Decision:** T-101 is upgraded to `VERIFIED`, Evidence Hierarchy tag `GUIDELINE/CONSENSUS`, per the
Decision Taxonomy's `VERIFIED_AND_REPLACE` category (replaces the prior `INSUFFICIENT EVIDENCE`
holding position from Decision 2026-09-01-03). **Explicit caveat carried forward, not dropped:**
`ahajournals.org` is Cloudflare-walled to this project's tools, so this is verification by independent
corroboration (DOI registry + Crossref metadata + internal coherence), not a literal byte-for-byte
publisher re-download match — recorded honestly as such in `02_SOURCE-INVENTORY.md`, not overstated
as "identical to a fresh publisher download." This methodology (doi.org resolution + Crossref public
API, both lawful metadata-only tools per `CLAUDE.md` §10) is itself a reusable pattern worth using
again for any future candidate-source verification in this project.

**Downstream effect:** guideline-risk-intelligence's focus-area-1 exact-wording extraction
(`20_EVIDENCE/guideline-risk/focus-area-1-guideline-wording.md`) now proceeds from a verified source.

**Evidence Hierarchy tag:** `GUIDELINE/CONSENSUS`. **Decision Taxonomy:** `VERIFIED_AND_REPLACE`.

---

### Decision 2026-09-01-05 — Q2 resolved: genuine dual co-publication, not a citation error; and a real US-vs-ESC stepwise-vs-upfront-combination contrast recorded

**Context:** `04_OPEN-QUESTIONS.md` Q2 asked whether DOI `10.1161/CIR.0000000000001423` (T-101,
Circulation) and the prior run's `BLOCKED_FOR_SOURCE` DOI `10.1016/j.jacc.2025.11.016` (T-028, JACC)
were two genuine co-publication DOIs for the same guideline, or a bad/fabricated citation.

**Decision:** Resolved as genuine co-publication. Crossref records for both DOIs carry an identical
author list, same names and order (Blumenthal, Morris, Gaudino, Johnson, ...) — the same simultaneous
dual-journal publication pattern used by the 2018 predecessor guideline (Circulation
2019;139:e1082–e1143 / JACC 2019;73:3168–3209, both cited inside the 2026 text itself). T-028's content
is treated as `VERIFIED`/obtained via its Circulation co-publication (T-101) going forward in this run
— see `02_SOURCE-INVENTORY.md` T-104. The prior run's own closed record (T-028 = `BLOCKED_FOR_SOURCE`)
is **not edited**, per additive-versioning discipline; this is new information layered on top.

**Separately, a genuine finding recorded rather than smoothed over:** T-101 (US ACC/AHA 2026) is
explicitly **stepwise** — statin first, add-on only if goal not met on maximally tolerated statin — and
does **not** use "early/upfront combination therapy" language anywhere. This is a real, citable
contrast with ESC's 2025 Focused Update (upfront high-intensity statin + ezetimibe, but specifically in
the narrower in-hospital ACS-intensification context, not general goal-directed therapy — the two are
not the same clinical scenario, so this is a contrast to state precisely, not a contradiction to
resolve). guideline-risk-intelligence flagged this as a deliberate negative finding, not a search gap.
Recorded here so it survives into the attack/defense section (focus area 5) rather than being lost:
"not all major guidelines uniformly endorse early/upfront combination therapy" is a legitimate,
sourced counter-argument.

**Q3 also closed as moot** (04_OPEN-QUESTIONS.md): with T-101 independently verified, chasing the
intake's self-cited `markdown/1-s2.0-S0735109725102544.md` (a different extraction/pagination of the
same underlying guideline, per the Wave 0 spot-check) is no longer necessary for this run's purposes.

**Evidence Hierarchy tag:** `GUIDELINE/CONSENSUS` (both the co-publication finding and the stepwise-vs-
upfront contrast, each independently sourced to T-101/Crossref). **Decision Taxonomy:**
`VERIFIED_AND_REPLACE` (Q2), `NO_CHANGE` (Q3, closed without new evidence needed).

---

### Decision 2026-09-01-06 — Two QA catches routed back to safety-pharmacology for correction

**Context:** External QA input (relayed to the Director, specific enough to reference real committed
content — K-924 numbers and the Taiwan STS attribution — from `safety-pharmacology`'s already-
committed `positioning-brief.md`/`attack-defense-contribution.md`, commit `38f40a9`) identified two
issues before this content reaches Wave 2/3 synthesis.

**Issue 1 — numeric integrity (`positioning-brief.md`):** the K-924 "2mg+eze10 (−51.4%) vs pitava 4mg
(−45.2%)" framing is a cross-arm comparison presented as "最直接頭對頭／加 ezetimibe 優於劑量加倍" without
confirmation that this specific contrast was prespecified/statistically tested. The trial's actual
supported matched-dose LS differences are combo 2/10 vs pitava 2 = −11.9% (95% CI −15.2 to −8.7) and
combo 4/10 vs pitava 4 = −12.7% (95% CI −15.9 to −9.4). Per the Numeric Integrity Rule (`CLAUDE.md`
§9), routed back to safety-pharmacology to downgrade/rephrase unless it can confirm the direct
contrast was actually tested. Also flagged: the guideline table's mg/dL↔mmol/L conversion should get
an explicit QA note, not silent endorsement.

**Issue 2 — guideline-attribution over a still-blocked source (`attack-defense-contribution.md` §2.1):**
text states a recommendation is "consistent with Taiwan STS 2026," but Taiwan STS 2026 remains
`BLOCKED_FOR_SOURCE` (carried forward from the prior run, PI-confirmed not assumed resolvable). This is
exactly the `CLAUDE.md` §7 trap — citing a blocked source's content as if confirmed. Routed back to
retain only the mechanistic argument, re-tagged `EXPERT INTERPRETATION`, with the guideline-attribution
language removed.

**Decision:** Both routed to safety-pharmacology-intelligence for direct correction in its own owned
files (not a Director edit — file ownership preserved). Will confirm once safety-pharmacology reports
back. Neither issue is a large substantive problem — both are the ordinary “write it, catch it, fix
it” cycle this project's Challenge Round methodology exists for; recorded here so the correction is
traceable.

**Evidence Hierarchy tag:** n/a (process/QA decision). **Decision Taxonomy:** `NEEDS_ANALYST` (routed
to safety-pharmacology-intelligence) for both issues.

---

### Decision 2026-09-01-07 — guideline-risk self-corrected a COR-grading extraction error (transparent, not silent)

**Context:** During the T-102 intake-dedup cross-reference pass, guideline-risk-intelligence found
the intake's `quick_reference_card.md` disagreeing with its own already-written
`focus-area-1-guideline-wording.md`: the very-high-risk ezetimibe/PCSK9-add-on recommendation had
been graded COR 2a in its Wave 1 extraction, vs. the intake's claimed COR 1, LOE A with an
ezetimibe-before-PCSK9i sequencing requirement removed.

**Decision:** Re-extracted T-101 directly with a wider context window (root cause: the original
extraction used `pdftotext -layout`, and a too-narrow window caused a column-alignment misread). The
intake was correct: the true grading is **COR 1, LOE A**, and the sequencing-requirement-removed
statement is present verbatim in T-101's own synopsis text. Corrected transparently in
`focus-area-1-guideline-wording.md` with a visible correction note — not silently overwritten, per
the Numeric Integrity Rule (`CLAUDE.md` §9: never silently correct, always leave a trace). This is
recorded as a positive example of the intake's cross-reference value continuing even after T-101 was
independently verified as primary — dedup work was not wasted effort once verification succeeded.

**Evidence Hierarchy tag:** `GUIDELINE/CONSENSUS` (T-101, corrected). **Decision Taxonomy:**
`VERIFIED_AND_REPLACE` (replaces the erroneous COR 2a with the correct COR 1, LOE A).

---

### Decision 2026-09-01-08 — non-HDL-C "2.4 mmol/L" flagged as a likely source-internal conversion typo, not a validated distinct target

**Context:** `focus-area-1-guideline-wording.md`'s target-attainment table (§5) transcribes T-101's
printed non-HDL-C goal for the "Severe hypercholesterolemia (LDL-C≥190), no clinical ASCVD" row as
`<100 mg/dL (2.4 mmol/L)`. The transcription itself is correct (Numeric Integrity Rule followed — the
printed value was preserved exactly). But the accompanying note went further, asserting the 2.4 vs
2.2 mmol/L figures (for the <100 mg/dL and <85 mg/dL rows respectively) "are not [typos], per the
source" — i.e., defending 2.4 as a deliberately correct, distinct conversion.

**External QA catch:** 100 mg/dL cholesterol converts to 2.586 mmol/L, conventionally rounded to
**2.6 mmol/L** — not 2.4. This is confirmed by the *same table*: two other `<100 mg/dL` rows
("Diabetes, no ASCVD, standard risk" and "Diabetes, multiple ASCVD risk factors") are printed
elsewhere in T-101 as `<100 mg/dL (2.6 mmol/L)`. The `2.4 mmol/L` figure on the severe-
hypercholesterolemia/no-ASCVD row is therefore internally inconsistent with the guideline's own
conversion convention used two rows above it in the identical table — a published source-internal
conversion inconsistency (most plausibly a typo, `2.4` vs the expected `2.6`), not a genuinely
distinct, intentional target.

**Decision:** Routed back to guideline-risk-intelligence to revise the annotation — NOT to silently
change the transcribed `2.4 mmol/L` value (still preserved exactly as printed, Numeric Integrity Rule),
but to correct the note's claim from "these are not typos" to an explicit `POSSIBLE_ERROR`/
`NEEDS_ANALYST` flag, consistent with `CLAUDE.md` §9. `40_SYNTHESIS/` must privilege the mg/dL target
(`<100 mg/dL`, unambiguous and internally consistent across the table) and treat the `2.4 mmol/L`
mmol-side figure as an annotated source anomaly, not a value to build any claim on.

**Evidence Hierarchy tag:** `GUIDELINE/CONSENSUS` for the mg/dL target itself (unaffected); the mmol
conversion figure is flagged, not used as a load-bearing number anywhere. **Decision Taxonomy:**
`NEEDS_ANALYST` (routed to guideline-risk-intelligence for the annotation fix).

---

### Decision 2026-09-01-06 (outcome) — safety-pharmacology's three corrections confirmed, committed `b7bf5fa`

1. **K-924 dose-doubling claim:** retracted from its overclaimed framing; downgraded to
   `OBSERVATIONAL SIGNAL`/`INSUFFICIENT EVIDENCE`. Important honesty flag from safety-pharmacology:
   it could not independently verify the Director-relayed matched-dose LS-difference figures
   (−11.9%/−12.7%) either, from its own accessible sources — those numbers are labeled
   "Director-reported, not independently verified by this role" in its output, not presented as
   settled. **These numbers still need independent verification by a role with full-text access
   before Wave 3 treats them as confirmed** — see new action below, routed to trials-efficacy.
2. **mg/dL↔mmol/L anomaly:** confirmed and extended. safety-pharmacology grepped T-101 directly (not
   guideline-risk's table) and found the same 100 mg/dL value correctly converts to 2.6 mmol/L in 7+
   *other* locations in the identical document — strengthening Decision 2026-09-01-08's conclusion
   that the `2.4 mmol/L` figure is a source-internal artifact, not a validated distinct value.
   Working hypothesis on root cause: a column-merge artifact from T-101's "Table 1. Continued"
   two-column 2018-vs-2026 comparison layout — same PDF-extraction artifact class as the reversed
   sidebar heading noted at Wave 0. Relayed to guideline-risk with a request for a PDF-page-level
   (not `.md`-derivative) spot-check to confirm the root cause before this figure is relied on for
   anything beyond an annotated anomaly.
3. **Taiwan STS attribution:** removed; retagged `EXPERT INTERPRETATION`. safety-pharmacology
   acknowledged it should have caught this itself, given its own prior-run familiarity with the
   still-`BLOCKED_FOR_SOURCE` status — recorded plainly, not glossed over.

**New action:** trials-efficacy-intelligence asked to independently verify the K-924 matched-dose
LS-difference figures (−11.9% [95% CI −15.2 to −8.7], −12.7% [95% CI −15.9 to −9.4]) against the
primary trial source before Wave 3 synthesis treats them as confirmed — currently no role in this
project has independently verified them; they entered this run via an external QA relay to the
Director, not a specialist's own source check.

**Decision Taxonomy:** `VERIFIED_AND_REPLACE` (items 1 and 3, corrected); `NEEDS_ANALYST` (item 2
root-cause confirmation, routed to guideline-risk; K-924 LS-difference verification, routed to
trials-efficacy).

---

### Decision 2026-09-01-09 — K-924 matched-dose LS differences independently verified (trials-efficacy); focus areas 2/3/5 complete

**K-924 verification resolved:** trials-efficacy-intelligence confirms −11.9% (95% CI −15.2 to −8.7)
/ −12.7% (95% CI −15.9 to −9.4) are exactly correct — sourced to its own prior-run (2026-08-31-v1
Wave 2) LlamaParse full-text extraction of the K-924 J-STAGE PDF (hashed, SHA-256 on file in that
run's fulltext-manifest.md), MMRM same-dose pairwise comparisons. The original "−51.4% vs −45.2%"
cross-dose claim is confirmed NOT a formally-tested contrast, exactly as flagged. **Status: `VERIFIED`
by trials-efficacy against primary full text** — safety-pharmacology's "Director-reported, not
independently verified" citation is now upgradable. Director did not need to duplicate this lookup
personally, per the PI's instruction to verify it — trials-efficacy's own prior full-text access
satisfied it faster and more rigorously than a fresh Director search would have.

**Focus area 2 (RWE):** Q5 answered — no new pitavastatin+ezetimibe FDC RWE found beyond the prior
run's TE-013 (Lu 2026, Taiwan post-PCI cohort), still the only one. Noted: an atorvastatin/ezetimibe
FDC RWE abstract (ACC 2026) shows the drug class accumulating RWE elsewhere while pitavastatin
specifically does not yet — a fair, honestly-scoped observation for the limitations section.

**Focus area 3 (Level 3 gap):** re-confirmed no newer trial closes the HIJ-PROPER gap. Two substudies
not in the prior run's catalogue, both flagged with explicit confidence caveats rather than presented
as settled: Yamaguchi 2018 (Atherosclerosis, full absorber-phenotype publication) — MODERATE
confidence, WebSearch-aggregated only, not independently fetched (ScienceDirect 403'd, reported
honestly rather than confabulated) — `NEEDS_ANALYST`. Sci Rep 2021 (PMC8021554, open access,
baseline-LDL-C-stratified statin-naive subgroup: low-LDL-C N=686 HR 1.13 ns; high-LDL-C N=743 HR 0.72
95% CI 0.56–0.91 P=0.007, interaction P=0.012) — HIGH confidence on N/cutoff (two tools agreed),
MODERATE on HR/CI (single WebFetch source, PMC PDF blocked by anti-bot challenge, unresolved from the
prior run too).

**Focus area 5 (trial-side attack/defense):** built using REAL-CAD ("maximize statin first"
counter-position) and a hard-outcome comparator table for bempedoic acid/PCSK9i/inclisiran.
**Notable asymmetry flagged for synthesis:** inclisiran currently has **no published hard-outcome
trial** found (only design/protocol papers — VICTORION-2 Prevent, ORION-4) — a real gap vs.
CLEAR-Outcomes (bempedoic acid) and FOURIER/ODYSSEY OUTCOMES (PCSK9i). The attack/defense section must
not frame "hard-outcome-proven alternatives" as a uniform category — inclisiran is currently a
surrogate/mechanistic case, not (yet) an outcomes-proven one.

**Evidence Hierarchy tags:** K-924 matched-dose figures `DIRECT EVIDENCE` (verified); Yamaguchi 2018
`INSUFFICIENT EVIDENCE` pending independent fetch; Sci Rep 2021 subgroup `OBSERVATIONAL
EVIDENCE`/hypothesis-generating (HR/CI moderate confidence); inclisiran hard-outcome status
`INSUFFICIENT EVIDENCE`. **Decision Taxonomy:** `VERIFIED_AND_REPLACE` (K-924), `NO_CHANGE` (Q5, RWE
gap reconfirmed), `INSUFFICIENT_EVIDENCE` (both new HIJ-PROPER substudies, inclisiran outcomes gap).

---

### Decision 2026-09-01-10 — SUPERSEDES Decision 2026-09-01-08: "2.4 mmol/L" does not exist in the source at all; it was our own extraction artifact, not a source typo

**Context:** Following up on the column-merge hypothesis (Decision 2026-09-01-08/safety-pharmacology's
extension), guideline-risk-intelligence re-extracted the relevant page with `pdftotext -raw`
(preserves actual content-stream order, no column reconstruction) against T-101's own authoritative
numbered "Recommendations for Severe Hypercholesterolemia" section — not the error-prone summary
comparison table.

**Finding:** Severe hypercholesterolemia (LDL-C≥190) is a genuine **three-tier** structure, not the
two-tier one originally reported: Tier 1 (no ASCVD/HeFH/subclinical atherosclerosis/other risk
factors) → `<100 mg/dL (2.6 mmol/L)`, non-HDL `<130 (3.4 mmol/L)`, COR 1 B-NR; Tier 2 (HeFH/subclinical
atherosclerosis/additional risk factors, no clinical ASCVD) → `<70 mg/dL (1.8 mmol/L)`, non-HDL
`<100 (2.6 mmol/L)`, COR 1 B-R; Tier 3 (clinical ASCVD) → `<55 mg/dL (1.4 mmol/L)`, non-HDL
`<85 (2.2 mmol/L)`, COR 1 B-R. The original extraction had conflated Tiers 1 and 2 into a single
non-existent hybrid row (`<70 mg/dL / 2.4 mmol/L`) — a `pdftotext -layout` column-merge artifact on
this document's multi-row "Table 1. 2018 vs 2026" summary table. **The `2.4 mmol/L` figure does not
appear anywhere in T-101's actual text.**

**This changes the correct action from Decision 2026-09-01-08.** That decision (and the PI's own
explicit instruction to "preserve the explicit 2.4 mmol/L source-typo annotation") were both made on
the reasonable-at-the-time understanding that `2.4 mmol/L` was genuinely printed in the source as an
internally-inconsistent conversion. It was not.

**Root-cause wording corrected post-Wave-4 (2026-09-01, per the independent auditor's spot-check #4
in `99_FINAL-QA.md`):** this entry originally attributed the artifact solely to "this project's own
`pdftotext -layout` tooling." The auditor independently located the same garbled fragment at line 369
of the intake's own `.md` derivative (a *separate* extraction pipeline this project does not
control), showing the artifact is reproduced by at least two independent extraction pipelines, not
unique to this project's own tooling. The more precise framing: this is an artifact of T-101's
two-column PDF layout, reproduced independently by multiple extraction pipelines (this project's own
`pdftotext -layout`, and the intake's separate `.md` conversion) — not evidence that the source
itself prints `2.4 mmol/L` as a genuine (if inconsistent) value. This correction does not change the
final numbers (already fixed) or reopen the decision; it only sharpens the causal narrative per the
Numeric Integrity Rule's own standard of not overstating specificity. Per the Numeric Integrity
Rule's own logic (never build on an unverified number, and correct course transparently when better
evidence arrives rather than defending an earlier hypothesis) — **the `2.4 mmol/L` figure is dropped
entirely, not carried forward as an annotated anomaly.** The corrected 3-tier structure replaces it in
`focus-area-1-guideline-wording.md`.
guideline-risk also re-verified the earlier COR-1-vs-2a self-correction (Decision 2026-09-01-07)
against `-raw` mode and confirmed it holds.

**Methods improvement adopted project-wide for this run:** T-101's numbered "Recommendations for
[topic]" sections are treated as authoritative; its summary comparison tables ("Table 1. 2018 vs
2026") are treated as secondary and error-prone, cross-checked with `-raw`-mode extraction whenever a
summary-table figure looks internally inconsistent.

**Explicitly flagged for the PI:** this supersedes the PI's own "preserve the 2.4 mmol/L source-typo
annotation" instruction. That instruction is not disregarded lightly — it is superseded because the
factual premise it was based on (that 2.4 mmol/L is genuinely printed in the source) turned out to be
false on deeper investigation. Reported transparently rather than either silently complying with a
now-outdated instruction or silently overriding it without note.

**Evidence Hierarchy tag:** `GUIDELINE/CONSENSUS` (corrected 3-tier structure, `-raw`-mode verified).
**Decision Taxonomy:** `VERIFIED_AND_REPLACE` (supersedes Decision 2026-09-01-08's `NEEDS_ANALYST`
holding position with a final, verified correction).

---

### Decision 2026-09-01-11 — guideline-risk's attack/defense contribution complete; Wave 1 closed for all three specialists; Gate 1 declared

**guideline-risk's focus-area-5 contribution (5 honest attacks, not softened):**
1. 2026 ACC/AHA doesn't endorse upfront combination — stepwise (already established, Decision -05).
2. **T-101 treats ezetimibe/PCSK9i/bempedoic acid as interchangeable options, not ezetimibe-preferred**
   — and its own synopsis cites falling PCSK9 mAb costs as rationale for removing a barrier to going
   straight to PCSK9i instead of ezetimibe. A real, direct hit against "ezetimibe as the practical
   first choice," recorded without softening.
3. Nothing in T-101 is pitavastatin-specific or FDC-specific — citing it for the FDC's own efficacy
   case would repeat the exact RACING/REPRIEVE conflation error this project already guards against.
4. **The Taiwan STS "ezetimibe as first add-on" claim — this project's own central framing device
   since the prior run — remains unverified against primary text.** guideline-risk's own assessment:
   this is "honestly the single largest unverified-but-load-bearing claim in the whole project's
   framing," more consequential than any individual trial gap. **Director concurs and elevates this
   for explicit, prominent treatment in `40_SYNTHESIS/` and the manuscript** — it must not be stated
   as if resolved anywhere in this run's final output.
5. The "maximize statin first" counter-position is not just legacy inertia — it is literally what the
   newly-verified 2026 ACC/AHA guideline still recommends as step one.
Defenses noted where genuinely present; none manufactured where absent (explicitly not attempted for
#4).

**blocked-sources-recheck.md:** time-boxed re-check of Taiwan STS/ESC 2025/Taiwan Lp(a) found no new
access route for any of the three (same DOIs, still blocked). One genuinely new, useful finding:
Unpaywall now confirms Taiwan STS 2026 is Gold OA/CC BY (resolves the prior run's unresolved OA-badge
discrepancy) — but the actual page remains Cloudflare-bot-walled regardless of OA status, so full-text
access itself is unchanged, still `BLOCKED_FOR_SOURCE`.

**Wave 1 status: closed for all three specialists.** All Wave 1 work (plus most of Wave 2's
Challenge-Round-equivalent attack/defense contribution) is committed and consolidated onto the
Director's branch (`worktree-pit-eze-run-2026-09-01`) via cherry-pick — the single source of truth
for this run going into synthesis.

**Gate 1 declared: PASSED.** Facts substantively verified before interpretation, per `CLAUDE.md` §4:
T-101 independently verified (Decision -04), K-924 independently verified (Decision -09), intake
dedup complete (T-102), no `SOURCE_CONFLICT` left unresolved, all Numeric Integrity Rule catches
(Decisions -06, -07, -08→-10) resolved transparently. Remaining open items (Q1/Q4/Q6/Q7/Q9/Q10, Taiwan
STS block) are genuine, honestly-scoped evidence gaps — not blockers to Gate 1, exactly the kind of
"BLOCKED is a normal outcome" case the Runbook anticipates. Proceeding to Wave 2 wrap-up (already
substantively complete via the attack/defense contributions) → Gate 2 → Wave 3 synthesis.

**Evidence Hierarchy tag:** n/a (process decision). **Decision Taxonomy:** n/a.

---

### Decision 2026-09-01-12 — Gate 2 declared PASSED; Wave 3 synthesis complete; Gate 3 declared PASSED

**Gate 2 (Conflicts resolved via Decision Taxonomy; Open Questions current):** All Wave 1/2 conflicts
(K-924 numbers, 2.4 mmol/L figure, Taiwan STS attribution, COR grading) resolved via the Decision
Taxonomy and recorded (Decisions -06 through -11). `04_OPEN-QUESTIONS.md` is current as of this Wave.
Declared **PASSED**.

**Wave 3 (Synthesis) complete:** `40_SYNTHESIS/00_executive-synthesis.md` (zh-TW integrated evidence
brief), `40_SYNTHESIS/01_attack-defense.md` (consolidated 3-role attack/defense across the PI's 6
sub-areas), `40_SYNTHESIS/02_evidence-traceability-table.md` (new/updated citations + explicit
retracted-do-not-cite list), `50_MANUSCRIPT/pitavastatin-ezetimibe-positioning-slides.md` (12-slide
presentation outline, PI-authorized this run) all written and committed.

**Gate 3 (Director internal-consistency check) declared PASSED** — full record in
`30_METHODS/shared/gate3-challenge-round.md`. Four-angle review (guideline/trials/safety/methods) plus
one deliberate cross-check on whether the PI's superseded "preserve 2.4 mmol/L" instruction was
handled transparently. Verified with actual `grep` passes (not memory alone) that every retracted
number and prohibited phrase appears only in "do not cite"/correction-narrative context, never as a
live claim, across all Wave 3 output.

**Next:** Wave 4 — spawn independent auditor (read-only, writes only `99_FINAL-QA.md`).

---

### Decision 2026-09-01-13 — Wave 4 independent audit complete; Final Gate = PASS_WITH_MINOR_ISSUES; RUN COMPLETE

A fresh, independent auditor sub-agent (not a fork of the Director's session, to avoid inheriting
synthesis-writing bias) audited the fully consolidated branch and wrote `99_FINAL-QA.md`. It did not
trust the Director's own Gate 3 grep results — it re-ran the retraction/prohibited-phrase greps
independently, re-hashed the `official/` files independently, and directly grepped the `.md`
derivative itself to corroborate several specialist-quoted passages (finding, on its own, an
additional line-interleaving artifact at line 2014 that corroborates the project's "artifact-prone
source" finding, and independently locating line 369's garbled "2.4 mmol/L" fragment — see the
root-cause correction above).

**Result: zero material findings.** All eight of this project's established traps (from the prior
run) plus this run's five new specific risk areas (T-101 overclaiming, the K-924/2.4-mmol-L
retractions, inclisiran hard-outcome grouping, and the PI-instruction-supersession transparency) were
checked and none were found violated. Two minor, non-blocking observations: (1) the Decision -10
causal-wording precision nit, corrected above; (2) a cosmetic pre-cherry-pick commit-hash reference in
prose (`b7bf5fa`/`38f40a9`) that doesn't resolve directly on the consolidated branch — noted, not
corrected (content is still correctly traceable by path).

**Final Gate: `PASS_WITH_MINOR_ISSUES`** (Runbook §36: may be marked `FINAL`). `40_SYNTHESIS/` and
`50_MANUSCRIPT/` are FINAL as of this decision.

**RUN 2026-09-01-v1 is complete.** All required durable outputs delivered (see `05_STATUS.md` for the
full manifest). Branch `worktree-pit-eze-run-2026-09-01` remains local-only, not pushed to `origin`,
per the PI's explicit instruction for this continuation.

---
