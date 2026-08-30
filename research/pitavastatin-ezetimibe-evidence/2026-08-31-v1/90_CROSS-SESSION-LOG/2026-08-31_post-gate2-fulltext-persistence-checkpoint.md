# Cross-session log — post-Gate-2 checkpoint: trials-efficacy fulltext persistence repair (f30023c) — 2026-08-31

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Logged by: Research Director (`pit-eze-research-director`)

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]             2026-08-31-v1
[FROM]           Research Director
[TO]             90_CROSS-SESSION-LOG (control-plane record; PI-facing)
[TYPE]           STATUS_REPORT
[FINDING]        trials-efficacy-intelligence's commit f30023c (branch worktree-trials-efficacy-
                 wave1; content-identical to main's 76f4f51 — same patch, cherry-picked, only the
                 commit hash differs) is a narrow, correctly-scoped persistence repair, not new
                 research. TE-002 (Tsujita 2023) and TE-003 (Ako 2024) PDFs/LlamaParse markdown,
                 lost when their prior $CLAUDE_JOB_DIR temp copies disappeared, were re-downloaded
                 from the exact J-STAGE URLs already on record and re-parsed. Independently verified
                 this checkpoint:
                 - SHA-256 of both PDFs on disk in the consolidated main working directory
                   (afe6befc...4022c26 for TE-002, 1e103ff0...1ac960 for TE-003) recomputed via
                   `shasum -a 256` and matches both the commit's claimed value AND the original
                   Wave 2 record in the same manifest file byte-for-byte — confirms genuine
                   byte-identical re-download, not a fabricated/copied hash.
                 - `git check-ignore -v` on all 6 files in the new
                   `20_EVIDENCE/trials-efficacy/fulltext/` path (2 PDF, 2 parsed .md, 2 header logs)
                   confirms all matched by `.gitignore:16` (`**/20_EVIDENCE/**/fulltext/`).
                 - `git ls-files` across `20_EVIDENCE/` in the consolidated main working directory
                   confirms zero PDF/parsed-fulltext files tracked (only the pre-existing, legitimate
                   `guideline-risk/wave2-fulltext-extraction.md` extraction-table file matched, which
                   is expected committed content, not raw full text).
                 - Same pattern independently confirmed for the other two specialists: guideline-risk
                   (`20_EVIDENCE/guideline-risk/fulltext/`, 5 source PDFs + parsed .md) and
                   safety-pharmacology (`20_EVIDENCE/safety-pharmacology/fulltext/`, 2 source PDFs +
                   parsed .md) both exist on disk in the consolidated main working directory and are
                   likewise fully gitignored and untracked — the three-role fulltext-persistence
                   state described in the task is accurate as of this checkpoint.
                 - `git show f30023c --stat` confirms only 2 files touched, both role-owned
                   (`10_DATA/trials-efficacy/fulltext-manifest.md`,
                   `90_CROSS-SESSION-LOG/trials-efficacy-intelligence.md`) — no shared file (00-05,
                   02/03, 99) or other role's path touched.
                 - Secret scan (`grep -iE` for API-key/token/password/bearer/secret patterns) on the
                   commit's full diff — no hits.
                 - `05_STATUS.md`/`04_OPEN-QUESTIONS.md` (consolidated main working directory, the
                   live governance copy) re-read: Gate 2 still `READY_WITH_PENDING_ITEMS`
                   (Decision 2026-08-31-27), Wave still 2, Wave 3 explicitly "not opened," and the
                   same six `BLOCKED_FOR_SOURCE` items (T-005 Taiwan STS 2026, T-006 Taiwan Lp(a)
                   2026, #34 base 2019 ESC/EAS, #28 2026 ACC/AHA, T-007 ESC 2025 Focused Update,
                   #33 Chou MT 2022 safety tables) unchanged — f30023c does not touch, resolve, or
                   otherwise affect any of them.
[IMPACT]         TE-002/TE-003 full text is durably available again at a role-owned, gitignored path
                 for future Wave-3-or-later extraction use, matching the Wave 2 record exactly
                 (byte-identical PDFs; markdown content-complete on inspection, minor non-substantive
                 byte-count drift between LlamaParse calls already explained and accepted by the
                 specialist). No change to Gate 2 status, Wave count, the six blockers, or any prior
                 Wave 1/Wave 2 conclusion. No shared governance file required correction this
                 checkpoint (unlike the prior #35 checkpoint, no stale entries were found).
[ACTION]         None required on shared files (00-05, 99) — none touched by f30023c, none found
                 inconsistent by this checkpoint's re-read. Noting one pre-existing, unrelated
                 provenance-location fact for the record only (not actioned, not a defect introduced
                 by this repair): `worktree-wave0-init` (this branch) and `main` diverged after the
                 Wave-2-PI-authorization point (12 commits ahead / 14 behind) — f30023c itself lives
                 only on `worktree-trials-efficacy-wave1`, and its content reached the consolidated
                 main working directory as a separately-hashed but patch-identical commit (76f4f51),
                 not as a merge into this branch. This mirrors the same gap already recorded in the
                 prior post-Gate-2 #35 checkpoint and is not re-actioned here — same "do not merge
                 branches in this session" boundary applies (Decision 2026-08-31-12 item 4).
[OUTPUT_PATHS]   This file only. No edits made to 00_RUN-MANIFEST.md, 01_RESEARCH-CHARTER.md,
                 02_SOURCE-INVENTORY.md, 03_DECISION-LOG.md, 04_OPEN-QUESTIONS.md, 05_STATUS.md, or
                 99_FINAL-QA.md this checkpoint.
[CONFIDENCE]     HIGH (SHA-256 independently recomputed and matched, not merely re-read from the
                 commit message; gitignore/tracked-file state independently checked via git
                 plumbing commands, not taken on the specialist's word).
[STATUS]         READY_FOR_INTEGRATION
```

## Verification checks run this checkpoint

- **Commit inspection**: `git show f30023c --stat` and full diff read — confirms 2 files changed
  (`10_DATA/trials-efficacy/fulltext-manifest.md`, `90_CROSS-SESSION-LOG/trials-efficacy-intelligence.md`),
  both trials-efficacy-owned, 74 insertions, 0 deletions, no other path touched.
- **Cross-check against main**: `diff <(git show f30023c -- <file>) <(git show 76f4f51 -- <file>)`
  for both changed files — patches are identical apart from the commit-hash header line, confirming
  the consolidated main working directory's 76f4f51 carries the same content, not a divergent or
  conflicting version.
- **SHA-256 recomputation**: `shasum -a 256` run directly on
  `20_EVIDENCE/trials-efficacy/fulltext/TE-002_Tsujita2023.pdf` and `TE-003_Ako2024.pdf` in the
  consolidated main working directory — both match the commit's claimed hashes and the original
  Wave 2 manifest record exactly.
- **Gitignore/tracked-file check**: `git check-ignore -v` on all trials-efficacy, guideline-risk,
  and safety-pharmacology `fulltext/` contents (13 files total across the three roles) — all
  matched by `.gitignore:16`. `git ls-files` restricted to `20_EVIDENCE/` — no PDF or parsed-fulltext
  file tracked for any of the three roles.
- **Secret scan**: pattern grep (api[_-]key, token, password, secret, bearer, authorization:,
  sk-<hash>) across the commit's diff — no hits.
- **Governance re-read**: `05_STATUS.md` and `04_OPEN-QUESTIONS.md` in the consolidated main working
  directory re-read in full — Gate 2 `READY_WITH_PENDING_ITEMS`, Wave 3 not opened, six blockers
  unchanged, all consistent with the pre-checkpoint state. No edit made.

## Not actioned (out of scope for this checkpoint)

The `worktree-wave0-init` / `main` branch divergence noted above is a pre-existing condition from
Wave 2 (not introduced or worsened by f30023c) and is recorded here for continuity with the prior
#35 checkpoint's note, not resolved. No branch merge performed in this session.
