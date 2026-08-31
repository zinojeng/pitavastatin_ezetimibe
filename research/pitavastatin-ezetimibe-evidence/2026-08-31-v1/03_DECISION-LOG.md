# 03_DECISION-LOG — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

Append-only. One entry per material decision (source conflict resolution, taxonomy application,
scope change, gate transition). Use the Decision Taxonomy from `CLAUDE.md` §8. Never delete an
entry; if a decision is later reversed, add a new entry that supersedes it and say so explicitly.

---

## Decision 2026-08-31-01

**Issue:** How to treat `Tonvasca_2026.md`'s ~30+ embedded citations and numeric claims (LDL-C %
changes, HR/RR, AE rates) discovered during Wave 0 cataloging.

**Decision:** `NO_CHANGE` (provisional) — catalog only, do not treat any figure in `Tonvasca_2026.md`
as verified. All figures quoted from it in `02_SOURCE-INVENTORY.md` (e.g., HIJ-PROPER's HR 0.89,
RACING's 9.1% vs 9.9% MACE, Phase III FDC trial's −51.04%/−50.5% LDL-C change) are **PI-supplied,
unverified legacy figures** pending independent Wave 1 verification against primary sources.

**Reason:** Wave 0 is orientation-only (CLAUDE.md §4); interpretation and verification are Wave 1/2
work assigned to the three specialists. Treating legacy figures as pre-verified would violate the
Numeric Integrity Rule (CLAUDE.md §9) and the Runbook's "facts before interpretation" principle
(Golden Rule 6).

**Affected files:** `02_SOURCE-INVENTORY.md` (citation table, `verified?` = No for all rows).

**Source:** `Tonvasca_2026.md` (L-002).

**Approved by:** Research Director (Wave 0).

---

## Decision 2026-08-31-02

**Issue:** `Tonvasca_2026.md` is 2811 lines; only lines 1–1794 (~64%) were read in full during Wave 0
orientation, due to a single-read tool output cap.

**Decision:** `NEEDS_ANALYST` — flag the unread remainder (lines 1795–2811) as a Wave 1 task for the
owning specialist(s) rather than treating the Wave 0 partial read as a complete citation inventory.

**Reason:** Numeric Integrity Rule / provenance discipline — do not assert completeness of a source
inventory that is known to be partial.

**Affected files:** `02_SOURCE-INVENTORY.md` (explicit "not yet reached" note under the L-002
citation table).

**Source:** `Tonvasca_2026.md`, Wave 0 Read tool output (truncation notice at line 1794 of 2811).

**Approved by:** Research Director (Wave 0).

---

## Decision 2026-08-31-03

**Issue:** `research_hub`, `llamaparse`, and `openevidence` MCP servers — all listed as permitted
sources in the task instructions — failed to connect during the Wave 0 session (ENOENT for
`research_hub`/`llamaparse` binaries, CONNECTION_CLOSED for `openevidence`).

**Decision:** `NEEDS_ANALYST` — do not attempt to route around the failures (e.g., via Sci-Hub, which
remains prohibited regardless of other-source availability, CLAUDE.md §10). Record as an open
question / environment blocker for the PI to resolve before or during Wave 1, and re-check
connectivity at Wave 1 start rather than assuming the Wave 0 failure is permanent.

**Reason:** Golden Rule 7 ("Blocked is a valid research outcome") and CLAUDE.md §10's prohibition on
unauthorized-access workarounds.

**Affected files:** `00_RUN-MANIFEST.md` (blockers section), `04_OPEN-QUESTIONS.md`.

**Source:** Session tool-connectivity system reminders received during Wave 0 (2026-08-31).

**Approved by:** Research Director (Wave 0).

---

## Decision 2026-08-31-04

**Issue:** No dedicated manuscript/presentation-intelligence persistent role was named in the task
instructions' role list (Research Director, guideline-risk, trials-efficacy, safety-pharmacology,
independent-auditor only), yet the repo's mandated directory structure includes `50_MANUSCRIPT/`.

**Decision:** `NEEDS_PI` — leave `50_MANUSCRIPT/` unowned at Wave 0; do not silently assign it to the
Research Director as a standing responsibility or invent a sixth persistent role without PI
confirmation.

**Reason:** Runbook §43 treats manuscript work as strictly downstream of Director-approved facts,
methods, and evidence, and explicitly warns against premature parallel manuscript starts (Runbook
§33, §20). Given the task's role list omits this role, the safer default is to ask rather than
assume scope.

**Affected files:** `50_MANUSCRIPT/.gitkeep`, `CLAUDE.md` §3 (ownership matrix note),
`04_OPEN-QUESTIONS.md`.

**Source:** Task instructions (role list) vs. mandated directory list (both explicit in the same
instructions — genuine ambiguity, not an oversight to silently resolve).

**Approved by:** Research Director (Wave 0).

---

## Decision 2026-08-31-05

**Issue:** `CLAUDE.md` §3's File Ownership Matrix does not list an explicit writer for
`02_SOURCE-INVENTORY.md`. At Wave 1 kickoff, guideline-risk-intelligence independently (and
correctly, by the safest reading) declined to edit it directly and said it would report findings to
the Director instead.

**Decision:** `VERIFIED_NEW_SENSITIVITY` — formalize this as the explicit rule: `02_SOURCE-INVENTORY.md`
is Director-owned. Specialists never edit it directly; each specialist reports verification findings
(per-citation verified/refuted/superseded status) to the Director via the standard message schema,
and the Director updates the `verified?`/`superseded?` columns from those reports. This avoids
simultaneous-edit conflicts on a file all three specialists touch.

**Reason:** Consistent with the Runbook's file-ownership discipline (Runbook §28) and with how the
first specialist to reach this ambiguity resolved it on its own — codifying observed good behavior
rather than leaving the gap for the next peer to guess differently.

**Affected files:** `CLAUDE.md` §3 (needs an explicit `02_SOURCE-INVENTORY.md` row added — pending,
see `04_OPEN-QUESTIONS.md` sync-gap note), `05_STATUS.md`.

**Source:** Cross-session exchange with guideline-risk-intelligence, 2026-08-31 (`90_CROSS-SESSION-LOG/2026-08-31_wave1-kickoff.md`).

**Approved by:** Research Director (Wave 1).

---

## Decision 2026-08-31-06

**Issue:** trials-efficacy-intelligence reports (2026-08-31, Wave 1) that `Tonvasca_2026.md`'s
citation #26 (Sydhom P, et al. BMC Cardiovasc Disord. 2024;24(1):660.) is quoted/used to support
"low/moderate-intensity statin + ezetimibe" clinical-outcome benefit **surpassing** high-intensity
statin monotherapy without qualifier — but per trials-efficacy's read of the primary publication's
own abstract, that benefit was shown only in the **observational-study-pooled** analysis; the
**RCT-pooled** analysis within the same meta-analysis found **no significant** difference in clinical
endpoints between the two strategies. `Tonvasca_2026.md`'s own slide text (lines ~1006–1037, "RCTs
demonstrate superior lipid lowering and fewer adverse effects... while observational data indicate
better clinical outcomes") does appear to preserve this RCT/observational split for AEs/NODM, but the
MACE/CV-death/all-cause-death/stroke HRs on the preceding slide are not clearly labeled
observational-only in the table trials-efficacy reviewed — this is exactly the kind of Evidence
Hierarchy conflation (`OBSERVATIONAL EVIDENCE` cited as if `DIRECT EVIDENCE`/RCT-grade) that
`CLAUDE.md` §7 exists to catch.

**Decision:** `NEEDS_PI` → **PI DECIDED, 2026-08-31**: do not reword `Tonvasca_2026.md` itself (it
remains a read-only legacy input, `CLAUDE.md` §1). For all `20_EVIDENCE/`, `40_SYNTHESIS/`, and any
future manuscript/slide output, the PI's required framing for Sydhom et al. 2024's clinical-outcome
figures (MACE HR 0.76, CV death HR 0.80, all-cause death HR 0.84, non-fatal stroke HR 0.81) is:

> State the observational-pooled benefit only; the RCT-pooled clinical endpoints were **not**
> statistically significant.

This must be the standing framing anywhere this citation's clinical-outcome claim is used — never
present the pooled HRs as if they were RCT-grade evidence. `VERIFIED_AND_REPLACE` applied: this PI
framing supersedes the earlier `NEEDS_PI` hold.

