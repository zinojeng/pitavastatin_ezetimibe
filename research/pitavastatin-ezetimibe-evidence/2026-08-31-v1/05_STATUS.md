# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Last updated: 2026-08-31 (Wave 1, Research Director)

## Current Gate

**READY_FOR_NEXT_WAVE** (Gate 0 passed; Wave 1 now in progress — Gate 1 not yet reached)

## Wave

1 — Source / Evidence Verification (in progress)

## Completed — Wave 0

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
  the owning Wave 1 specialist, in `02_SOURCE-INVENTORY.md`.
- Legacy input files (`pitavastatin topic.md`, `Claude_Code_Cross-Session_Research_完整建議與經驗_Runbook.md`,
  `Tonvasca_2026.md`) preserved unmodified at repo root; checksummed in `00_RUN-MANIFEST.md`.

## In progress — Wave 1 (as of this update)

All three domain specialists are online and confirmed reachable via `ListAgents`
(`pit-eze-guideline-risk`, `pit-eze-safety-pharmacology`, `pit-eze-trials-efficacy`, all status
`busy`), and this session is confirmed addressable as `pit-eze-research-director`.

- **guideline-risk-intelligence** — sent `CROSS_SESSION_TEST`, confirmed orientation reading
  complete, scope confirmed against `CLAUDE.md` §2.2/§5 and `02_SOURCE-INVENTORY.md` citations
  #1,2,17,18,24,27,28,29,30,31,32; also reading the previously-unread `Tonvasca_2026.md` remainder
  (lines 1795–2811). Director acknowledged and approved scope. Awaiting completion report with
  `OUTPUT_PATHS`.
- **safety-pharmacology-intelligence** — sent `CROSS_SESSION_TEST`, reports Wave 1 work already
  underway on a task assignment received directly (not yet reconciled with Director). Director
  acknowledged, confirmed the domain/citation mapping it expects (#3–16, 23, 26-joint) per
  `CLAUDE.md` §2.4/§5, and asked it to confirm its actual assignment in its next report so the two
  can be reconciled — **not yet confirmed**, tracked as a follow-up.
- **trials-efficacy-intelligence** — shows `busy` in `ListAgents` (per safety-pharmacology's report
  and Director's own check) but has not yet sent the Director a `CROSS_SESSION_TEST` or status
  report directly. Per Runbook §32, the Director is waiting for it to report rather than
  interrupting or duplicating its assumed-in-progress work. **No confirmed scope from this peer
  yet.**

Both received messages and both Director replies are logged verbatim in `90_CROSS-SESSION-LOG/`.

## Known process gap flagged during Wave 1 (for `03_DECISION-LOG.md` / `CLAUDE.md` follow-up)

`CLAUDE.md` §3's File Ownership Matrix does not list an explicit writer for
`02_SOURCE-INVENTORY.md`. guideline-risk-intelligence correctly treated it as Director-owned/shared
and said it will not edit it directly, reporting verification findings back to the Director instead.
This is the safe default and is now the explicit rule (see Decision 2026-08-31-05) — the Director
updates `02_SOURCE-INVENTORY.md`'s `verified?`/`superseded?` columns based on each specialist's
reported findings, rather than specialists editing it directly, to avoid simultaneous-edit conflicts
on a file three peers all touch.

## Sync-state caveat (operational, not a research blocker)

This Director session is running as a background job isolated in a git worktree
(`.claude/worktrees/wave0-init`, branch `worktree-wave0-init`). The shared checkout the three
specialist peers actually read from (`main`, at commit `3d63075`) already contains all Wave 0
content — apparently merged there outside this session, since this session's own attempt to `git
push` its branch to `origin` was blocked by the environment's permission classifier. **Any further
edit this session makes (including this Wave 1 status update) lands only on the isolated
`worktree-wave0-init` branch and will not be visible to the peer sessions reading `main` until it is
merged there again.** Flagged to the PI; see the Wave 1 report delivered to the user.

## Pending (Wave 1 exit / Gate 1 criteria)

- Re-confirm `research_hub` / `llamaparse` / `openevidence` MCP connectivity (all three failed to
  connect during Wave 0; see `00_RUN-MANIFEST.md` and Decision 2026-08-31-03) — not yet re-checked
  by any peer as of this update.
- guideline-risk-intelligence, safety-pharmacology-intelligence, and trials-efficacy-intelligence
  each complete their Wave 1 verification pass and report back with `OUTPUT_PATHS`.
- safety-pharmacology-intelligence's exact task assignment reconciled with the Director's expected
  scope (see above).
- trials-efficacy-intelligence's scope/status confirmed directly with the Director.
- Director updates `02_SOURCE-INVENTORY.md` (`verified?`/`superseded?` columns) from each peer's
  reported findings once received.
- PI decision still needed on whether to create a manuscript/presentation-intelligence role for
  `50_MANUSCRIPT/` (Decision 2026-08-31-04) — not a Wave 1 blocker, but should be resolved before
  Wave 3.
- Worktree/main sync gap above resolved (this branch merged into `main` again) so Director-side
  Wave 1 updates are actually visible to peers.

## Blocked

None at the repository-structure level. MCP-connectivity items remain open questions
(`04_OPEN-QUESTIONS.md`). The worktree/main sync gap above is an operational blocker on the
Director's own write visibility, not on the specialists' in-progress work.

## Next action

Director awaits: (a) safety-pharmacology-intelligence's scope confirmation, (b)
trials-efficacy-intelligence's first report, (c) all three specialists' Wave 1 completion reports.
PI: resolve the worktree/main sync gap (merge `worktree-wave0-init` into `main` again, or move this
Director session out of worktree isolation) so ongoing Director updates reach the shared checkout.
