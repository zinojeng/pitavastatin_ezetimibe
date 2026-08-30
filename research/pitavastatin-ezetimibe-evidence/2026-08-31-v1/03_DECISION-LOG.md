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

**Decision:** `NEEDS_PI` — do not silently reword `Tonvasca_2026.md` (it is a read-only legacy input,
`CLAUDE.md` §1) or `40_SYNTHESIS/` content yet. Route to the PI: any future synthesis or slide
language drawing on the Sydhom et al. 2024 clinical-outcome figures (MACE 0.76, CV death 0.80,
all-cause death 0.84, non-fatal stroke 0.81) must explicitly qualify them as observational-pooled,
not RCT-pooled, evidence — pending PI confirmation of trials-efficacy's read of the primary source's
abstract (Director has not independently re-verified the primary source directly).

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