**Affected files:** `02_SOURCE-INVENTORY.md` (citation #26 row — verified?/notes updated),
`04_OPEN-QUESTIONS.md`. Not `Tonvasca_2026.md` (read-only) or `40_SYNTHESIS/` (Wave 3, not started).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31
(`90_CROSS-SESSION-LOG/trials-efficacy-intelligence.md`, referenced — full detail currently in that
peer's unmerged worktree; this entry records the Director-facing summary only).

**Approved by:** Research Director (Wave 1).

---

## Decision 2026-08-31-07

**Issue:** trials-efficacy-intelligence located two new sources during Wave 1 that directly answer
Search Protocol item 5 (`CLAUDE.md` §5, "2 mg vs 4 mg, and add-ezetimibe vs dose escalation"),
previously logged as "not yet located" (source T-004 in `02_SOURCE-INVENTORY.md`): Tsujita K, et al.
J Atheroscler Thromb. 2023 (4-arm Japanese RCT: pitavastatin 2 mg / 4 mg / 2 mg+ezetimibe 10 mg /
4 mg+ezetimibe 10 mg; 12-week LDL-C % change reported as −39.5 / −45.2 / −51.4 / −57.8 respectively,
per trials-efficacy's report) and its 52-week open-label extension, Ako J, et al. 2024.

**Decision:** `VERIFIED_AND_REPLACE` (for the "not yet located" status of T-004 only — the underlying
numeric figures themselves are newly added, not replacing any prior verified value). Add both as new
rows in `02_SOURCE-INVENTORY.md`, update T-004's status from "not yet located" to "located,
trials-efficacy-verified against PubMed-indexed primary publication (HIGH confidence per peer
report; Director has not independently re-verified)."

**Affected files:** `02_SOURCE-INVENTORY.md`.

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 1).

---

## Decision 2026-08-31-10

**Issue:** safety-pharmacology-intelligence identified Singh H, et al. 2024 (PMID 39587804) as the
actual source behind `pitavastatin topic.md`'s generic reference to "a 2024 systematic review/
meta-analysis" on pitavastatin's new-onset-diabetes (NODM) risk vs. atorvastatin/rosuvastatin (RR
0.86 vs. atorvastatin, RR 0.77 vs. rosuvastatin, per its report). This is a **different 2024
publication** from citation #26 (Sydhom P, et al., BMC Cardiovasc Disord. 2024;24(1):660), which
covers a different comparison (low/moderate-statin+ezetimibe vs. high-intensity statin monotherapy,
not pitavastatin-specific NODM).

**Decision:** `VERIFIED_AND_REPLACE` — T-003 in `02_SOURCE-INVENTORY.md` updated from "not yet
located" to located, citing Singh H et al. 2024 specifically. Explicit rule going forward: **Singh
2024 and Sydhom 2024 must never be conflated** in any `20_EVIDENCE/`, `40_SYNTHESIS/`, or manuscript
output — they answer different Search Protocol items (item 3 glycemic outcomes vs. item 9/Level 2
combination-strategy evidence respectively) and citing one for the other's claim would be a
citation-misattribution error.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-003 row).

**Source:** safety-pharmacology-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 1).

---

## Decision 2026-08-31-11

**Issue:** trials-efficacy-intelligence reports that `Tonvasca_2026.md`'s slide covering the
Katzmann JL et al. 2022 (T-012/TE-010) FDC-vs-separate-pills comparison prints **two different,
internally inconsistent cohort sizes** for the same comparison: the slide header states
"n=6,429 FDC / n=533 separate pills," while the results table immediately below states
"n=1,639 FDC / n=796 separate pills" — the relative ordering is even reversed between the two
(6,429 > 533 vs. 1,639 < 796). The primary publication's own abstract gives only the overall study
N (311,242, across all non-statin LLT types), not this specific subgroup's *n*, so trials-efficacy
could not resolve which pair (or neither) is correct without the paper's own tables.

**Decision:** `SOURCE_CONFLICT` — neither value is silently chosen or "corrected." Both are preserved
exactly as printed, per the Numeric Integrity Rule (`CLAUDE.md` §9). **No *n* from this specific
comparison may be cited in `20_EVIDENCE/`, `40_SYNTHESIS/`, or any manuscript output until Wave 2
full-text acquisition of Katzmann 2022 resolves it.** The four already-verified percentage/p-value
figures (28.4% vs. 19.4% LDL-C reduction, p<0.0001; 31.5% vs. 21.0% attainment) are unaffected and
may be cited, since they were independently confirmed against the primary abstract and do not
depend on which cohort-size pair is correct.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-012 row), `04_OPEN-QUESTIONS.md` (Wave 2 priority
item added).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31 (its own
`20_EVIDENCE/trials-efficacy/unresolved-questions.md`, Q7).

**Approved by:** Research Director (Wave 1).

**PI confirmation, 2026-08-31**: remains unresolved until Katzmann 2022 full text is obtained — no
change. Added to Wave 2 trials-efficacy dispatch as a named acquisition target (see Wave 2 dispatch
log, `90_CROSS-SESSION-LOG/`).

**Wave 2 update, 2026-08-31**: trials-efficacy confirmed `BLOCKED_FOR_SOURCE` — no OA location via
Unpaywall; a direct HTTP check on the Crossref-supplied Springer `pdf_url` returned an HTML
access-restriction page, not a PDF. No workaround attempted. Remains unresolved; genuine
institutional/manual access would be required.

**RESOLVED, 2026-08-31 (superseding `SOURCE_CONFLICT` above with `NO_CHANGE`):** safety-pharmacology
obtained the primary source lawfully (see Decision 2026-08-31-20) and located both *n* pairs
directly in the paper's own tables — **neither is an error; they measure two different subsets of
the same study**:
- **n=6,429 (FDC) / n=533 (SPC)** = the paper's Table 1, "baseline characteristics for patients
  treated by general practitioners in 2018" — a GP-only, single-year prescription-count snapshot
  (out of that table's GP total N=136,494). The paper's Table 2 gives the parallel
  cardiologist-only figures (FDC n=682, SPC n=51) — neither of `Tonvasca_2026.md`'s two printed
  pairs matches this one, so it is not a third candidate.
- **n=1,639 (FDC) / n=796 (SPC)** = the paper's Graphic Abstract / Figure 6 — the pooled
  (GP+cardiologist) subgroup with paired pre/post LDL-C measurements available, i.e. the exact
  sample the paper's headline LDL-C result is built on (FDC −28.4%/−40.0 mg/dL vs. SPC
  −19.4%/−27.5 mg/dL, p<0.0001).

**Director's own direct read of `Tonvasca_2026.md`** (lines 2311–2345) confirms which pairing the
slide actually uses where: the slide's header/setup line ("Statin + ezetimibe FDC (n=6,429) vs...
separate pills (n=533)") introduces the comparison generally using the GP-2018 prescription-count
figure, while the **results table itself explicitly re-labels its own rows** "Statin + ezetimibe
FDC (**n=1,639**)" / "...separate pills (**n=796**)" directly alongside the −28.4%/−19.4% and
31.5%/21.0% figures. So the slide is not internally contradictory in the sense originally described
(it does not print the same claim twice with conflicting numbers) — it uses two different,
individually-correct cohort definitions for two different purposes (general framing vs. the specific
result table) without explaining the distinction to the reader. The earlier "internally
inconsistent... reversed ordering" characterization is withdrawn as an overstatement; the more
accurate description is "two correct but easily conflated sample definitions in the same source
figure."

**Final decision: `NO_CHANGE`** — no source value is wrong or needs replacing. **The LDL-C
reduction and attainment figures (−28.4%/31.5% vs. −19.4%/21.0%) are unambiguously and correctly
attributable to n=1,639 (FDC) / n=796 (separate pills)**, per both the primary source's own table
labeling and `Tonvasca_2026.md`'s own results-table row labels. The n=6,429/533 figure describes a
broader, separate GP-2018 prescription-prevalence statistic and should not be cited alongside the
LDL-C percentages as if it were their sample size.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-012 row, fully resolved).

**Source:** safety-pharmacology-intelligence cross-session report, 2026-08-31 (full-text table
locations); Research Director's own direct read of `Tonvasca_2026.md` lines 2311–2345.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-12 — PI Wave 2 Authorization (consolidated record)

