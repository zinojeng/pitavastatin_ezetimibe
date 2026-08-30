# Cross-session log — Wave 2 dispatch — 2026-08-31

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Logged by: Research Director (`pit-eze-research-director`)

## Context

PI reviewed and authorized all five items escalated at Wave 1 close (Decision 2026-08-31-12). Full
detail in `03_DECISION-LOG.md`. This entry records the resulting Wave 2 dispatch.

## Pre-dispatch health check

`ListAgents` confirmed all three persistent specialists reachable and idle:
`pit-eze-guideline-risk` [a7823a], `pit-eze-trials-efficacy` [ce9a36],
`pit-eze-safety-pharmacology` [5c9140]. Full registry written to `SESSION-REGISTRY.md` in this same
directory.

## Governance updates made before dispatch

- `CLAUDE.md` §10: `mcp__research_hub__download_paper` restriction changed from interim to
  **permanent**; MCP connectivity update (research_hub/llamaparse repaired, llamaparse passed a live
  dummy-PDF smoke test) recorded.
- `CLAUDE.md` §3: `50_MANUSCRIPT/` ownership resolved — Director owns coordination until Gate 2.
- `CLAUDE.md` §12: security TODO added (historical hardcoded `llamaparse` credentials exist outside
  this repo, should be rotated/removed — no credential value recorded).
- `.gitignore`: `.metadata_cache/` added.
- `02_SOURCE-INVENTORY.md` #26: Sydhom framing updated to the PI's exact required wording.
- `03_DECISION-LOG.md`: Decision 2026-08-31-12 added (consolidated record of all five PI decisions).
- `04_OPEN-QUESTIONS.md`: reorganized (several items had been mis-filed under "Resolved" during
  rapid Wave 1 processing — corrected, no content lost) and updated with Wave 2 dispatch targets.
- `05_STATUS.md`: condensed (many superseded "Update —" sections from Wave 1) and updated to Wave 2/
  Gate 1-passed state, with the PI's Gate 2 exit criteria recorded verbatim.
- `00_RUN-MANIFEST.md`: MCP repair and consolidation-status sections added.
- Local `main` merged into this session's own working branch (`worktree-wave0-init`) to bring in the
  three specialists' actual Wave 1 output files for direct Director visibility — verified via
  `git log` that local `main` already contains all four branches' Wave 1 work per the PI's
  consolidation report. This was a same-branch catch-up, not a branch-consolidation act; this
  session did not and will not merge branches into `main` itself, per the PI's instruction.

## Dispatch (this entry)

Three `TASK_ASSIGNMENT` messages sent via real `SendMessage` (message schema per `CLAUDE.md` §6):

- **trials-efficacy**: Tsujita 2023 (PMC10627746 / J-STAGE PDF) + Ako 2024 (PMC10918028) full text,
  LlamaParse required on ≥1 (Tsujita) as one of two Gate-2 demonstrations; exact arm/LDL-C/AE/CK/
  AST/ALT/HbA1c/significance extraction; Chou MT 2022 AE/CK/liver tables; Katzmann 2022 full text
  for cohort-size resolution (Decision 2026-08-31-11, still open per PI).
- **guideline-risk**: Taiwan STS 2026 publisher-authorized fetch attempt (else `BLOCKED_FOR_SOURCE`);
  official 2026 ACC/AHA PDF + official ESC 2025 content; LlamaParse required on ≥1 as the second
  Gate-2 demonstration; exact combination-therapy wording extraction.
- **safety-pharmacology**: Singh 2024 + Katzmann 2022 lawful full text (else `BLOCKED_FOR_SOURCE`);
  DDI validation directly against official DailyMed/FDA; parse a lawful safety PDF if obtained (not
  a required Gate-2 demonstration); T-013/CKD-elderly/BCRP gaps remain in queue.

**Common requirement communicated to all three**: for every PDF touched, record license/source URL,
retrieval timestamp, SHA-256, parse status, and page/table/section locators. PDFs stay gitignored,
never committed — only metadata/extraction/citation records land in git.

All three reminded: `mcp__research_hub__download_paper` remains permanently prohibited;
`research_hub`'s metadata/search tools remain permitted.

## Status

Wave 2 dispatched. Director awaits completion reports, including explicit confirmation from
trials-efficacy and guideline-risk of whether their required LlamaParse demonstration succeeded
(Gate 2 exit criteria per `05_STATUS.md`).
