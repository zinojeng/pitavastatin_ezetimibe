# Search Log — guideline-risk-intelligence, RUN_ID 2026-09-01-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · Wave 1

## Session start

Resumed per Director's message (new RUN_ID 2026-09-01-v1). Original locked worktree
(`.claude/worktrees/pit-eze-run-2026-09-01`) was in use by another live session (the Director), so
created a fresh worktree (`worktree-pit-eze-guideline-risk-run2026-09-01`) branched from that
worktree's current commit, to inherit the new run's already-created governance files without
touching the Director's in-progress worktree. Read CLAUDE.md (unchanged), the Runbook (unchanged),
and this run's 00-05 governance files in full, including Decision 2026-09-01-01/02/03 and
Open Questions Q1–Q5, before any substantive work.

## MCP connectivity re-check (this session)

- `paper-search` — **down** (`ENOENT: uv not found`).
- `tavily` — **down** (`ENOENT: npx not found`).
- `openevidence` — **down** (`ENOENT: node not found`).
- `research_hub` — connected (metadata/search only; `download_paper` permanently prohibited).
- `google-scholar` — connected, not needed this Wave (Crossref API direct + doi.org sufficed).
- `llamaparse` — connected, not used this Wave (used local `pdftotext`/`pdfinfo` instead — faster
  and sufficient for a targeted grep-driven extraction from a 123-page document already in hand as
  a local file, not requiring OCR or a fresh acquisition).

Given `paper-search`'s per-database DOI tools were unavailable, T-101 verification used direct,
unauthenticated HTTP calls to `doi.org` (DOI Foundation's own resolver) and `api.crossref.org`
(Crossref's public REST API) via `curl` — both are the lawful, no-auth, primary-registry sources
this project's MCP tools would themselves ultimately call; going directly to them was necessary
given the MCP layer's unavailability, not a workaround of any restriction (`CLAUDE.md` §10 names
Crossref itself, not just the MCP wrapper, as an allowed source).

## Work performed

1. Independently recomputed SHA-256/line-count for the `official/` PDF and `.md` (matched the
   intake's own manifest and the Director's Wave 0 note).
2. `pdfinfo` on the PDF — Title/Subject/Pages read directly from the file's own metadata, not
   trusted from any derivative.
3. `strings` pass over the raw PDF bytes — found embedded Adobe Illustrator/Photoshop XMP metadata
   (consistent with genuine publisher figure-production pipeline) but did not find plaintext
   watermark/DOI strings this way (expected — page content streams are FlateDecode-compressed;
   `strings` cannot see through compression).
4. `pdftotext -layout` full extraction (9,931 lines) — the actual verification workhorse. Confirmed
   the "Downloaded from http://ahajournals.org" watermark on every page, the DOI printed in every
   running footer alongside the exact page-date "April 28, 2026," and pulled all quoted content in
   `focus-area-1-guideline-wording.md` from this extraction.
5. `curl https://doi.org/10.1161/CIR.0000000000001423` — confirmed a 302 redirect to a real
   `ahajournals.org` article path (DOI genuinely registered).
6. `curl https://api.crossref.org/works/10.1161/CIR.0000000000001423` (parsed with `python3 -c
   "import json..."`) — independent, authoritative metadata: title/journal/volume/publisher/
   published-print-date/author-list, cross-checked point-by-point against the PDF's own internal
   citation. Exact match on all fields, including the specific publication date (2026-04-28)
   matching the PDF's own footer text independently.
7. Compared this DOI's Crossref author list against the prior run's already-verified Crossref
   record for citation #28 (JACC DOI `10.1016/j.jacc.2025.11.016`) — identical author list/order,
   resolving Q2 (genuine co-publication, not a citation error).
8. Systematic `grep` passes over the `pdftotext` output for: goal-directed/absolute LDL-C targets,
   "early combination"/"upfront combination"/"combination therapy," ezetimibe add-on recommendations,
   statin intolerance/SAMS, and the risk-stratified target-attainment table — results in
   `focus-area-1-guideline-wording.md`.

## Not done this Wave (deferred, noted for the Director)

- Q3 (`markdown/1-s2.0-S0735109725102544.md`) — not searched for; recommended moot given direct
  primary verification succeeded (see `T-101-official-source-verification.md` §6).
- Intake dedup (34 secondary-drafted files, 8 topic-slot families) — not started this Wave; T-101
  verification and focus-area-1 extraction were prioritized per the Director's explicit ordering.
  Flagging as the next task if the Director wants it before Gate 1.
- Taiwan STS 2026 / Taiwan Lp(a) 2026 / the 2019 ESC/EAS base guideline (prior run's #34) — carried
  forward as still `BLOCKED_FOR_SOURCE`, not re-attempted this Wave (no new access route found or
  tried; Director's message did not ask for a retry on these specifically this Wave).
