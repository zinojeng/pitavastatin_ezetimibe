# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Last updated: 2026-08-31 (Wave 2 dispatch, Research Director)

> **Housekeeping note:** this file had accumulated many superseded "Update —" sections from rapid
> Wave 1 processing. Condensed here into a single current narrative; no information dropped — see
> git history for the previous, more granular version if a specific timestamp/sequence is needed.

## Current Gate

**Gate 1: PASSED (PI authorization, 2026-08-31, Decision 2026-08-31-12).**

**Gate 2 exit criteria (PI-specified, 2026-08-31):** mark `READY_WITH_PENDING_ITEMS` if paywalled
sources remain unresolved, **provided** the two required lawful LlamaParse demonstrations succeed —
at least one PDF parsed by trials-efficacy (Tsujita 2023) and at least one PDF parsed by
guideline-risk (an ACC/AHA or ESC 2025 document). Not yet evaluated — Wave 2 has just been
dispatched this session; see the dispatch messages in `90_CROSS-SESSION-LOG/`.

## Wave

2 — Focused lawful full-text acquisition (just dispatched to all three persistent specialists)

## Wave 0 — complete

Repository initialized (`CLAUDE.md`, `README.md`, `.gitignore`, `docs/`, full run directory
structure, persistent-role definitions, Search Protocol, MCP source policy). See `00_RUN-MANIFEST.md`
and `01_RESEARCH-CHARTER.md`.

## Wave 1 — complete, all loose ends closed

All three domain specialists (`pit-eze-guideline-risk`, `pit-eze-trials-efficacy`,
`pit-eze-safety-pharmacology`) completed Source/Evidence Verification against their assigned legacy
citations, read the previously-unread `Tonvasca_2026.md` remainder, and found/verified several new
sources. Highlights (full detail in `02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md`, and
`90_CROSS-SESSION-LOG/`):

- All ~35+ legacy citations across the three domains verified or explicitly flagged not-locatable
  (never silently dropped or guessed).
- New sources found and verified: Singh H et al. 2024 (T-003, pitavastatin NODM meta-analysis —
  explicitly distinct from Sydhom 2024), Tsujita 2023 + Ako 2024 (T-004a/T-004b, closing the 2mg-
  vs-4mg dose-comparison gap), Taiwan STS 2026 / Taiwan Lp(a) 2026 / ESC 2025 Focused Update
  (T-005/T-006/T-007), the LIVALO/DailyMed DDI label (T-010), Katzmann JL et al. 2022 (T-012).
- A Sci-Hub compliance concern was caught and correctly handled by guideline-risk (no contamination)
  — led to Decision 2026-08-31-08.
- A genuine legacy-source inconsistency was caught by trials-efficacy: `Tonvasca_2026.md` itself
  prints two contradictory cohort sizes for the Katzmann 2022 comparison — Decision 2026-08-31-11,
  unresolved pending full text (PI-confirmed this stays open, see below).
- Two self-corrections by guideline-risk (withdrawing an over-stated "open access" claim; confirming
  a citation the Director had flagged as a possible duplicate was in fact correctly resolved)
  demonstrated good epistemic discipline — commended, not just accepted.
- Five items were escalated to the PI at Wave 1 close: the Sydhom framing, the research_hub/Sci-Hub
  tool policy, `50_MANUSCRIPT/` ownership, the multi-worktree consolidation gap, and the Katzmann
  cohort-size discrepancy.

## PI Wave 2 authorization, 2026-08-31 (Decision 2026-08-31-12 — full text there)

The PI reviewed and decided all five escalated items:

1. **Sydhom framing** — state observational-pooled benefit only; RCT-pooled clinical endpoints not
   statistically significant. Applied to `02_SOURCE-INVENTORY.md` #26.
2. **research_hub policy** — `mcp__research_hub__download_paper` **permanently** prohibited
   (was interim). `CLAUDE.md` §10 updated.
3. **`50_MANUSCRIPT/` ownership** — Research Director owns coordination until Gate 2.
4. **Multi-worktree consolidation** — PI confirms all four Wave 1 branches + Director's Gate 1
   commits reviewed, secret-scanned, and consolidated into local `main` by the supervising Codex
   process. This session verified that independently and merged `main` into its own working branch
   for direct file visibility (not a branch-consolidation act — this session will not merge branches
   into `main` itself).
5. **Katzmann cohort discrepancy** — confirmed still unresolved until full text; added to Wave 2
   trials-efficacy dispatch.

Also directed and completed this session: `.metadata_cache/` added to `.gitignore`; session registry
created (`90_CROSS-SESSION-LOG/SESSION-REGISTRY.md`); `research_hub`/`llamaparse` MCP repair and
`llamaparse`'s live dummy-PDF smoke test recorded (`00_RUN-MANIFEST.md`); a security TODO recorded
for historical hardcoded `llamaparse` credentials reported to exist outside this repo (`CLAUDE.md`
§12 — no credential value recorded anywhere); Wave 2 dispatched to all three specialists via real
`SendMessage` (see `90_CROSS-SESSION-LOG/`).

## Not addressed by the PI — still open

- **safety-pharmacology's commit permission**: its own task instructions say "do not commit/push";
  the PI's Wave 2 authorization did not explicitly relax this. Its Wave 1 output remains uncommitted
  in its own worktree but *is* already visible to the Director via the Codex-process consolidation
  into `main`, so this is not blocking Wave 2 — flagged only in case the PI wants it addressed.

## Wave 2 dispatch summary (this update)

| Specialist | Assigned Wave 2 targets |
|---|---|
| trials-efficacy | Tsujita 2023 (PMC10627746 or J-STAGE PDF) + Ako 2024 (PMC10918028) full text, LlamaParse on ≥1; exact arm/LDL-C/AE/CK/AST/ALT/HbA1c/significance extraction. Chou MT 2022 AE/CK/liver tables. Katzmann 2022 full text (cohort-size resolution). |
| guideline-risk | Taiwan STS 2026 publisher-authorized fetch attempt (else `BLOCKED_FOR_SOURCE`). Official 2026 ACC/AHA PDF + official ESC 2025 content, LlamaParse on ≥1; exact combination-therapy wording extraction. |
| safety-pharmacology | Singh 2024 + Katzmann 2022 lawful full text (else `BLOCKED_FOR_SOURCE`). DDI validation against official DailyMed/FDA directly. Parse a lawful safety PDF if obtained. Never use `research_hub` download tool. |

**Common requirement for every PDF any specialist touches**: record license/source URL, retrieval
timestamp, SHA-256, parse status, and page/table/section locators. PDFs stay gitignored, never
committed.

## Blocked

None at the repository-structure or governance level. Wave 2 literature acquisition may surface
individual `BLOCKED_FOR_SOURCE` items (paywalled sources) — expected and acceptable per Gate 2's
exit criteria above, not a project-level blocker.

## Next action

Director awaits Wave 2 completion reports from all three specialists, including confirmation of the
two required LlamaParse demonstrations, before evaluating Gate 2.