**Issue:** Five items had been escalated to the PI across Wave 1 (Decisions 06, 08, 04; the
multi-worktree consolidation gap; and the Katzmann *n*-mismatch from Decision 11). The PI reviewed
all five and authorized Wave 2.

**Decisions, verbatim intent preserved:**

1. **Sydhom framing** (Decision 06) — state observational-pooled benefit only; RCT-pooled clinical
   endpoints were not statistically significant. Applied to citation #26 in
   `02_SOURCE-INVENTORY.md`.
2. **research_hub policy** (Decision 08) — keep metadata/search tools only; **permanently** prohibit
   `mcp__research_hub__download_paper` (no Sci-Hub opt-out). `CLAUDE.md` §10 updated from "interim"
   to permanent.
3. **`50_MANUSCRIPT/` ownership** (Decision 04) — Research Director owns coordination until Gate 2.
   `CLAUDE.md` §3 updated.
4. **Multi-worktree consolidation** — PI confirms all four Wave 1 branches plus the Director's Gate
   1 commits were reviewed, secret-scanned, committed, and consolidated into local `main` by the
   supervising Codex process. **This session must not merge branches itself** going forward. Director
   independently verified local `main` does contain all four branches' Wave 1 work (confirmed via
   `git log`) and merged `main` into its own working branch to pick up the specialists' output files
   — this is a same-branch catch-up, not a branch-consolidation act, and does not touch `main`.
   `origin/main` was found to still show only the Wave 0 commit as of this entry (not yet pushed by
   the Codex process) — noted for transparency, not treated as a discrepancy for this session to
   resolve; pushing `main` is likewise reserved to the PI/Codex process.
5. **Katzmann cohort-size discrepancy** (Decision 11) — remains unresolved until full text; carried
   into Wave 2 dispatch below.

**Also authorized/directed by the PI, 2026-08-31:**
- Add `.metadata_cache/` to `.gitignore` (done).
- Create a session registry (`90_CROSS-SESSION-LOG/SESSION-REGISTRY.md`, done).
- Record that `research_hub` and `llamaparse` MCP servers were repaired and `llamaparse` passed a
  live dummy-PDF smoke test (`CLAUDE.md` §10 updated; `00_RUN-MANIFEST.md` connectivity section to
  be updated).
- Add a security TODO (not a credential value) that historical hardcoded `llamaparse` credentials
  exist outside this repository and should be rotated/removed (`CLAUDE.md` §12, done).
- Dispatch Wave 2 focused full-text acquisition to the three existing persistent specialists via
  real `SendMessage` (see Wave 2 dispatch, `90_CROSS-SESSION-LOG/`).

**Affected files:** `CLAUDE.md` (§3, §10, §12), `02_SOURCE-INVENTORY.md` (#26), `.gitignore`,
`00_RUN-MANIFEST.md`, `05_STATUS.md`, `90_CROSS-SESSION-LOG/SESSION-REGISTRY.md`.

**Source:** PI directive, 2026-08-31.

**Approved by:** PI; implemented by Research Director (Wave 2 dispatch).

---

## Decision 2026-08-31-13

**Issue:** guideline-risk-intelligence's Wave 2 attempts to fetch all three assigned priority PDFs
(2026 ACC/AHA at the PI-supplied `ahajournals.org` URL, Taiwan STS 2026 at ScienceDirect, ESC 2025
Focused Update at `academic.oup.com`) all returned HTTP 403 with a **Cloudflare bot-challenge
signature** (`cf-mitigated: challenge`) via both `curl` and `WebFetch` — a bot-detection wall, not a
conventional subscription login wall. Independently corroborated via Europe PMC's own indexed
metadata: all three PMIDs show `is_open_access:False` with no PMCID.

**Decision:** `BLOCKED_FOR_SOURCE` for all three, by automated means. guideline-risk did **not**
escalate to any workaround (e.g., programmatically solving the Cloudflare challenge) — correctly
identified that as crossing from lawful acquisition into detection-evasion territory, out of scope
for any role in this project (`CLAUDE.md` §10's spirit extends here even though Cloudflare, not
Sci-Hub, is the specific wall). Genuine institutional or manual access is the only lawful path
forward for these three documents; recorded as a standing ask to the PI (see `04_OPEN-QUESTIONS.md`).
guideline-risk satisfied the Wave 2 Gate-2 LlamaParse requirement instead using a substitute,
genuinely open-access source (T-014) — see that row in `02_SOURCE-INVENTORY.md` for the caveat that
this substitute does not cover ezetimibe/combination-therapy content, so the "extract
combination-therapy wording" task item remains unfulfilled pending the blocked documents.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-005, T-007, #28 rows), `04_OPEN-QUESTIONS.md`.

**Source:** guideline-risk-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

**Reinforced, 2026-08-31**: guideline-risk re-ran the precise NCBI elink (`linkname=pubmed_pmc`)
check it had already used before the original report — the rigorous method that finds only "this
article has its own PMC copy" links, not the broader "cited-by" list — as a single batched,
explicit confirmation across all 6 remaining guideline PMIDs (2026 ACC/AHA ×2 references, ESC 2025
Focused Update ×2, Taiwan STS 2026, Taiwan Lp(a) 2026/T-006) plus, as a courtesy check,
citation #33 (Chou MT 2022, PMID 36030106, trials-efficacy's domain). **All 7 returned an empty
linkset** — a genuinely negative result via the precise method, not an inference from a broader OA
flag. `BLOCKED_FOR_SOURCE` stands with high confidence for all 7 (T-006 and #34/the base 2019
ESC/EAS guideline confirmed no PMC deposit either, same check). trials-efficacy independently
re-confirmed the same negative result for #33 via its own retry shortly after (see the Wave 2
trials-efficacy follow-up log), gaining a fuller Europe PMC abstract in the process — convergent,
not redundant, confirmation.

---

## Decision 2026-08-31-23

