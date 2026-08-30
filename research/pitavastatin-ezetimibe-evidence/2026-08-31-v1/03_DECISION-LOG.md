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
