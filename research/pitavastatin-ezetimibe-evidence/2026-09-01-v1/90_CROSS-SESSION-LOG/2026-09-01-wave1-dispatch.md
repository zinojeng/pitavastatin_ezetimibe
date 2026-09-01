# Cross-session log — 2026-09-01, Wave 1 dispatch

Sent to all three specialists (resume + TASK_ASSIGNMENT combined, given time-sensitivity of the
`official/` candidate-source verification): full message text preserved in each session's own
transcript; summarized here per `CLAUDE.md` §6 ("full content stays in the repo... only in the
message" — task framing reproduced below at summary level; the specialists' own detailed findings
will land in their owned `10_DATA/`/`20_EVIDENCE/`/`30_METHODS/` paths, not this log).

| To | msg_id | Priority tasking |
|---|---|---|
| `pit-eze-guideline-risk [dac378]` | `6907ecde-28a5-45e6-ad83-07bbafa874c6` | P1: verify `inbox/2026-acc-aha-drive/official/` candidate primary source (DOI resolution, PDF spot-check, JACC-DOI relationship). P2: focus area 1 (exact 2026 guideline wording) + intake dedup/verification. |
| `pit-eze-trials-efficacy [615600]` | `7b2cb6cc-7e12-4631-b569-99a7c32769c5` | Focus areas 2 (direct FDC evidence + RWE search) and 3 (HIJ-PROPER vs RACING, no conflation) + trial-side attack/defense drafting. |
| `pit-eze-safety-pharmacology [192773]` | `b0103f5f-dacb-4616-a28a-7d4d2551d65c` | Focus area 4 (clinical positioning: glycemic, DDI, polypharmacy, elderly/Asian/Taiwan, CKD, tolerability/adherence) + safety-side attack/defense drafting. |

All three instructed to: apply both the `CLAUDE.md` §7 Evidence Hierarchy tag and the new claim-safe
distinction taxonomy (`01_RESEARCH-CHARTER.md` focus area 6) to every claim; never edit
`02_SOURCE-INVENTORY.md` directly; use `BLOCKED_FOR_SOURCE`/`BLOCKED_FOR_ANALYST`/`BLOCKED_FOR_PI`
rather than guess; no Sci-Hub, no `mcp__research_hub__download_paper`; write only to owned paths.

**Gate 0 status:** not yet formally declared `READY_FOR_NEXT_WAVE` — waiting on `READY` replies (or
substantive findings, which several specialists were invited to send directly given time-sensitivity)
from all three before treating Wave 1 as fully underway. This is a deliberate relaxation of strict
wait-for-READY-before-any-work sequencing, justified by: (a) all three specialists are the same
long-lived, already-oriented roles from the just-closed prior run (not fresh spawns needing first-time
orientation), and (b) the `official/` candidate-source finding is time-sensitive enough that waiting
for a formal round-trip before guideline-risk can even start reading it would cost real time for no
governance benefit. Gate 0 will still be formally closed only once all three have responded.

## Addendum — safety-pharmacology BLOCKED_FOR_SOURCE, resolved

`pit-eze-safety-pharmacology` correctly reported `BLOCKED_FOR_SOURCE`: it checked `origin/main` and
three remote branches via `git ls-tree` and found no `2026-09-01-v1/` anywhere, since the Director's
Wave 0/1 commits (`960741f`, `a9c2a0c`, `601cbdd`) are local-only on `worktree-pit-eze-run-2026-09-01`
and (per the PI's explicit no-push instruction for this run) not pushed to `origin`.

Director confirmed via `git worktree list` that all sessions here are linked worktrees of one shared
local repository (`git-common-dir` identical across them) — local branches are visible to every
worktree via plain `git log <branch>`/`git show <branch>:<path>` without any push/fetch. Also
observed: `guideline-risk-intelligence` had already independently discovered this and created its own
new worktree off `worktree-pit-eze-run-2026-09-01` (at commit `a9c2a0c`) without reporting a blocker —
confirming the fix works. Replied to safety-pharmacology with the exact commands to check locally;
no PI escalation or push was needed.