**Issue:** Using the same precise elink method proactively, guideline-risk found genuine PMC
deposits for 2 of the remaining Search-Protocol-item-6 guideline targets and obtained/parsed full
text: the 2023 TSC CCS guideline (Ueng KC et al., citation #30, PMC9829849) and the ADA 2025
Standards of Care Ch.10 (citation #32, PMC11635050). It also found and parsed a genuinely
open-access secondary review (Katzmann & Laufs, Curr Atheroscler Rep 2026, PMC12945982) that closely
paraphrases and cites the still-blocked ESC 2025 Focused Update's own upfront-combination-therapy
recommendation, substantively advancing the "extract combination-therapy wording" task even without
the primary ESC 2025 document itself.

**Decision:** `VERIFIED_NEW_SENSITIVITY` for #30/#32 (content-verified, not just citation-verified,
against primary text). Logged as new source **T-021** for the Katzmann & Laufs 2026 review, with
an important caveat preserved rather than smoothed over: that review's own "no upfront combination
in US guidelines" comparison cites the **old 2018 AHA/ACC guideline**, not the 2026 update — this
must not be used as if it described the current (2026) US guideline's actual position, which
remains unconfirmed pending the still-blocked primary document (#28).

**Affected files:** `02_SOURCE-INVENTORY.md` (#30, #32 rows updated; new T-021 row).

**Source:** guideline-risk-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-24

**Issue:** While independently verifying Decision 2026-08-31-11's resolution by reading
`Tonvasca_2026.md` lines 2280–2349 directly, the Director found a citation not previously catalogued
in `02_SOURCE-INVENTORY.md`: Wei Q, et al. Front Pharmacol. 2023;14:1156081 (a 61-study
meta-analysis on FDC-vs-free-equivalent-combination adherence), used in the slide immediately
preceding the Katzmann 2022 slide.

**Decision:** Logged as new source **T-022**, assigned to safety-pharmacology-intelligence for
verification (adherence-outcome domain, consistent with the existing T-009 cluster assignment).

**Affected files:** `02_SOURCE-INVENTORY.md` (new T-022 row).

**Source:** Research Director's own direct read of `Tonvasca_2026.md`.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-25

**Issue:** trials-efficacy retried citation #33 (Chou MT 2022) per the Europe-PMC-PMCID method tip:
Europe PMC indexes its metadata (PMID 36030106) but shows an empty PMCID and `is_open_access:
False` — genuinely not PMC-deposited, converging with guideline-risk's independent elink check
(Decision 2026-08-31-13 reinforcement). `BLOCKED_FOR_SOURCE` stands, now doubly confirmed by two
independent methods. Europe PMC's abstract copy was fuller than Crossref's, yielding one new detail:
a stated *trend* toward greater LDL-C lowering in elderly (≥65y) vs. younger patients, with no
CI/p-value given — correctly flagged as a trend only, not a confirmed subgroup finding. While
checking, trials-efficacy also found two new, previously-uncatalogued sources: **TE-013** (Lu YW,
Fang CC, Cheng YT, "Real-World Safety and Efficacy of a Pitavastatin-Ezetimibe Combination Therapy
in Taiwanese Patients after PCI," Acta Cardiol Sin. 2026;42(3), DOI
10.6515/ACS.202605_42(3).20251013A — Taiwan real-world retrospective cohort, N=120, post-PCI,
pitavastatin 4mg+ezetimibe 10mg, 12-month LDL-C reduction 32.54%, HbA1c/TyG-index changes in the
diabetic subgroup; its "zero AEs recorded" claim flagged as plausible retrospective
under-ascertainment, not to be weighted the same as an RCT's AE reporting) and **TE-014** (Abbas MS
et al., "Combination pitavastatin-ezetimibe therapy for hypercholesterolemia and mixed
dyslipidemia: a systematic review and meta-analysis," Future Cardiol. 2026;22(6):607-619, DOI
10.1080/14796678.2026.2676249, PROSPERO CRD420251233057 — possibly the **first formal meta-analysis
specific to the pitavastatin+ezetimibe FDC question**, eligibility criteria closely matching
TE-001/TE-002; abstract's Results section has no numeric effect sizes yet, LOW confidence on actual
findings). Both new sources have Europe PMC PMCID entries (PMC13202365, PMC13288897) but report
`is_open_access: False`; trials-efficacy correctly did not attempt download without checking in
first.

**Decision:** Logged as new sources **T-023** (Lu YW et al. 2026) and **T-024** (Abbas MS et al.
2026). T-024 is flagged as the **highest-priority Wave 3 full-text target** — if it genuinely pools
TE-001/TE-002-type FDC trials, it would meaningfully strengthen the Level 1 evidence base described
in `pitavastatin topic.md` §6, but nothing about it can be cited yet since the abstract has no
numbers. Full-text pursuit for T-023/T-024 held for Wave 3 pending Director/PI direction on whether
Wave 2 continues or a formal Wave 3 is opened.

**Affected files:** `02_SOURCE-INVENTORY.md` (new T-023, T-024 rows; #33 row reinforced).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-26

**Issue:** safety-pharmacology verified T-022 (Wei Q et al. 2023, Front Pharmacol — 61-study
FDC-vs-free-equivalent adherence meta-analysis, general/cross-disease) and found a new, more
directly on-topic source while searching for it: Samnaliev M et al. 2025 (Front Cardiovasc Med,
THIN-database retrospective cohort, N=15,643, **rosuvastatin/ezetimibe FDC vs. free-combination
specifically** — persistence HR 0.54, adherence OR 3.00, ~10% greater LDL-C reduction in
persistent/adherent patients).

**Decision:** T-022 confirmed `VERIFIED`, tagged `INDIRECT EVIDENCE` (cross-disease-general).
Samnaliev logged as new source **T-025**, also tagged `INDIRECT EVIDENCE` — same
different-statin caveat class as RACING (rosuvastatin, not pitavastatin) — but flagged as more
directly relevant to this project's FDC-adherence narrative than T-022 since it is statin+ezetimibe-
specific. Also: the Director discovered it had never actually forwarded full citation strings for
the T-009 adherence cluster to safety-pharmacology (only author/year fragments in an earlier
message) — resent in full; corrected, no content was lost since `02_SOURCE-INVENTORY.md` always had
the complete strings.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-022, new T-025 rows).

**Source:** safety-pharmacology-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-14

**Issue:** During the same Wave 2 attempt, a `WebFetch` call against the ESC 2025 Focused Update's
Oxford Academic landing page returned a response that explicitly stated the article was paywalled,
then went on to confidently quote specific quantitative content and a page/section locator anyway —
consistent with the underlying summarization model confabulating plausible content rather than
performing genuine extraction.

**Decision:** guideline-risk-intelligence **discarded the fabricated content entirely** — it was
never recorded in any output file, never cited, and is not part of this repo's evidence base. This
Director records the incident (not the fabricated content itself) for institutional memory and adds
a general caution for all roles going forward — see `CLAUDE.md` §9 ("Tool-confabulation caution").
This is exactly the discipline the project's Numeric Integrity Rule and Evidence Hierarchy exist to
enforce, extended from source-printed numbers to tool-summarized content.

**Affected files:** `CLAUDE.md` §9, `02_SOURCE-INVENTORY.md` (T-007 row, informational note).

**Source:** guideline-risk-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2). Commended, not corrected — this is exactly the
adversarial self-scrutiny the project needs more of (Runbook §30).

---

## Decision 2026-08-31-15

**Issue:** guideline-risk-intelligence, while reading T-014's (Razavi/Blumenthal 2026 editorial)
reference list, found a citation for the REPRIEVE trial (Grinspoon SK, Fitch KV, Zanni MV, et al.,
"Pitavastatin to Prevent Cardiovascular Disease in HIV Infection," N Engl J Med. 2023;389:687-699)
— a pitavastatin cardiovascular-**outcome** RCT not currently in `02_SOURCE-INVENTORY.md`.
guideline-risk explicitly flagged this as outside its own domain and not independently verified
beyond what's printed in the reference list, and routed it to the Director rather than claiming it.

**Decision:** `VERIFIED_AND_REPLACE` is not applicable (this is a genuinely new source, not a
correction) — logged as **new source T-015**, assigned to trials-efficacy-intelligence for
verification and evidence-hierarchy placement. Important distinction to hold going forward:
REPRIEVE is pitavastatin **monotherapy** in an **HIV population**, evidentially distinct from both
HIJ-PROPER (pitavastatin+ezetimibe combination, general dyslipidemia population) and RACING
(rosuvastatin+ezetimibe combination) — none of the three should be conflated with each other in any
future synthesis.

**Affected files:** `02_SOURCE-INVENTORY.md` (new T-015 row).

**Source:** guideline-risk-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-16

**Issue:** trials-efficacy obtained and LlamaParse-parsed the full text of T-004a (Tsujita K et al.
2023) — one of the two Gate-2 LlamaParse demonstrations, and on the actual assigned target this
time (PMC's proof-of-work anti-bot challenge blocked the two PMC IDs supplied; trials-efficacy did
not attempt to solve it and instead used the lawful J-STAGE PDF links, correctly). Full text
resolved the exact statistical structure: comparisons are pairwise MMRM, not pooled. The
K-924-HD-vs-K-924-LD comparison (dose-response *within* the FDC) was formally tested and
significant (−6.4%, 95% CI −9.6 to −3.2, p≤0.001). Critically, the comparison
`pitavastatin topic.md`'s own framing highlights as a headline clinical question — "add ezetimibe
or double the statin?" (K-924 LD, i.e. pitavastatin 2mg+ezetimibe10, vs. pitavastatin 4mg alone) —
was **not formally tested** in this trial; only a descriptive point-estimate difference exists
(−51.4% vs. −45.2%), with no reported p-value/CI for that specific pairwise comparison.

**Decision:** `VERIFIED_NEW_SENSITIVITY` — the trial answers the FDC-dose-response question directly
but does **not** answer the specific "add-on vs. dose-escalation" question as a formally tested
head-to-head comparison. **Any `40_SYNTHESIS/` or manuscript output using this trial for the
"add ezetimibe or double the statin?" framing must present the −51.4% vs. −45.2% figures as a
descriptive/point-estimate difference only — never as a statistically significant result —** and
should note the K-924-HD-vs-LD within-FDC comparison separately as the trial's actual formally
tested finding.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-004a row).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31 (its own
`10_DATA/trials-efficacy/wave2-fulltext-extraction.md`).

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-17

**Issue:** trials-efficacy's full-text read of T-004b (Ako J et al. 2024, the 52-week open-label
extension) found that the abstract's "a single adverse drug reaction" framing, taken alone, would
understate the study's actual safety picture: overall AE incidence was 59.6% (65/109 patients),
with 12 serious AEs (11.0%) — but only 1 event across the whole study was adjudicated as a
drug-related ADR (a CK elevation), and none of the serious AEs were adjudicated as drug-related.

