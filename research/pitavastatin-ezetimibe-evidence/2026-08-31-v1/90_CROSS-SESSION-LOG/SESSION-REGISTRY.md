# Session Registry — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Compiled by: Research Director, at Wave 2 dispatch (2026-08-31), from a live `ListAgents` call.
Additive — re-run `ListAgents` and append/update rather than deleting stale rows; strike through
(don't delete) a row for a session that has ended, and note when.

## Identifier note

`ListAgents` exposes each session by **name** (the address used in `SendMessage`) plus a **short
ref** in brackets (used to disambiguate when a name collides). It does not expose a longer canonical
agent ID for named cross-machine sessions. A `uds:/tmp/cc-socks/<port>.sock` path has also been
observed in the `from=` attribute of incoming cross-session messages from each peer — recorded below
as an additional identifier, but flagged as **transport-layer and not guaranteed stable across a
peer's own reconnects/restarts** (unlike the name+ref pair, which is the durable address). When in
doubt, address peers by **name** — it is what `SendMessage` resolves reliably.

## This project's persistent roles

| Role (name) | Short ref | Observed socket path (transport, may rotate) | Kind | Status as of last check | Notes |
|---|---|---|---|---|---|
| `pit-eze-research-director` | `33d078` | n/a (this session) | background | active (this session) | Research Director. `ListAgents` shows this session's own row omitted (would be self-addressing). |
| `pit-eze-guideline-risk` | `a7823a` | `uds:/tmp/cc-socks/72394.sock` (as of its Wave 1 messages) | background | idle | guideline-risk-intelligence. Wave 1 complete, `READY_FOR_INTEGRATION`. |
| `pit-eze-trials-efficacy` | `ce9a36` | `uds:/tmp/cc-socks/72378.sock` (as of its Wave 1 messages) | background | idle | trials-efficacy-intelligence. Wave 1 complete, `READY_FOR_NEXT_WAVE`. |
| `pit-eze-safety-pharmacology` | `5c9140` | `uds:/tmp/cc-socks/14187.sock` (as of its Wave 1 messages) | background | idle | safety-pharmacology-intelligence. Wave 1 complete, `READY_WITH_PENDING_ITEMS` (T-013 self-queued, commit-permission question open with PI). |
| independent-auditor | *(not yet spawned)* | — | — | not started | Wave 4 only, per `CLAUDE.md` §2.5. |

All three domain specialists confirmed reachable via a live `ListAgents` call at Wave 2 dispatch time
(2026-08-31) — see the dispatch messages logged in this same `90_CROSS-SESSION-LOG/` directory.

## Other sessions visible in `ListAgents` — NOT part of this project

The account/machine also has concurrent, unrelated sessions from other projects (a GLP-1/incretin
research effort, apparently run by the same PI). Listed here only so a future Director doesn't
mistake them for this project's peers — **do not address these from this project**:

| Name | Short ref | Kind |
|---|---|---|
| `incretin-research-director (2)` | `2d5f8b` | background |
| `glp1 memory role consistency` | `bbf94d` | background |
| `incretin metabolic evidence` | `d9b443` | background |
| `gip-mechanism-specialist` | `c69c55` | interactive |
| `gip-mechanism-specialist` | `881bac` | background (name collision with the interactive session above — use the ref to disambiguate if ever needed) |
| `glp1 memory session roles` | `77ec2d` | background |
| `incretin-source-evidence` | `60cf86` | background |

## Git branches associated with each role (as of Wave 2 dispatch)

| Role | Branch | Path | Push/commit state |
|---|---|---|---|
| Director | `worktree-wave0-init` | `.claude/worktrees/wave0-init/` | Pushed to `origin`. Just merged local `main` in to pick up the other three roles' output files (see `03_DECISION-LOG.md`). |
| guideline-risk | `worktree-pit-eze-guideline-risk-wave1` | `.claude/worktrees/pit-eze-guideline-risk-wave1/` (per its reports) | Pushed to `origin`. |
| trials-efficacy | `worktree-trials-efficacy-wave1` | `.claude/worktrees/trials-efficacy-wave1/` | Committed locally only, per its task instructions (no push). |
| safety-pharmacology | `worktree-safety-pharm-wave1` | `.claude/worktrees/safety-pharm-wave1/` | Not committed as of its last report; a PI decision on relaxing its "no commit" instruction is still open (`04_OPEN-QUESTIONS.md`). |

Per the PI (2026-08-31): all four branches, plus the Director's Gate 1 commits, have been reviewed,
secret-scanned, committed, and consolidated into local `main` by the supervising Codex process. `main`
has not yet been pushed to `origin` as of this registry (`origin/main` still shows only the Wave 0
commit) — noted for transparency, not treated as a discrepancy to resolve by this Director (per the
PI's explicit "do not merge branches yourself" instruction, pushing `main` is likewise left to the
PI/Codex process, not this session).

---

## Update — Post-Gate-2 documentation-only check, 2026-08-31 (later same date)

Compiled from a fresh, live `ListAgents` call plus direct git inspection. **Additive — nothing above
this line is edited or deleted; this section supersedes only the "Director active (this session)" /
"main not pushed" facts that had gone stale, per the rows below.**

### Task/project state (per `05_STATUS.md`, `03_DECISION-LOG.md` — content facts, not liveness claims)

- **Gate 2: `READY_WITH_PENDING_ITEMS`** (Decision 2026-08-31-27). Both PI-required LlamaParse
  demonstrations remain confirmed satisfied.
- **Wave 3: not opened.** No new research/acquisition authorized since Gate 2.
- **Six sources remain explicitly `BLOCKED_FOR_SOURCE`/`NEEDS_PI`, unchanged**: Taiwan STS 2026
  (T-005), Taiwan Lp(a) 2026 (T-006), base 2019 ESC/EAS (#34), 2026 ACC/AHA (#28), ESC 2025 Focused
  Update (T-007), citation #33 (Chou MT 2022)'s safety tables. Per standing PI instruction, no
  assumption is made that these can be supplied, and no further acquisition is authorized.
- **All three specialists have no pending assigned Wave-2 work and are recorded as idle/standing by**
  per `05_STATUS.md`'s "Next action" section: *"None pending from the specialists — all three are
  idle, standing by."* Two additional narrow post-Gate-2 Director checkpoints (commits `2c4b16a`/
  `45f93ce` on this branch, `ca44059`/`b03590c` on `main`) verified a stale #35 cross-reference and
  independently re-confirmed a trials-efficacy fulltext-repair commit — neither reopened Wave 2 work
  for any specialist nor changed the above.

### Live reachability, as actually observed via `ListAgents` just now — reported as observed, not assumed

- **This session's own registered name is `wave0-init-75` [945f8a]** — not `pit-eze-research-director`
  as Wave 2's registry entry recorded. This is a session-identity change (likely from a context
  compaction/resume), not a project-state change; noted for transparency, not corrected/resolved by
  this session.
