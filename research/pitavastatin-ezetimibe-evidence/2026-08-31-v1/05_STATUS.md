# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Last updated: 2026-08-31 (Wave 0, Research Director)

## Current Gate

**READY_FOR_NEXT_WAVE**

## Wave

0 — Orientation (complete)

## Completed

- Repository initialized: `CLAUDE.md`, `README.md`, `.gitignore`, `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`.
- Run directory created: `00_RUN-MANIFEST.md`, `01_RESEARCH-CHARTER.md`, `02_SOURCE-INVENTORY.md`,
  `03_DECISION-LOG.md`, `04_OPEN-QUESTIONS.md`, `05_STATUS.md` (this file), and all mandated
  subdirectories (`10_DATA/`, `20_EVIDENCE/`, `30_METHODS/`, `40_SYNTHESIS/`, `50_MANUSCRIPT/`,
  `90_CROSS-SESSION-LOG/`) with per-role ownership placeholders and `99_FINAL-QA.md` skeleton.
- Persistent roles defined and tailored to this clinical evidence review (Research Director,
  guideline-risk-intelligence, trials-efficacy-intelligence, safety-pharmacology-intelligence,
  independent-auditor) with full prompt templates in `CLAUDE.md` §14.
- File ownership matrix, Wave/Gate rules, cross-session message schema, Evidence Hierarchy taxonomy,
  Decision Taxonomy, MCP source policy (with explicit Sci-Hub prohibition), full-text/licensing
  rule, and secrets rule all written into `CLAUDE.md`.
- Prioritized Search Protocol (10 items) derived from `pitavastatin topic.md` and written into
  `CLAUDE.md` §5, each pre-assigned to an owning specialist.
- Preliminary source catalog of `Tonvasca_2026.md`'s ~33 embedded citations, assigned by domain to
  the owning Wave 1 specialist, in `02_SOURCE-INVENTORY.md`. **None of these citations are verified
  yet** — that is Wave 1 work.
- No persistent specialist sessions have been spawned yet (Wave 0 is Director-only per `CLAUDE.md`
  §4); no literature search of any kind has been performed (task explicitly scoped Wave 0 to
  initialization only).
- Legacy input files (`pitavastatin topic.md`, `Claude_Code_Cross-Session_Research_完整建議與經驗_Runbook.md`,
  `Tonvasca_2026.md`) preserved unmodified at repo root; checksummed in `00_RUN-MANIFEST.md`.
- Structure validated (directory tree, required files, file-count checks — see Wave 0 completion
  report delivered to PI) before setting this Gate to READY_FOR_NEXT_WAVE.

## Pending (Wave 1 entry criteria)

- Re-confirm `research_hub` / `llamaparse` / `openevidence` MCP connectivity (all three failed to
  connect during Wave 0; see `00_RUN-MANIFEST.md` and Decision 2026-08-31-03).
- Read the unread remainder of `Tonvasca_2026.md` (lines 1795–2811) and extend
  `02_SOURCE-INVENTORY.md` accordingly (Decision 2026-08-31-02).
- PI decision needed on whether to create a manuscript/presentation-intelligence role for
  `50_MANUSCRIPT/` (Decision 2026-08-31-04) — not a Wave 1 blocker, but should be resolved before
  Wave 3.
- Spawn the three domain specialists (guideline-risk-intelligence, trials-efficacy-intelligence,
  safety-pharmacology-intelligence) using the startup prompt in `CLAUDE.md` §14.2, run the
  cross-session health check (`CLAUDE.md` §13), and confirm all three reply READY before Wave 1
  dispatch.

## Blocked

None at the repository-structure level. Three MCP-connectivity items are logged as open questions
(`04_OPEN-QUESTIONS.md`) to resolve before or during Wave 1, not blockers to Wave 0 completion
itself.

## Next action

Human PI (or Research Director on PI's instruction) initiates Wave 1: spawn the three specialist
peers, run health check, dispatch Source/Evidence Verification per `CLAUDE.md` §4 Wave 1 and §5
Search Protocol.
