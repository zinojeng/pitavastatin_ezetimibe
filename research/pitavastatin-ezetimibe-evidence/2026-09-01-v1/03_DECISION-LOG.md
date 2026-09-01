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