**Decision:** `VERIFIED_NEW_SENSITIVITY` — the underlying "well-tolerated" conclusion still holds
once the AE-vs-ADR (adjudicated-causality) distinction is understood, but **any output citing this
study's safety data must carry both figures (overall AE incidence AND the ADR-adjudication result),
never the ADR figure alone presented as if it were the full AE picture.** This is a methodological
distinction worth generalizing: "adverse event" and "adjudicated adverse drug reaction" are not
interchangeable, and a source's own abstract may lead with the narrower, more favorable framing.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-004b row).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-18

**Issue:** trials-efficacy fully verified T-015 (REPRIEVE trial, Grinspoon SK et al., NEJM
2023;389(8):687-699) against PubMed/Crossref — matches exactly. Key result: N=7,769, pitavastatin
4mg vs. placebo in HIV-positive patients, trial stopped early for efficacy, primary MACE HR 0.65
(95% CI 0.48–0.90, P=0.002). trials-efficacy also flagged (without resolving) a cross-domain nuance:
REPRIEVE's diabetes signal (5.3% pitavastatin vs. 4.0% placebo, an absolute-risk, placebo-controlled
comparison) uses a different comparator/framing than safety-pharmacology's Singh 2024 (T-003) NODM
meta-analysis (relative risk vs. other statins) — not contradictory, but not directly comparable
either.

**Decision:** `VERIFIED_AND_REPLACE` (T-015's "found, not verified" status superseded by full
verification). REPRIEVE stands as a fourth, independent reference point in the evidence base —
pitavastatin **monotherapy**, HIV population, vs. placebo — distinct from HIJ-PROPER,
RACING, and the Katzmann/Tsujita/Ako FDC-dose-comparison trials. The diabetes-signal
cross-domain nuance is logged for safety-pharmacology's awareness but not adjudicated by the
Director — that synthesis judgment belongs to whichever role eventually writes the NODM section of
`40_SYNTHESIS/`.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-015 row).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-19

**Issue:** trials-efficacy found a secondhand citation to the REAL-CAD trial (pitavastatin 4mg vs.
1mg, Japanese CAD patients, HR 0.81, 95% CI 0.69–0.95) inside T-004a's (Tsujita 2023) discussion
section — not yet independently verified, logged as its own Q8, and asked whether to pursue it
itself or have it routed elsewhere.

**Decision:** Logged as new source **T-016**. **Director authorizes trials-efficacy to pursue
verification itself** — this is squarely a dose-comparison/hard-outcome trial within its own
domain, and it was found while already deep in directly relevant full text, so re-routing it would
just add a round-trip with no benefit.

**Affected files:** `02_SOURCE-INVENTORY.md` (new T-016 row).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-20

**Issue:** trials-efficacy reported T-012 (Katzmann JL et al. 2022) as `BLOCKED_FOR_SOURCE` (no OA
via Unpaywall; a direct HTTP check on the Springer `pdf_url` returned an access-restriction page).
Shortly after, safety-pharmacology — working independently, on the same citation, same PMID
32949286 — reported it obtained the full text lawfully via **Europe PMC directly**, finding PMCID
PMC8873069, CC BY 4.0, genuinely open access, and successfully LlamaParse-parsed it.

**Decision:** `VERIFIED_AND_REPLACE` — T-012's status updated from `BLOCKED_FOR_SOURCE` to full text
obtained. Not a contradiction between the two peers: different lookup methods (Unpaywall +
publisher direct link vs. Europe PMC's own PMCID index) gave different results for the same paper.
**Methodological lesson generalized to guideline-risk and trials-efficacy for their own still-blocked
sources** (Taiwan STS 2026, 2026 ACC/AHA, ESC 2025 Focused Update, Chou MT 2022): try a direct Europe
PMC PMCID lookup specifically before concluding `BLOCKED_FOR_SOURCE`, since it succeeded here where
other routes failed. The cohort-size numeric-integrity flag from Decision 2026-08-31-11 can likely
now be resolved from this full text — assigned to whichever role reads it first to report back.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-012 row).

**Source:** trials-efficacy-intelligence and safety-pharmacology-intelligence cross-session reports,
2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-21

**Issue:** safety-pharmacology re-verified the T-010 DDI matrix (LIVALO/DailyMed label) directly
against DailyMed in Wave 2 (not a secondary transcription): cyclosporine/erythromycin/rifampin/
gemfibrozil figures all exact-matched the Wave 1 report (no drift). Two refinements: clarithromycin
upgraded from "not found as fetched" to `CONFIRMED_ABSENT_FROM_LABEL` (checked the full label text,
not just Section 7); fenofibrate's figures precisely located in Section 12.3 Table 3, not Section 7
as the Wave 1 report implied. New content captured: fibrate-class (general), niacin, and colchicine
caution language.

**Decision:** `VERIFIED_AND_REPLACE` for the location/completeness refinements; `NO_CHANGE` for the
five previously-reported figures (re-confirmed, not altered).

**Affected files:** `02_SOURCE-INVENTORY.md` (T-010 row).

**Source:** safety-pharmacology-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-22

**Issue:** safety-pharmacology obtained and cross-verified Tramontano D et al. 2025 (Drugs,
PMC12098426, CC BY-NC 4.0, T-018) against the FDA label directly, resolving most of the CKD-dosing
gap flagged in Wave 1: pitavastatin 1mg starting/2mg max dose in eGFR 15–59 or hemodialysis, no
adjustment needed for eGFR ≥60, and — per this review's own comparison table — pitavastatin has the
lowest CKD dose ceiling of all 7 statins tabulated. Also found (abstract-only, not open access):
Li H, Li J et al. 2026 (T-017), an elderly-specific pitavastatin-vs-atorvastatin NODM cohort
(n=126, 0% vs. 10.29%) partially filling the Wave 1 elderly-population glycemic-outcomes gap.

**Decision:** `VERIFIED_NEW_SENSITIVITY` — T-018's CKD-dosing figures accepted as cross-verified
against the primary regulatory source (the FDA label), not merely a secondary review's own claim.
T-017 accepted at MODERATE confidence (abstract-level only). **Remaining open gap, explicitly not
addressed by any source found so far: FDC-specific (pitavastatin+ezetimibe combined) CKD dosing** —
carried forward in `04_OPEN-QUESTIONS.md`.

**Affected files:** `02_SOURCE-INVENTORY.md` (new T-017, T-018 rows).

**Source:** safety-pharmacology-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 2).

---

## Decision 2026-08-31-08

**Issue:** guideline-risk-intelligence reports that calling `mcp__research_hub__download_paper`
(for the Taiwan STS 2026 consensus, DOI 10.1016/j.jfma.2026.04.111, itself confirmed open-access/
CC-licensed) produced a tool response stating it searches "ArXiv, CrossRef, SSRN, Sci-Hub, and
others" — with no parameter exposed to exclude Sci-Hub from that internal search. The call returned
no PDF/content, so nothing Sci-Hub-sourced entered the repo, but the tool itself queries a prohibited
source as part of its normal operation with no opt-out.

**Decision:** `NEEDS_PI` for final policy, but Director is imposing an **interim precautionary
restriction effective immediately** (tightening, not loosening, an existing safety rule — within
Director authority per Runbook §5 without needing to pause for PI sign-off, though PI visibility is
still warranted given the subject): `mcp__research_hub__download_paper` must not be called by any
role in this project until the PI decides otherwise. `research_hub`'s metadata-only tools (e.g.
`search_papers`) remain permitted. `CLAUDE.md` §10 updated accordingly. Reported to the PI directly
in this turn's response, per the harness's Sci-Hub/unauthorized-access sensitivity guidance.

