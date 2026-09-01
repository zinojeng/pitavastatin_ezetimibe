# 03_DECISION-LOG — pitavastatin-ezetimibe-evidence / 2026-09-01-v1

Continues the decision-numbering convention from `2026-08-31-v1/03_DECISION-LOG.md` (which reached
Decision 40) but restarts the counter under this RUN_ID's own date prefix for clarity, per that run's
own additive-versioning precedent. Append-only.

---

### Decision 2026-09-01-01 — Duplicate-Director collision resolved by stand-down, not by silent merge

**Context:** At Wave 0 orientation, `ListAgents` showed a second live `pit-eze-research-director
[853c1a]` session (`busy`), concurrent with fresh restarts of all three specialist peers — strong
evidence the same PI directive reached two channels.

**Decision:** Per Golden Rule 1 (never silently substitute for/duplicate a peer), this Director
(`[5aa219]`) held all writes and sent a `CONFLICT` cross-session message before creating any file.
`[853c1a]` responded with full disclosure (working in isolated worktree `worktree-wave0-init`, two
draft files only, no specialist contact, nothing committed/pushed) and stood down unconditionally,
including a commitment not to push its branch or contact specialists. A follow-up `ListAgents` showed
`[853c1a]` no longer listed (session ended).

**Resolution:** `[5aa219]` proceeds as sole Research Director for `2026-09-01-v1`, writing the
manifest/charter fresh (not pulling `[853c1a]`'s draft) to keep authorship of Director-owned
governance files unambiguous. No specialist received conflicting task assignments — the collision
was caught and resolved before either Director dispatched real work, which is the intended outcome
of the health-check protocol (`CLAUDE.md` §13).

**Evidence Hierarchy tag:** n/a (governance/process decision, not a clinical claim).
**Decision Taxonomy:** n/a (control-plane resolution, not an evidentiary decision).

---

### Decision 2026-09-01-02 — `inbox/` excluded from git tracking wholesale

**Context:** The new Google Drive intake (`inbox/2026-acc-aha-drive/`, 35 files) plus an unplanned
`official/` subfolder (a 16.9 MB PDF + 697 KB `.md` derivative claiming to be the actual 2026 ACC/AHA
guideline) were found untracked in the working tree. The existing `.gitignore` only excluded
`**/*.pdf`/`**/*.PDF`, not `.md` derivatives or the small intake drafts.

**Decision:** Added a new `.gitignore` section excluding `inbox/` entirely, extending the existing
full-text/licensing principle (`CLAUDE.md` §11: full text is local-only until redistribution rights
are verified) to the intake folder as a whole, since intake material is explicitly unverified
secondary material per the PI's own instruction. Only curated, verified extractions written into
`10_DATA/`/`20_EVIDENCE/` by specialists are tracked — never the raw intake files themselves.

**Note:** this edit was first (mistakenly) applied to the shared checkout's `.gitignore` before this
session isolated into its own worktree (a background-job isolation guard blocked a subsequent file
creation but had already allowed this edit through). The same edit was then correctly reapplied
inside the isolated worktree. The stray uncommitted edit in the shared checkout is content-identical
and harmless (adds `inbox/` to a gitignore, touches no tracked research content) — flagged
transparently here and to the PI/user rather than silently left unmentioned; it can be committed,
reverted, or ignored without consequence when this branch is later consolidated.

**Evidence Hierarchy tag:** n/a. **Decision Taxonomy:** n/a (governance).

---

### Decision 2026-09-01-03 — `official/` guideline file treated as unverified candidate primary source, not fact

**Context:** `inbox/2026-acc-aha-drive/official/2026_ACC_AHA_Multisociety_Dyslipidemia_Guideline_
Circulation.{pdf,md}` appeared in the intake folder, timestamped 2026-09-01 10:50–10:52 (after this
run's authorization message), with an accompanying `OFFICIAL_SOURCE_MANIFEST.md` claiming it is the
official *Circulation* 2026;153:e1154–e1276 publication, DOI `10.1161/CIR.0000000000001423`.

**Decision:** Despite Director's Wave 0 spot-check finding it highly plausible (matching SHA-256/
line-count self-report, realistic PDF-extraction artifacts, correct internal self-citation, and
topical — though not line-exact — agreement with 3–4 of the intake's own `adjudication_log_v2.md`
claimed corrections), **this file is NOT treated as verified.** Per the Tool-Confabulation Caution
(`CLAUDE.md` §9) and the Numeric Integrity Rule, "looks real" is not "independently confirmed."
guideline-risk-intelligence is assigned, as Wave 1 priority #1, to: (a) attempt DOI resolution via
doi.org/Crossref/PubMed (lawful metadata tools only — `research_hub` search tools, not
`download_paper`), (b) spot-check a sample of quoted recommendations against the **PDF**, not just
the `.md` derivative (to rule out conversion-introduced errors), (c) explicitly investigate whether
this DOI and the prior run's still-`BLOCKED_FOR_SOURCE` `10.1016/j.jacc.2025.11.016` are two genuine
co-publication DOIs for the same joint guideline or a citation error, and (d) report findings via the
standard message schema for the Director to record in `02_SOURCE-INVENTORY.md` — never to silently
treat the file as authoritative in the meantime.

**Evidence Hierarchy tag:** `INSUFFICIENT EVIDENCE` (pending verification) — not yet eligible for any
higher tag. **Decision Taxonomy:** `NEEDS_ANALYST` (routed to guideline-risk-intelligence).

---
