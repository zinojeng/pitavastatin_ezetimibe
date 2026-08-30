# pitavastatin-ezetimibe-evidence

A recoverable, auditable Claude Code Cross-session Research repository for a clinical evidence
review of pitavastatin, ezetimibe, and pitavastatin/ezetimibe fixed-dose combination (FDC) therapy
in dyslipidemia management — built for a clinical talk / manuscript by Dr Tseng (童綜合醫院 新陳代謝科).

## Start here

1. **`CLAUDE.md`** — the project's operating rules: persistent roles, file ownership, Wave/Gate
   rules, the prioritized search protocol, message schema, evidence hierarchy, MCP source policy,
   licensing/secrets rules, and every prompt template needed to run or resume a session.
2. **`docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`** — the general Cross-session Research operating
   system this project instantiates (durable copy of the repo-root legacy Runbook file).
3. **`research/pitavastatin-ezetimibe-evidence/<RUN_ID>/`** — the actual research run. Current:
   `2026-08-31-v1`. Read `05_STATUS.md` in that folder first to see where the run currently stands.

## Legacy input files (repo root, read-only, do not delete/overwrite)

- `pitavastatin topic.md` — PI's topic/angle notes; source of the search protocol.
- `Claude_Code_Cross-Session_Research_完整建議與經驗_Runbook.md` — source of `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`.
- `Tonvasca_2026.md` — existing slide-deck source material (unverified legacy citations to be
  independently re-verified, not assumed correct).

## Repository layout

```text
CLAUDE.md
README.md
.gitignore
docs/
  CROSS-SESSION-RESEARCH-RUNBOOK.md
research/
  pitavastatin-ezetimibe-evidence/
    2026-08-31-v1/
      00_RUN-MANIFEST.md
      01_RESEARCH-CHARTER.md
      02_SOURCE-INVENTORY.md
      03_DECISION-LOG.md
      04_OPEN-QUESTIONS.md
      05_STATUS.md
      10_DATA/            numeric extraction tables (per-role subfolders)
      20_EVIDENCE/        evidence notes, evidence-hierarchy-tagged (per-role subfolders)
      30_METHODS/         methodology notes (per-role subfolders + shared/)
      40_SYNTHESIS/       Director-integrated evidence map / clinical synthesis
      50_MANUSCRIPT/      manuscript/slide work (unowned pending an open question)
      90_CROSS-SESSION-LOG/  append-only control-plane message log
      99_FINAL-QA.md      independent auditor's output (read-only elsewhere)
```

Full-text PDFs and any parsed full text stay local and are gitignored by default; only metadata,
extraction tables, citations, and synthesis are committed. See `CLAUDE.md` §11.

## Governing principle

> Cross-session outside, Workflow inside. Persistent sessions are departments; workflows/subagents
> are temporary labor; the repository is the durable source of truth; the Research Director
> orchestrates; the independent auditor finds errors.

Current status: see `research/pitavastatin-ezetimibe-evidence/2026-08-31-v1/05_STATUS.md`.
