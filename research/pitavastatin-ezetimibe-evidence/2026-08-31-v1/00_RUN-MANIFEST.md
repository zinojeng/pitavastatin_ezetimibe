# 00_RUN-MANIFEST — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence`
RUN_ID: `2026-08-31-v1`
Date initialized: 2026-08-31 (Wave 0, Research Director)
Previous run: none — this is the first run for this project.

## Git

- Repo root: `/Users/ander/Documents/medical/hyperlipidemia/pitavastatin`
- Branch at Wave 0 init: `main`, plus this session's isolation branch `worktree-wave0-init`
  (background-job git-worktree isolation; merges back to `main`).
- Initial commit (legacy inputs only): `4cf3f7b` — "Initial commit: legacy input files (topic
  notes, runbook, slide source)"
- Working tree at Wave 0 start: clean except for the three untracked legacy files (now committed
  in `4cf3f7b`) and this Wave 0 initialization.

## Input files (legacy, root-level, read-only — see CLAUDE.md §1)

| File | Size (bytes) | Modified | SHA-256 | Role |
|---|---|---|---|---|
| `pitavastatin topic.md` | 7600 | 2026-08-31 03:39 | `4993cbc67ae7623a82984f72788bb8ac47ab461345b81ed728865f0127b8dcf5` | Topic/angle notes; source of Search Protocol |
| `Claude_Code_Cross-Session_Research_完整建議與經驗_Runbook.md` | 38726 | 2026-08-31 03:24 | `73137596b86f012d847c3c5602a1700a2d81a7da6195d6380c178b03e046f639` | Source of `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md` |
| `Tonvasca_2026.md` | 67055 | 2026-08-31 03:12 | `61a09c2ebf9191221c9bb64bb61f94652640b76ff961a75229853048f7b657d3` | Legacy slide-deck source content; citations require independent re-verification |

(SHA-256 values computed at Wave 0 init via `shasum -a 256`. If any legacy file's checksum changes
in a future session, treat it as a new source version and record the change in `03_DECISION-LOG.md`
— do not silently re-checksum and move on.)

## Persistent session topology (see CLAUDE.md §2 for full role definitions)

1. Research Director
2. guideline-risk-intelligence
3. trials-efficacy-intelligence
4. safety-pharmacology-intelligence
5. independent-auditor (Wave 4 only)

No persistent sessions have been spawned yet as of Wave 0 completion — this Wave was performed
directly by the Research Director acting alone (per CLAUDE.md §4, Wave 0 is Director-only
orientation; no specialist should be dispatched before Gate 0 = READY_FOR_NEXT_WAVE).

## Output folders

`10_DATA/`, `20_EVIDENCE/`, `30_METHODS/` (each with `guideline-risk/`, `trials-efficacy/`,
`safety-pharmacology/` subfolders, plus `fulltext/` under 10_DATA/20_EVIDENCE and `shared/` under
30_METHODS), `40_SYNTHESIS/`, `50_MANUSCRIPT/` (unowned pending an open question),
`90_CROSS-SESSION-LOG/`, `99_FINAL-QA.md`. Full tree in `README.md`.

## File ownership

See `CLAUDE.md` §3 (File Ownership Matrix) — authoritative; not duplicated here to avoid drift.

## Current research gate

**Gate 0** — Wave 0 (Orientation) complete as of this manifest's creation. Status to be set to
`READY_FOR_NEXT_WAVE` in `05_STATUS.md` once this Wave 0 validation checklist passes.

**Superseded, 2026-08-31**: Gate 1 passed (PI authorization, Decision 2026-08-31-12); Gate 2
declared `READY_WITH_PENDING_ITEMS` (PI directive, Decision 2026-08-31-27). `05_STATUS.md` is the
authoritative current-gate pointer going forward — this section is left as the historical Wave 0
record per the additive-versioning principle (`CLAUDE.md` §15, Golden Rule 9), not edited in place.

## Known blockers as of Wave 0 (MCP connectivity)

The following MCP servers listed in CLAUDE.md §10 as allowed sources **failed to connect** or were
unavailable during this Wave 0 session:

- `research_hub` — ENOENT: `posix_spawn '/Users/ander/research_hub_mcp/target/release/rust-research-mcp'` not found (binary missing/not built).
- `llamaparse` — ENOENT: `posix_spawn '/Users/ander/llamaparse-mcp/.venv/bin/python'` not found (venv missing).
- `openevidence` — CONNECTION_CLOSED.