- **A separate peer named `pit-eze-research-director` [a2c0d8] is currently live**, `background`,
  `idle`, started ~4 minutes before this check. Two sessions now answer to/near the Director identity
  — flagged for the PI's awareness. This session did not contact it, to avoid duplicate-Director
  activity (Runbook Golden Rule 1) — reconciling this is a PI-level call, not something to
  self-resolve.
- **`pit-eze-safety-pharmacology` [5c9140]** — confirmed live, `background`, `idle` (started ~5h before
  this check, i.e. the same long-running session from Wave 2).
- **`pit-eze-trials-efficacy` [1a2045]** — confirmed live, `background`, `idle`. **Ref changed from
  `ce9a36` (recorded above at Wave 2 dispatch) to `1a2045`, and per `ListAgents`' own "started ~4m
  ago" timing this appears to be a recently (re)started session, not the original continuously-running
  one** — noted, not further investigated (out of scope for a documentation-only pass).
- **`pit-eze-guideline-risk` did NOT appear in this `ListAgents` call at all.** Its current live
  reachability is **unverified** — this section makes no claim about whether it is running. Its last
  known task-state (per `05_STATUS.md`, above) was idle/standing by with no pending Wave 2 work; that
  remains the project's task-state record regardless of current process liveness, which this session
  could not confirm either way.

