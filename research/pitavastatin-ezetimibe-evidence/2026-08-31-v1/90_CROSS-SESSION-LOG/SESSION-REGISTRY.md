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