**Reason:** `CLAUDE.md` §10 (itself instantiating the PI's explicit instruction) prohibits Sci-Hub
"for any purpose, under any framing" — a tool whose own internal search fan-out includes Sci-Hub
with no disable option falls inside that framing even when the specific call obtained no content.
guideline-risk-intelligence's handling was correct: it did not use the (empty) result, did not
retry via a different route, and escalated instead of deciding unilaterally — commended, not
corrected.

**Affected files:** `CLAUDE.md` §10.

**Source:** guideline-risk-intelligence cross-session report, 2026-08-31
(`20_EVIDENCE/guideline-risk/unresolved-questions.md`, item 2 — read via `git show` against the
peer's pushed-but-unmerged branch `origin/worktree-pit-eze-guideline-risk-wave1`).

**Approved by:** Research Director (Wave 1), flagged to PI.

---

## Decision 2026-08-31-09

**Issue:** guideline-risk-intelligence reports citation #27 (2025 Taiwan lipid clinical pathway
consensus, 李貽恒、石崇良, 內科學誌 2024;35:426-430) as printed in `Tonvasca_2026.md` has a DOI
transcription discrepancy: printed as `10.6314/JIMT.202412_35(6).04.04` (doubled `.04` suffix);
independently located correct DOI is `10.6314/JIMT.202412_35(6).04` (single suffix). Title/authors/
journal/volume/issue/pages otherwise match.

**Decision:** `VERIFIED_AND_REPLACE` — for the DOI field only. The citation's identity is confirmed
correct; only the DOI string as printed in the legacy slide source contains a transcription error.
Use the corrected DOI (`10.6314/JIMT.202412_35(6).04`) in any `20_EVIDENCE/`/`40_SYNTHESIS/` output
going forward; `Tonvasca_2026.md` itself is not edited (read-only legacy input, `CLAUDE.md` §1) —
this correction lives in `02_SOURCE-INVENTORY.md` and this log entry, not in the source file.

**Affected files:** `02_SOURCE-INVENTORY.md` (citation #27 row).

**Source:** guideline-risk-intelligence cross-session report, 2026-08-31.

**Approved by:** Research Director (Wave 1).

---

## Decision 2026-08-31-27 — Gate 2 declared READY_WITH_PENDING_ITEMS

**Issue:** All three specialists' Wave 2 assignments are complete. Six sources remain
`BLOCKED_FOR_SOURCE` (Taiwan STS 2026/T-005, Taiwan Lp(a) 2026/T-006, base 2019 ESC/EAS/#34, 2026
ACC/AHA/#28, ESC 2025 Focused Update/T-007, citation #33/Chou MT 2022's safety tables). Both
Gate-2-required LlamaParse demonstrations succeeded (guideline-risk on a substitute source, T-014;
trials-efficacy on the actual assigned target, T-004a/Tsujita 2023).

**Decision:** Per the PI's existing Gate 2 exit criteria (Decision 2026-08-31-12): `READY_WITH_
PENDING_ITEMS` is declared now. **Explicit, PI-directed framing**: the PI has instructed that no
assumption be made that these six sources can be supplied — they remain recorded as `NEEDS_PI`/
`BLOCKED_FOR_SOURCE` in `04_OPEN-QUESTIONS.md`, not treated as pending resolution. **No Wave 3 is
opened** — T-024 (Abbas 2026, flagged as the highest-priority Wave 3 candidate) and all other
not-yet-obtained new-source full texts (T-003, T-012's cohort-n is resolved but T-003/Singh 2024
itself remains blocked, T-023, T-025's fuller text, etc.) are held, not pursued further, pending
separate PI authorization to reopen. A Wave 2 Challenge Round was conducted by the Director across
all four Runbook §30 angles (guideline/trials/safety/methods) — see
`30_METHODS/shared/wave2-challenge-round.md` — surfacing four priority findings to carry into any
future Wave 3: (1) Taiwan STS 2026's "ezetimibe as first add-on" framing remains unverified against
primary text; (2) REPRIEVE/REAL-CAD-to-FDC conflation is the highest-likelihood overclaim risk;
(3) FDC-specific CKD dosing is the highest-stakes safety gap; (4) Singh 2024's RCT-vs-observational
pooling is an unresolved parallel risk to the already-PI-decided Sydhom framing. None of these block
Gate 2 under the PI's own stated criteria.

**Affected files:** `05_STATUS.md` (Gate formally set), `04_OPEN-QUESTIONS.md` (challenge-round
findings added), `30_METHODS/shared/wave2-challenge-round.md` (new), `99_FINAL-QA.md` (status note
only — Wave 4 audit itself not started).

**Source:** PI directive, 2026-08-31.

**Approved by:** PI; implemented by Research Director.

---

## Decision 2026-08-31-28 — Post-Gate-2 checkpoint: citation #35 evidence verified, staleness in
04_OPEN-QUESTIONS.md/05_STATUS.md corrected, branch-consolidation gap noted

**Issue:** A narrow post-Gate-2 checkpoint reviewed guideline-risk-intelligence's two commits
(`d5e5131`, `31ddebc`, on branch `worktree-pit-eze-guideline-risk-wave1`) completing citation #35
(Huang PH et al. 2022 Taiwan primary-prevention guideline) — full text obtained lawfully from the
Taiwan Society of Lipids and Atherosclerosis's own `tas.org.tw` mirror (no PMC deposit; same pattern
as #30/#32), CC BY 4.0 confirmed verbatim in the parsed text, exact COR/LOE-graded recommendation
text extracted (four risk-stratified primary-prevention LDL-C targets: <100/<115/<130/<160 mg/dL).

Found on verification: (1) `02_SOURCE-INVENTORY.md` row #35 **already correctly** states "Full text
obtained Wave 2" with matching detail (folded in by the Director's own Gate-2-declaration commit,
`8543960`, from the specialist's report) — no correction needed there. (2) `04_OPEN-QUESTIONS.md`
and `05_STATUS.md` (Wave 2 follow-up round section) had **not** been updated to match — both still
described #35 as "not yet attempted"/"queued next," contradicting `02_SOURCE-INVENTORY.md` within
the same branch. Genuine staleness, corrected this checkpoint. (3) The underlying specialist-owned
evidence files this finding rests on (`20_EVIDENCE/guideline-risk/wave2-item6-extraction.md` §D,
`30_METHODS/guideline-risk/fulltext-manifest.md`'s Huang entry) exist only on
`worktree-pit-eze-guideline-risk-wave1` (commits `d5e5131`/`31ddebc`), which is **not** an ancestor
of this integration branch (`worktree-wave0-init`) — that branch has continued past the Wave 1
consolidation point (Decision 2026-08-31-12 item 4) without a further merge. The Director's
`02_SOURCE-INVENTORY.md` claim is accurate (verified independently against the specialist's own
commit content) but its supporting primary-extraction file is not yet present in this branch's own
`20_EVIDENCE/`/`30_METHODS/` tree — a provenance-location gap, not a content error. No merge
performed by this checkpoint (out of scope; flagged for the PI/Director's ordinary consolidation
process).

No secrets found in either commit (`git grep` clean). No PDF/parsed-markdown tracked (both files
confirmed gitignored, untracked). No impact on the six existing `BLOCKED_FOR_SOURCE` items — #35 was
never one of the six (it was Item 6's 5th target, already known "not yet attempted," now resolved).

**Decision:** `VERIFIED_AND_REPLACE` — `04_OPEN-QUESTIONS.md`'s #35 bullet moved from Open to
Resolved; `05_STATUS.md`'s stale "1/5 (#35) queued next" line corrected to "3/5 complete." No change
to `02_SOURCE-INVENTORY.md` (already correct), the six `BLOCKED_FOR_SOURCE` items, Gate 2 status, or
Wave 3 (not opened — out of scope for this checkpoint).

**Affected files:** `04_OPEN-QUESTIONS.md`, `05_STATUS.md`, `90_CROSS-SESSION-LOG/
2026-08-31_post-gate2-checkpoint-row35.md` (new).

**Source:** PI-directed narrow post-Gate-2 checkpoint, 2026-08-31.

**Approved by:** Research Director.

---

## Decision 2026-08-31-28 — PI authorizes Wave 3 (Synthesis)

**Issue:** Gate 2 was declared `READY_WITH_PENDING_ITEMS` (Decision 2026-08-31-27) with Wave 3
explicitly not opened. The PI has now reviewed that state and authorized Wave 3.

**Decision:** Wave 3 (Synthesis) is opened. **Scope, explicit PI decision**: synthesis work in
`40_SYNTHESIS/` is authorized; **manuscript/slide drafting in `50_MANUSCRIPT/` is NOT authorized
this wave** — the Decision 2026-08-31-04/2026-08-31-12 question of whether a dedicated manuscript
role is ever created remains separately unresolved and is not implicitly answered by opening Wave 3.
All Claude Code work this wave, including every resumed/dispatched peer session, must run on model
**sonnet**. The Director's own branch was brought up to current local `main` via the established
safe merge-catch-up pattern (merge `main` into the Director's working branch; no merge/push of
`main` itself — unchanged policy from Decision 2026-08-31-12 item 4). A cross-session health check
via `ListAgents` confirmed this session is the sole live `pit-eze-research-director` and all three
specialist identities remain reachable by name — used directly, no replacement identities created
(Golden Rule 1). `openevidence` MCP remains disconnected in this session; recorded as a tool blocker,
not treated as a project blocker — lawful PubMed/PMC/Crossref/Unpaywall/paper-search/`research_hub`
metadata-search paths remain the primary Wave 3 acquisition routes. Where a dispatched specialist's
own session does have a working OpenEvidence relay, **at most one bounded discovery pass** on the
six still-blocked sources (T-005, T-006, #34, #28, T-007, #33) is authorized — discovery/
corroboration only, never a primary-source substitute, and must not weaken any `BLOCKED_FOR_SOURCE`
status unless an independently lawful primary source is actually obtained.

**Affected files:** `05_STATUS.md` (Wave 3 opened), `04_OPEN-QUESTIONS.md` (Wave 3 dispatch targets
added), `90_CROSS-SESSION-LOG/` (dispatch log).

**Source:** PI directive, 2026-08-31.

**Approved by:** PI; implemented by Research Director.

---

## Decision 2026-08-31-29

**Issue:** safety-pharmacology's Wave 3 report on its four dispatched tasks: (1) Singh 2024 (T-003)
RCT-vs-observational disaggregation — re-attempted via Europe PMC PMCID lookup, still
`is_open_access:false`/no PMCID, genuinely cannot be resolved without full text (a source-access
limitation, not a declined judgment call). (2) T-025 (Samnaliev 2025) — turned out to be open access
after all (PMID 40454236, PMCID PMC12123881, CC BY); full text obtained and parsed, surfacing a new
overall-vs-subgroup inconsistency: the paper's own pooled cohort found no significant persistence/
adherence-MACE association, but its R10/E10 dose-specific subgroup shows a positive MACE signal
(HR 0.58, 95% CI 0.35–0.96, p=0.030) not replicated in the overall analysis. (3) FDC-specific CKD
dosing — nothing found; offered a plausible inference (FDC likely inherits its statin component's
monotherapy CKD guidance) explicitly labeled `EXPERT INTERPRETATION`, not a finding — gap stays
`BLOCKED_FOR_SOURCE`. (4) BCRP quantitative data — found two PBPK/simulation papers (T-026, Hong
2025, pitavastatin AUC ratio 2.24 with a multi-mechanism perpetrator, not an isolated BCRP
inhibitor; T-027, Wu 2025, ESRD reduces hepatic OATP1B1/3 ~75% in a PBPK model, mechanistic
rationale for the CKD dose cap but no new empirical pitavastatin number) — both correctly tagged
`MECHANISTIC SUPPORT`/simulation-based, not clinical DDI data. (5) The authorized bounded OpenEvidence
discovery pass could not be executed — `openevidence` remains `CONNECTION_CLOSED` in
safety-pharmacology's session too (a tool blocker, not a discretionary skip).

**Decision:** `VERIFIED_AND_REPLACE` for T-025 (abstract-only → full text obtained, with the
subgroup caveat now mandatory whenever the R10/E10 MACE HR is cited). New sources T-026, T-027
logged, both `MECHANISTIC SUPPORT`. Singh 2024's RCT-vs-observational question (Wave 2 Challenge
Round finding #4) **remains genuinely unresolved** — not a framing failure, a hard source-access
limit; carried forward as `BLOCKED_FOR_SOURCE`, not treated as abandoned. FDC-specific CKD dosing and
true isolated-BCRP-inhibitor fold-change both remain open gaps, now with the closest available
proxy evidence on record (T-026/T-027) explicitly marked as not equivalent to a real answer.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-025 updated; new T-026, T-027 rows).

**Source:** safety-pharmacology-intelligence cross-session report, 2026-08-31 (Wave 3).

**Approved by:** Research Director (Wave 3).

---

## Decision 2026-08-31-30

**Issue:** trials-efficacy's Wave 3 report on its four dispatched tasks. (1) T-024 (Abbas 2026):
three lawful acquisition attempts (Unpaywall, Taylor & Francis figshare supplementary link — hit an
AWS WAF bot-challenge, not solved — and a ResearchGate mirror via `tavily_extract`) all failed;
`BLOCKED_FOR_SOURCE` stands, no findings guessed at. (2) T-023 (Lu 2026): obtained via Taiwan's
National Central Library public periodical-access service (a lawful national-library service, not a
publisher bypass) — rich new data extracted, and the primary source's own Limitations section
independently confirms the "zero AEs = under-ascertainment" caution trials-efficacy had already
flagged from the abstract alone in Wave 2. (3) Built an explicit Level 1/2/3 framework table in its
own `20_EVIDENCE/trials-efficacy/evidence-map.md` — **transparently noted it could not read
`30_METHODS/shared/wave2-challenge-round.md` directly (not present in its isolated worktree, only a
`.gitkeep`) and built the framework from the Director's dispatch-message description instead,
disclosing this rather than silently working from an assumption.** (4) OpenEvidence bounded pass:
confirmed `CONNECTION_CLOSED` in this session too, reported honestly as not-attempted rather than
silently skipped. **Bonus find**: a third national Phase III pitavastatin+ezetimibe FDC RCT — Jeong
HS et al. 2022 (Korea, Clin Ther, same journal/issue as citation #33's Taiwan trial) — found in
T-023's reference list and independently verified: LDL-C −52.8% (combo) vs. −37.1% (pitavastatin
alone), diff −15.8 mg/dL (95% CI −18.7 to −12.9, P<0.001); goal attainment 94.2% vs. 69.1%
(P<0.001). Full text blocked (Yonsei repository, JS anti-bot challenge, not solved).

**Decision:** `VERIFIED_AND_REPLACE` for T-023 (abstract-only → full text obtained). T-024 stays
`BLOCKED_FOR_SOURCE` with the three exhausted lawful routes now documented. New source **T-028**
logged for Jeong 2022 — citation-verified, full text blocked. **Cross-national replication note**:
Level 1 evidence (LDL-lowering efficacy) now has independent RCT replication across three countries
(Taiwan/#33, Japan/T-004a, Korea/T-028), all showing >50% LDL-C reduction with broadly comparable
safety — this meaningfully strengthens (without changing) the Level 1/2/3 framework's existing
finding that Level 1 is the strongest-supported tier. **Worktree-visibility gap noted, not treated
as an error**: trials-efficacy's isolated worktree lacks files the Director has authored on `main`/
its own branch since a point before the last consolidation reached that worktree (e.g.
`30_METHODS/shared/wave2-challenge-round.md`) — expected given the project's known multi-worktree
consolidation lag, not a compliance issue; the peer's own disclosure of the gap is the correct
handling.

**Affected files:** `02_SOURCE-INVENTORY.md` (T-023, T-024 rows updated; new T-028 row).

**Source:** trials-efficacy-intelligence cross-session report, 2026-08-31 (Wave 3).

**Approved by:** Research Director (Wave 3).

---

## Decision 2026-08-31-31

**Issue:** guideline-risk's Wave 3 report on its three dispatched tasks. (1) Citation #29 obtained
via the tas.org.tw mirror (same pattern as #30/#32/#35) — exact COR/LOE-graded recommendations
extracted, with a printed "LOR IIa" (vs. every other instance's "COR IIa") preserved exactly as a
likely typo, not silently corrected. (2) T-008 (Taiwan Health Promotion annual report) obtained via
`hpa.gov.tw`'s `GetFile.ashx` endpoint (outside the WAF blocking its CMS pages) — its figures exactly
match `Tonvasca_2026.md`'s closing-slide prevalence numbers (63.0%/28.2%/40.0%), closing a citation
that had been open since Wave 0. **Verification-discipline highlight**: en route, a Wayback Machine
"closest available" lookup returned a different, wrong document (a 721-page cancer registry report)
under a mismatched `sid` — guideline-risk fetched it, checked the title page, recognized it was
wrong, and discarded it before it touched the repo, rather than assuming the lookup was correct. (3)
OpenEvidence bounded pass: `oe_health` shows the relay daemon up but the browser extension not
connected/polling, so `oe_ask` is unusable — genuinely blocked, not skipped; the six blocked sources
(including this role's T-005/T-006/#34) stay untouched.

**Decision:** `VERIFIED_AND_REPLACE` for citation #29 (citation-verified → content-verified) and
T-008 (not-located → obtained, verified, and cross-confirmed against the legacy slide's own
figures). The Wayback near-miss is recorded as a **positive example of the numeric-integrity/
provenance discipline this project requires** — commended explicitly, not merely noted.

**Affected files:** `02_SOURCE-INVENTORY.md` (#29, T-008 rows).

**Source:** guideline-risk-intelligence cross-session report, 2026-08-31 (Wave 3).

**Approved by:** Research Director (Wave 3).

---

## Decision 2026-08-31-32 — Wave 3 Synthesis complete, Gate 3 PASSED

**Issue:** All three specialists reported their Wave 3 assignments. Director integrated their
findings into the nine required `40_SYNTHESIS/` deliverables (`00_executive-synthesis.md` through
`08_traceability-table.md`), then ran a Director-level Wave 3 Challenge Round against the freshly
drafted synthesis itself (distinct from the Wave 2 Challenge Round, which audited the source base).

**Decision:** Three issues were self-caught and corrected in place: (1) `00_executive-synthesis.md`
had misattributed the four-tier primary-prevention LDL-C targets to both citation #29 and #35 —
only #35 carries that structure; corrected. (2) `06_adherence-residual-risk.md` stated ESC 2025's
Lp(a) threshold without the same "unverified against primary text" caveat already correctly applied
to the structurally identical Taiwan STS 2026 claim — both T-007 and T-005 are `BLOCKED_FOR_SOURCE`
and trace only to `pitavastatin topic.md`'s paraphrase; corrected. (3) `02_guideline-risk-positioning.md`
listed citation #27's specific LDL-C thresholds without noting they trace to `Tonvasca_2026.md`'s own
reproduced flowchart, not an independent re-check of #27's primary text — a weaker verification
layer than #27's own bibliographic verification; corrected to distinguish the two. All other checks
(trials-angle conflation guards, safety-language grep, cross-file numeric consistency, citation-ID
typo check) passed without correction. Full detail:
`30_METHODS/shared/wave3-challenge-round-and-gate3.md`.

**Gate 3: PASSED.** Per PI directive, proceeding automatically to Wave 4 (independent audit, sonnet,
read-only except `99_FINAL-QA.md`). `50_MANUSCRIPT/` remains out of scope.

**Affected files:** `40_SYNTHESIS/00`, `40_SYNTHESIS/02`, `40_SYNTHESIS/06` (corrections);
`30_METHODS/shared/wave3-challenge-round-and-gate3.md` (new); `05_STATUS.md` (Gate 3 recorded).

**Source:** Director's own Wave 3 Challenge Round, 2026-08-31.

**Approved by:** Research Director (Wave 3), per PI's standing Wave 3 authorization.

---

## Decision 2026-08-31-33 — Wave 4 audit Finding 1 corrected

**Issue:** The Wave 4 independent auditor (sonnet, read-only except `99_FINAL-QA.md`) found that
`40_SYNTHESIS/02_guideline-risk-positioning.md`'s risk-threshold table presented citation #28's
(2026 ACC/AHA) LDL-C goals (<55 mg/dL very-high-risk, <70 mg/dL not-very-high-risk) and, in
`06_adherence-residual-risk.md`, its Lp(a) thresholds (≥50 mg/dL / ≥125 nmol/L), without the
"unverified against primary text" caveat already correctly applied to structurally identical claims
(T-005, T-007) elsewhere in the same document set — and that neither number had a corresponding row
in `08_traceability-table.md`. The auditor flagged this as a genuine Numeric Integrity Rule
violation (an untraceable-within-the-evidence-base number) and recommended `HOLD_FOR_CORRECTION`.

**Director verification before correcting**: read `Tonvasca_2026.md` (L-002) directly. The <55/<70
LDL-C figures are reproduced verbatim in L-002 lines 1424–1481, explicitly cited there to citation
#28's DOI — **not fabricated**, but genuinely never independently extracted from #28's own primary
text (which remains `BLOCKED_FOR_SOURCE`) nor properly anchored in `02_SOURCE-INVENTORY.md` or
`08_traceability-table.md`. The Lp(a) mg/dL threshold (≥50 mg/dL) also traces to L-002 (line 1361,
cited to #28); the nmol/L conversion (≥125 nmol/L) traces only to `pitavastatin topic.md` (L-001,
the PI's own topic notes, line 149) — a more precise provenance breakdown than the auditor's
finding initially stated, surfaced while correcting.

**Decision:** `VERIFIED_AND_REPLACE` for the citation anchoring (both figures now explicitly sourced
to their exact L-002/L-001 line ranges in `02_SOURCE-INVENTORY.md` row 56); `VERIFIED_NEW_SENSITIVITY`
for the caveat consistency (the "unverified against primary text" caveat now applied uniformly to
#28's numbers in `02` and `06`, matching how T-005/T-007 are already treated). New rows added to
`08_traceability-table.md` for the previously-missing <70 mg/dL and Lp(a) figures.

**Affected files:** `02_SOURCE-INVENTORY.md` (#28 row), `40_SYNTHESIS/02_guideline-risk-positioning.md`,
`40_SYNTHESIS/06_adherence-residual-risk.md`, `40_SYNTHESIS/01_claim-evidence-matrix.md` (C19),
`40_SYNTHESIS/08_traceability-table.md`.

**Source:** `pit-eze-independent-auditor` Wave 4 audit report, `99_FINAL-QA.md` Finding 1, 2026-08-31.

**Approved by:** Research Director (Wave 4 correction cycle), routed back per the audit's own
recommendation that corrections go through the owning role (Director owns `40_SYNTHESIS/`).

---

## Decision 2026-08-31-34 — Wave 4 re-audit: PASS_WITH_MINOR_ISSUES, Final Gate reached

**Issue:** `pit-eze-independent-auditor` re-audited `02_SOURCE-INVENTORY.md` #28,
`40_SYNTHESIS/01/02/06/08` after Decision 2026-08-31-33's correction — independently re-read the
underlying legacy sources itself (`Tonvasca_2026.md` lines ~1330–1362/~1420–1481,
`pitavastatin topic.md` lines 145–153) rather than trusting the Director's fix on its face, and
confirmed the correction accurate: the <70 mg/dL figure is genuine (not fabricated), the caveat is
now applied consistently, and the mg/dL-vs-nmol/L provenance split is exactly right. One new,
explicitly non-blocking observation: `08_traceability-table.md` had a stale, less-detailed duplicate
Lp(a) row left over below the corrected one (same values, no numeric-integrity issue — tidiness
debt only).

**Decision:** Finding 1 `RESOLVED`. Stale duplicate row removed from `08_traceability-table.md`
(no separate Decision entry needed for this trivial cleanup, noted here). **Final Gate:
`PASS_WITH_MINOR_ISSUES`** — per Runbook §36, this is one of the two statuses that may be marked
`FINAL`. All eight originally-named project traps remain correctly guarded on re-audit (no
regression from the correction); no forbidden language, secrets, Sci-Hub provenance, or unresolved
placeholders found in either audit pass.

**Wave 3 Synthesis (`40_SYNTHESIS/00`–`08`, as committed through this decision) is marked `FINAL`.**
`50_MANUSCRIPT/` remains explicitly out of scope (Decision 2026-08-31-28) — reaching Final Gate on
the synthesis does not authorize manuscript/slide work absent separate PI direction.

**Affected files:** `40_SYNTHESIS/08_traceability-table.md` (duplicate row removed), `99_FINAL-QA.md`
(auditor's own re-audit addendum), `05_STATUS.md` (Final Gate recorded).

**Source:** `pit-eze-independent-auditor` re-audit report, `99_FINAL-QA.md`, 2026-08-31.

**Approved by:** Research Director, on the independent auditor's `PASS_WITH_MINOR_ISSUES`
recommendation.