### Git state, independently verified

- **Local `main` and `origin/main` are both at `b03590c`** (`git fetch origin` + `git log --oneline`
  on both refs, run this check) — **confirmed synchronized**, consolidating through both post-Gate-2
  checkpoint commits. This supersedes the "main not yet pushed to origin" note recorded above at Wave
  2 dispatch time, which is now stale.
- This session's own branch (`worktree-wave0-init`) is currently **behind** local `main` by ~1,130
  lines across 18 role-owned files (`10_DATA/`, `20_EVIDENCE/`, `30_METHODS/` extraction/evidence/
  search-log files for all three specialists) — expected staleness from the established pattern
  (Director branch carries Director-authored commits plus periodic catch-up merges; specialist detail
  accumulates on `main` via the Codex consolidation process between merges), not a content
  contradiction. Not remerged this pass — out of scope for a documentation-only check; flagged for
  whenever the Director next needs direct access to that specialist-owned detail.
- `git ls-files` / `git status --porcelain --ignored`: no `.pdf`/`.parsed.md`/`fulltext/` path tracked;
  both shared and per-role `fulltext/` directories confirmed still gitignored.
- `git grep` for API-key/secret-key/password/bearer-token/AWS-key patterns across all tracked files:
  no matches (only benign self-references — `.gitignore`'s own pattern lines, and prior checkpoint
  logs' text *describing* that a scan was run).
- **One genuine content inconsistency found and fixed** (outside this file, per the task's allowance
  for a control-plane correction when one is found): `04_OPEN-QUESTIONS.md` still listed citation #30
  (2023 TSC CCS), #32 (ADA 2025), and #35 (2022 Taiwan primary-prevention companion) as
  "numeric-threshold confirmation still pending," even though all three were separately confirmed
  obtained/content-verified earlier (Decision 2026-08-31-23; the prior #35 checkpoint). Corrected to
  list only the two still-genuinely-blocked documents (T-006, #34) plus #29 (citation-verified only,
  never separately pursued for full-text thresholds) as pending.

---

## Update — Wave 3 dispatch, 2026-08-31 (fresh `ListAgents`, resolves the prior duplicate-Director note)

The previous section flagged a possible second live `pit-eze-research-director` session as a
documentation-only observation. Re-checked via a fresh `ListAgents` call at Wave 3 start: **this
session is confirmed the sole live session named `pit-eze-research-director`, now at ref `a2c0d8`**
(was `33d078` at Wave 2 dispatch, `945f8a`/`wave0-init-75` per the prior stale intermediate note —
ref/name churn across resumes, not distinct concurrent Directors; no duplicate exists as of this
check).

Current live refs, all reachable by name:

| Role (name) | Ref at this check | Notes |
|---|---|---|
| `pit-eze-research-director` | `a2c0d8` | This session. |
| `pit-eze-guideline-risk` | `89b096` | Very recently (re)started (~1m old at check) — given a resume-prompt reminder in its Wave 3 dispatch. |
| `pit-eze-trials-efficacy` | `1a2045` | Started ~31m before check (a prior resume, not this turn's). |
| `pit-eze-safety-pharmacology` | `5c9140` | Same long-running session since Wave 2 (~6h old at check) — ref stable across the whole project so far. |

**Takeaway for future Directors reading this registry**: refs are session-scoped and change across
restarts/resumes — **address peers by name**, per the Identifier note at the top of this file, and
re-run `ListAgents` at the start of every wave rather than trusting a previously-recorded ref.