`paper-search`, `google-scholar`, `tavily`, and (per the "still connecting" list at Wave 0 time)
`mcp-obsidian` and `tmux-bridge` appeared in the deferred/connecting tool list and were not directly
exercised in Wave 0 (Wave 0 performs no literature search — see CLAUDE.md §4). Their live
reachability must be re-confirmed at the start of Wave 1 before dispatching guideline-risk-
intelligence, trials-efficacy-intelligence, or safety-pharmacology-intelligence, and any that remain
down should be reported to the PI as environment fixes needed (rebuild `research_hub`, recreate the
`llamaparse` venv, or retry `openevidence`) rather than silently worked around.

A `scihub` MCP tool is also present in this environment but is **prohibited for this project without
exception** (CLAUDE.md §10) — its presence is not a blocker to resolve, it is a tool that must never
be called here.

## Unresolved blockers carried into Wave 1

1. Confirm `research_hub` / `llamaparse` / `openevidence` connectivity before Wave 1 dispatch (or
   proceed on the fallback source set and record the gap — see `04_OPEN-QUESTIONS.md`).
2. `50_MANUSCRIPT/` ownership undecided — no dedicated manuscript/presentation-intelligence
   persistent role has been created for this run (see `04_OPEN-QUESTIONS.md`).

## Wave 1 update (2026-08-31, reported by safety-pharmacology-intelligence, not yet independently
re-tested by the Director — logged additively, Wave 0 record above left unchanged per Golden Rule 8)

safety-pharmacology-intelligence reports `research_hub` and `llamaparse` ARE reachable in its own
session (via ToolSearch), contrary to the Director's Wave 0 ENOENT failures for the same two
servers. This is plausibly per-session/per-process MCP state rather than a fixed environment fact
(e.g., a missing binary/venv on the Director's process specifically). `openevidence` remains down
(CONNECTION_CLOSED) in both sessions. Treat the Wave 0 `research_hub`/`llamaparse` failure note above
as **session-specific, not project-wide**, until the Director re-tests directly — do not assume
either server is unavailable to your own session without checking. `openevidence` should still be
treated as currently unavailable everywhere until a session reports otherwise.

## Wave 2 update (2026-08-31, PI-reported)

The PI confirms `research_hub` and `llamaparse` MCP servers have been **repaired** (the Wave 0
ENOENT failures — missing `research_hub` Rust binary, missing `llamaparse` Python venv — are
resolved), and `llamaparse` has **passed a live dummy-PDF smoke test**. Both are authorized for Wave
2 lawful full-text acquisition, subject to the permanent restriction on
`mcp__research_hub__download_paper` (Decision 2026-08-31-08/12, `CLAUDE.md` §10). This Director
session has not independently re-tested either tool itself (its own Wave 2 role is orchestration, not
literature search); each dispatched specialist should confirm its own session's connectivity before
relying on either tool, consistent with the "per-session state" caution above. `openevidence`'s
status is unchanged (last known: down) and is not part of this update.

**Security TODO (PI-directed, 2026-08-31):** historical hardcoded `llamaparse` credentials are
reported to exist outside this repository and should be rotated or removed by whoever administers
that environment. No credential value is or should ever be recorded in this repo — see `CLAUDE.md`
§12.

## Consolidation status (2026-08-31, PI-directed)

Per the PI: all four Wave 1 branches (`worktree-wave0-init`, `worktree-pit-eze-guideline-risk-wave1`,
`worktree-trials-efficacy-wave1`, `worktree-safety-pharm-wave1`) plus the Director's Gate 1 commits
have been reviewed, secret-scanned, committed, and consolidated into local `main` by the supervising
Codex process. Director confirmed via `git log` that local `main` does contain all four branches'
Wave 1 work, and merged `main` into its own working branch (`worktree-wave0-init`) to pick up the
three specialists' actual output files for direct visibility — a same-branch catch-up, not an act of
branch consolidation, per the PI's "do not merge branches yourself" instruction (that instruction
governs consolidating *other* branches into `main`, which this session has not done and will not
do). `origin/main` was observed to still show only the Wave 0 commit as of this entry — the local
consolidation has evidently not yet been pushed to `origin` by the Codex process; not this session's
concern to resolve.

## Wave 3 update (2026-08-31, PI-authorized)

Gate 2 → Wave 3 transition authorized by the PI (Decision 2026-08-31-28). Synthesis in
`40_SYNTHESIS/` authorized; `50_MANUSCRIPT/` explicitly not authorized this wave. All work this wave
(Director + every dispatched peer) runs on model sonnet. `05_STATUS.md` remains the authoritative
current-gate/wave pointer — this manifest is not edited in place for gate transitions, per the
additive-versioning principle already established above.
