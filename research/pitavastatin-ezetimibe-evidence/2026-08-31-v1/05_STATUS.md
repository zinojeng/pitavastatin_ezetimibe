# 05_STATUS — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Last updated: 2026-08-31 (PR #1 closure housekeeping, Decision 2026-08-31-40, Research Director)

> **Housekeeping note:** this file had accumulated many superseded "Update —" sections from rapid
> Wave 1/2 processing. Condensed here into a single current narrative; no information dropped — see
> git history for the previous, more granular version if a specific timestamp/sequence is needed.

> **CONSOLIDATION-STATUS HISTORY (preserved as historical context — see Decisions 2026-08-31-35
> through -37 for the full sequence):** `main` was reported stale at `a8507d2` pending PR #1, then
> the supervising Codex process cherry-picked Wave 3/4 content into *local* `main` (through Decision
> 35) while `origin/main` remained unpushed and PR #1 stayed open — both true statements at the time
> they were recorded.
>
> **DECISION 38 SNAPSHOT (2026-08-31, supervising Codex process — GitHub sync completed once; now
> itself historical):** the supervising Codex process completed final QA on local `main` and pushed
> `main` to `origin` successfully; Director-verified at that time via `git fetch origin` +
> `git rev-list --left-right --count main...origin/main` that both local `main` and `origin/main`
> resolved to the same commit, `275ab90`, zero divergence (`0 0`). **This was itself a point-in-time
> snapshot, not a durable fact**: the Decision 38 documentation commit recording that snapshot was
> then itself integrated by the supervising process into `main` (as is expected for every
> documentation-only Director commit), which necessarily advances `main`'s HEAD again — Director
> re-verified after that integration that local and `origin` `main` again showed zero divergence,
> confirming the sync process is working repeatedly and correctly, not just as a one-off.
>
> **DURABLE CURRENT-STATE STATEMENT (hash-independent, so this sentence does not go stale on the
> next documentation-only integration pass)**: GitHub `main` synchronization is an ongoing,
> periodically-reconfirmed process, not a single event — each time the supervising Codex process
> integrates a new Director governance commit into `main`, it (and independently, this Director
> session when asked) has re-confirmed zero divergence between local and `origin` `main` afterward.
> **Do not treat any specific commit hash recorded in this file as the current `main` HEAD** — verify
> live via `git fetch origin && git rev-list --left-right --count main...origin/main` (expect `0 0`)
> if an exact reference is needed. **[PR #1](https://github.com/zinojeng/pitavastatin_ezetimibe/pull/1)
> is now `CLOSED` (superseded)** — closed by the repo owner after the supervising Codex process
> compared all 26 changed paths against `origin/main` and found zero object-content mismatches; the
> closing comment documents that no unique PR content was discarded. No open PI decision remains on
> this point (Decision 2026-08-31-40). This Director branch has not been used to update `main`, and
> this session has not merged, pushed, or edited `main`, nor mutated the PR itself (its closure was
> performed by the repo owner, not this session). **Final Gate remains unchanged:
> `PASS_WITH_MINOR_ISSUES`; `40_SYNTHESIS/00`–`08` remains `FINAL`.** See Decisions 2026-08-31-35
> through -40 for the full history (each preserved as an accurate record of its own point in time).

## Current Gate

**Gate 1: PASSED** (PI authorization, 2026-08-31, Decision 2026-08-31-12).

**FINAL GATE: `PASS_WITH_MINOR_ISSUES`, 2026-08-31** (Decision 2026-08-31-34 — Wave 4 independent
audit, two passes, one Finding corrected and independently re-verified). **`40_SYNTHESIS/00`–`08`
is `FINAL`.**

**Gate 3: PASSED, 2026-08-31** (Director-run Wave 3 Challenge Round + internal-consistency check —
see `30_METHODS/shared/wave3-challenge-round-and-gate3.md`).

**Gate 2: DECLARED `READY_WITH_PENDING_ITEMS`, 2026-08-31 (Decision 2026-08-31-27, PI-directed).**
Both PI-required LlamaParse demonstrations succeeded (trials-efficacy on the actual assigned
target, Tsujita 2023/T-004a; guideline-risk on a substitute, T-014, after its three assigned targets
were Cloudflare-blocked). Six sources remain `BLOCKED_FOR_SOURCE` (Taiwan STS 2026/T-005, Taiwan
Lp(a) 2026/T-006, base 2019 ESC/EAS/#34, 2026 ACC/AHA/#28, ESC 2025 Focused Update/T-007, citation
#33/Chou MT 2022's safety tables) — per the PI's own exit criteria this is consistent with
`READY_WITH_PENDING_ITEMS`, not a failure. **Per explicit PI instruction: these six stay recorded
as `NEEDS_PI`/`BLOCKED_FOR_SOURCE` — no assumption is made that the PI can or will supply them, and
no further acquisition attempts are authorized without new instruction.** A Wave 2 Challenge Round
was run by the Director across all four Runbook §30 angles — see
`30_METHODS/shared/wave2-challenge-round.md` and `04_OPEN-QUESTIONS.md` for the four priority
findings carried forward. **No Wave 3 is opened at this time**, per explicit PI instruction — T-024
and other not-yet-obtained new-source full texts stay held.

## Wave

3 — Synthesis (`40_SYNTHESIS/` only; `50_MANUSCRIPT/` explicitly NOT authorized this wave) —
**complete, Gate 3 passed**. Wave 4 (independent audit) next.

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

## Wave 2 progress

**guideline-risk-intelligence** reported first: `BLOCKED_FOR_SOURCE` on all 3 assigned priority
documents (Taiwan STS 2026, 2026 ACC/AHA, ESC 2025 Focused Update — all Cloudflare bot-challenged,
corroborated via Europe PMC metadata; no workaround attempted, correctly). **1 of the 2 required
Gate-2 LlamaParse demonstrations succeeded**, but on a substitute open-access source (T-014, a
Blumenthal-coauthored editorial) rather than an assigned target — it doesn't cover ezetimibe, so the
"combination-therapy wording" task item remains unfulfilled. Also: **caught and discarded a
tool-confabulation incident** (a `WebFetch` call fabricated quantitative content while also
reporting the source as paywalled) — commended, led to a new general caution in `CLAUDE.md` §9.
Found a new source (T-015, REPRIEVE trial) while reading T-014's references, correctly routed to
trials-efficacy rather than claimed. Now proceeding to numeric-threshold work on already-accessible
guideline documents while a PI-level question (can the 3 blocked PDFs be supplied directly?) is
outstanding — see `04_OPEN-QUESTIONS.md`.

**trials-efficacy-intelligence** reported second — a strong report. **Both Gate-2 LlamaParse
demonstrations are now confirmed satisfied**: guideline-risk's (on a substitute source) and
trials-efficacy's (on the actual assigned target, Tsujita 2023 — 717,939-byte PDF via J-STAGE after
PMC's anti-bot challenge blocked automated access; 114,893 characters parsed, no truncation). Ako
2024 also successfully obtained/parsed via a derived J-STAGE URL. Full-text extraction yielded two
important nuances now locked into governance: (1) the "add ezetimibe or double the statin?"
head-to-head comparison the topic file's own framing highlights was **not formally tested** in
Tsujita 2023 — only descriptive point estimates exist (Decision 2026-08-31-16); (2) Ako 2024's
"single ADR" abstract framing understates its full AE picture (59.6% overall AE rate; only 1 event
adjudicated as drug-related) — both figures must be cited together going forward (Decision
2026-08-31-17). Chou 2022 and Katzmann 2022 both confirmed `BLOCKED_FOR_SOURCE` after Wave-2-repaired
connectivity (no OA location, direct HTTP checks failed) — no workaround attempted. T-015/REPRIEVE
fully verified (N=7,769, MACE HR 0.65, stopped early for efficacy) — Decision 2026-08-31-18. A new
candidate source, REAL-CAD (T-016), was found secondhand and trials-efficacy was authorized to
pursue its own verification (Decision 2026-08-31-19).

**safety-pharmacology-intelligence** reported third and last — also strong. T-012/Katzmann obtained
lawfully via a direct Europe PMC PMCID lookup (PMC8873069, CC BY 4.0) after trials-efficacy had
reported it blocked via a different method — corrected, not a contradiction (Decision
2026-08-31-20); the resulting method tip was relayed to the other two specialists for their own
blocked sources. T-003/Singh 2024 confirmed `BLOCKED_FOR_SOURCE` (Europe PMC: no OA, no PMCID). T-010
DDI matrix re-verified directly against DailyMed with refinements (clarithromycin confirmed absent
from the label, fenofibrate's correct section location, new fibrate/niacin/colchicine content).
T-013 verified. Two valuable new finds: T-017 (elderly NODM cohort, abstract-only) and **T-018
(Tramontano 2025 CKD-dosing review, cross-verified against the FDA label — resolves most of the
Wave 1 CKD-dosing gap)**. BCRP mechanism partially converged (T-019/T-020) but the pitavastatin-
specific quantitative fold-change number remains open. Remaining gaps: FDC-specific CKD dosing (no
source addresses the combination product), BCRP fold-change number, Chou 2022's safety tables.

## Wave 2 follow-up round (same session, after all three initial reports)

- **Katzmann cohort-*n* fully resolved**: safety-pharmacology pulled both table locations from its
  obtained full text; Director independently confirmed against `Tonvasca_2026.md`'s own text.
  Decision 2026-08-31-11 closed as `NO_CHANGE` (both n pairs correct, different subsets) — no longer
  `SOURCE_CONFLICT`.
- **guideline-risk**: reinforced all 7 blocked-source findings via a rigorous NCBI elink negative
  check (empty PMC linkset, not an OA-flag inference); obtained/content-verified 2023 TSC CCS (#30)
  and ADA 2025 (#32) full text, catching a genuine cross-guideline LDL-C threshold difference; found
  a partial ESC-2025-wording substitute (T-021, with an important "old 2018 guideline" caveat
  preserved). Item 6 was 2/5 complete, 2/5 confirmed blocked, 1/5 (#35) queued next at the time of
  this round. **Post-Gate-2 update (2026-08-31, Director checkpoint — see
  `90_CROSS-SESSION-LOG/2026-08-31_post-gate2-checkpoint-row35.md`): #35 (Huang PH et al. 2022 Taiwan
  primary-prevention guideline) subsequently obtained** via the same tas.org.tw mirror pattern that
  worked for #30/#32, lawfully (CC BY 4.0, confirmed verbatim in parsed text), full COR/LOE-graded
  recommendation text extracted. **Item 6 final: 3/5 complete, 2/5 confirmed blocked (T-006, #34) —
  no target left unattempted.** Already reflected in `02_SOURCE-INVENTORY.md` row #35; this line was
  stale until the post-Gate-2 checkpoint corrected it.
- **trials-efficacy**: independently re-confirmed Chou 2022 (#33) blocked, converging with
  guideline-risk's result via a different method; found two new candidate sources (T-023, a Taiwan
  real-world FDC cohort; **T-024, possibly the first pitavastatin+ezetimibe-FDC-specific
  meta-analysis, flagged highest-priority for Wave 3**).
- New sources this round: T-021, T-022, T-023, T-024 (13 total new sources found across Wave 2:
  T-014 through T-024).

## All three specialists' Wave 2 reports now processed

Every specialist-facing loose end from Wave 2 is closed except: (a) the outstanding PI question on
supplying the 3 (now effectively 4, including Chou 2022) blocked PDFs directly, (b)
safety-pharmacology's follow-up task to pull the Katzmann cohort-*n* from its own already-obtained
full text (should resolve Decision 2026-08-31-11), (c) guideline-risk's and trials-efficacy's
Europe-PMC-PMCID retry on their remaining blocked sources (in progress, not yet reported back).

## Wave 2 dispatch summary (as originally sent)

| Specialist | Assigned Wave 2 targets |
|---|---|
| trials-efficacy | Tsujita 2023 (PMC10627746 or J-STAGE PDF) + Ako 2024 (PMC10918028) full text, LlamaParse on ≥1; exact arm/LDL-C/AE/CK/AST/ALT/HbA1c/significance extraction. Chou MT 2022 AE/CK/liver tables. Katzmann 2022 full text (cohort-size resolution). |
| guideline-risk | Taiwan STS 2026 publisher-authorized fetch attempt (else `BLOCKED_FOR_SOURCE`). Official 2026 ACC/AHA PDF + official ESC 2025 content, LlamaParse on ≥1; exact combination-therapy wording extraction. |
| safety-pharmacology | Singh 2024 + Katzmann 2022 lawful full text (else `BLOCKED_FOR_SOURCE`). DDI validation against official DailyMed/FDA directly. Parse a lawful safety PDF if obtained. Never use `research_hub` download tool. |

**Common requirement for every PDF any specialist touches**: record license/source URL, retrieval
timestamp, SHA-256, parse status, and page/table/section locators. PDFs stay gitignored, never
committed.

## Blocked

Six sources `BLOCKED_FOR_SOURCE` at the content level (Taiwan STS 2026/T-005, Taiwan Lp(a) 2026/
T-006, base 2019 ESC/EAS/#34, 2026 ACC/AHA/#28, ESC 2025 Focused Update/T-007, citation #33's safety
tables) — explicitly accepted as consistent with Gate 2's `READY_WITH_PENDING_ITEMS` state per the
PI's own criteria, not treated as pending PI resolution (see Current Gate above). No
repository-structure or governance-level blocker.

## Wave 2 close-out summary (2026-08-31)

All three specialists' Wave 2 assignments complete. 25 sources now tracked (T-001–T-025) beyond the
original ~35 legacy citations, with the great majority verified or explicitly flagged
not-locatable/blocked (never silently guessed). A Wave 2 Challenge Round was run — see
`30_METHODS/shared/wave2-challenge-round.md` — surfacing 4 priority findings for Wave 3 (Taiwan STS
2026 framing unverified; REPRIEVE/REAL-CAD-to-FDC conflation risk; FDC-specific CKD dosing gap;
Singh 2024's RCT-vs-observational pooling as an unresolved parallel to the Sydhom framing). Full
detail: `02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md` (27 decisions logged), `04_OPEN-QUESTIONS.md`,
`90_CROSS-SESSION-LOG/`.

## Wave 3 OPENED, 2026-08-31 (PI authorization)

**Gate 2 → Wave 3 transition authorized by the PI.** Scope, per explicit PI decision: **synthesis in
`40_SYNTHESIS/` is authorized this wave; manuscript/slide drafting in `50_MANUSCRIPT/` is NOT
authorized this wave.** No merge/push of `main` by this session (unchanged policy). All Claude Code
work this wave, including every resumed/dispatched peer, must run on model **sonnet**.

**Cross-session health check (2026-08-31, this session)**: `ListAgents` confirms this session is
`pit-eze-research-director [a2c0d8]` (the sole live session under that name — an earlier
documentation-only note about a possible duplicate Director identity was a transient artifact of a
session resume, not an actual duplicate; resolved). All three specialists reachable by name:
`pit-eze-guideline-risk` [89b096] (recently restarted), `pit-eze-trials-efficacy` [1a2045]
(recently restarted), `pit-eze-safety-pharmacology` [5c9140] (same long-running session since Wave
2). Director branch caught up to local `main` via the established safe merge-catch-up pattern
(merge `main` into `worktree-wave0-init`, no push/merge of `main` itself) — brought in the
specialists' actual Wave 2 output files (extraction tables, evidence maps, DDI matrix, etc.) for
direct visibility.

**OpenEvidence tool check**: `openevidence` MCP remains disconnected in this session
(`CONNECTION_CLOSED`; `ToolSearch` found no `oe_health`/`oe_auth`-class tools). Recorded as a tool
blocker, not retried further this turn — proceeding on lawful PubMed/PMC/Crossref/Unpaywall/
paper-search/`research_hub` metadata-search paths only, per the PI's fallback instruction. If any
dispatched specialist's own session has a working OpenEvidence relay, it is authorized **at most one
bounded discovery pass** on the six blocked sources (T-005, T-006, #34, #28, T-007, #33) — discovery/
corroboration only, never a substitute for primary-source verification, and must not weaken their
`BLOCKED_FOR_SOURCE` status unless an independently lawful primary source is actually obtained.

**Wave 3 dispatch** (full task detail in `90_CROSS-SESSION-LOG/2026-08-31_wave3-dispatch.md`):
trials-efficacy → T-024 (Abbas 2026) then T-023 (Lu 2026) full text/extraction, build the Level
1/2/3 hard-outcome distinction without conflating RACING/HIJ-PROPER/REPRIEVE/REAL-CAD.
safety-pharmacology → Singh 2024 RCT-vs-observational disaggregation, verify T-009/T-025, search for
FDC-specific CKD dosing and pitavastatin BCRP quantitative data, preserve calibrated NODM/DDI
language. guideline-risk → #29 full-text thresholds, T-008 (Taiwan health-promotion annual report),
exact guideline wording via lawful paths only, preserve the six blockers if primary text stays
unavailable. Each role writes only to its own owned paths; every lawful full text gets provenance/
license/hash/LlamaParse-manifest logging; reports use the standard schema.

**40_SYNTHESIS/ deliverables required this wave** (Director-integrated, after specialist reports):
executive clinical synthesis; claim-evidence matrix (citation IDs + Evidence Hierarchy tags);
guideline/risk-positioning section; LDL efficacy/dose-escalation section; CV-outcomes hierarchy;
glycemic/safety/DDI/CKD section; adherence/residual-risk section; limitations/open gaps; number/
claim/citation traceability table. Traditional Chinese prose where practical, English drug/technical
names retained, per `CLAUDE.md`'s existing zh-TW convention. RCT/observational/meta-analysis/
guideline-consensus/mechanistic evidence kept distinct; causal language only where the evidence
supports it (the Wave 2 Challenge Round's four findings are the primary discipline check here).

**Sequence**: specialist reports → Director integration into `40_SYNTHESIS/` → Director-run Wave 3
Challenge Round → Gate 3 internal-consistency check → if passed, Wave 4 independent audit
(sonnet, read-only except `99_FINAL-QA.md`) → issues routed back to owning role, audit rerun.
Manuscript/slide work stays out of scope regardless of Gate 3/4 outcome, absent new PI authorization.

## Wave 3 — specialist reports processed, Synthesis complete, Gate 3 PASSED

All three specialists reported (Decisions 2026-08-31-29/30/31): Singh 2024 confirmed still
genuinely `BLOCKED_FOR_SOURCE` (not abandoned); T-025 upgraded to full text with a mandatory
subgroup-vs-overall caveat; T-026/T-027 (BCRP/CKD mechanistic proxies) added; T-023 upgraded to full
text with rich subgroup/GEE data; T-024 confirmed `BLOCKED_FOR_SOURCE` after 3 lawful attempts;
T-028 (Jeong 2022, Korea) found — Level 1 now has 3-country cross-national replication; citation
#29 and T-008 (Taiwan Health Promotion annual report) both content-verified, T-008 exact-matching
`Tonvasca_2026.md`'s own closing-slide figures.

**Director integration into `40_SYNTHESIS/` complete** — all nine required deliverables written
(`00_executive-synthesis.md` through `08_traceability-table.md`), Traditional Chinese prose with
English drug/technical names retained. **Wave 3 Challenge Round run** against the freshly-drafted
synthesis (`30_METHODS/shared/wave3-challenge-round-and-gate3.md`) — three self-caught issues
corrected in place (a #29/#35 target misattribution, an inconsistently-applied verification caveat
on ESC 2025's Lp(a) threshold, and a citation-vs-content verification-layer conflation on citation
#27's thresholds); all other checks passed, including a grep-verified absence of any forbidden
overclaim language anywhere in the synthesis.

**Gate 3: PASSED**, 2026-08-31.

## Wave 4 — first audit pass complete: HOLD_FOR_CORRECTION, corrected, re-audit requested

`pit-eze-independent-auditor` (sonnet, read-only except `99_FINAL-QA.md`) completed its first pass.
**Final Gate recommendation: `HOLD_FOR_CORRECTION`.** All eight named project traps checked out
clean (RACING, HIJ-PROPER subgroup, REPRIEVE/REAL-CAD-vs-FDC conflation — the project's own top
self-flagged risk — Taiwan STS mis-tiering, the dose-comparison overclaim, the Sydhom framing, the
#29/#35 and #28/#30 threshold conflations, the Katzmann cohort-n mix-up), no forbidden language, no
secrets, residual-risk content within charter bounds. **One material finding**: citation #28's LDL-C
and Lp(a) thresholds in `40_SYNTHESIS/02` and `06` lacked the "unverified against primary text"
caveat already correctly applied to structurally identical T-005/T-007 claims, and had no
`08_traceability-table.md` entry — a genuine Numeric Integrity Rule gap, though Director verification
confirmed the numbers themselves are not fabricated (they trace to `Tonvasca_2026.md` lines
1424–1481/1361 and `pitavastatin topic.md` line 149, just never properly anchored). **Corrected**
(Decision 2026-08-31-33): `02_SOURCE-INVENTORY.md` #28 row now cites exact legacy-source line
ranges; `40_SYNTHESIS/01/02/06/08` all updated with the caveat and new traceability rows.
Re-audit requested.

## Wave 4 — re-audit complete: FINAL GATE `PASS_WITH_MINOR_ISSUES`

`pit-eze-independent-auditor` independently re-verified the Finding 1 correction against the
underlying legacy sources itself (not just trusting the Director's fix), confirmed it accurate, and
found one trivial non-blocking tidiness item (a stale duplicate traceability-table row) — removed.
Decision 2026-08-31-34: **Final Gate `PASS_WITH_MINOR_ISSUES`**, one of the two statuses Runbook §36
permits marking `FINAL`. **`40_SYNTHESIS/00`–`08`, as committed, is marked `FINAL`.**
`50_MANUSCRIPT/` stays out of scope regardless.

## Current status: RUN COMPLETE through Wave 4

Wave 0 (orientation) → Wave 1 (source verification) → Wave 2 (full-text acquisition, Gate 2
`READY_WITH_PENDING_ITEMS`) → Wave 3 (synthesis, Gate 3 `PASSED`) → Wave 4 (independent audit, Final
Gate `PASS_WITH_MINOR_ISSUES`) are all complete for RUN_ID `2026-08-31-v1`. 28 new sources found and
verified/flagged beyond the ~35 original legacy citations; 34 decisions logged; every specialist's
work traceable through `90_CROSS-SESSION-LOG/`. Six sources remain deliberately `BLOCKED_FOR_SOURCE`/
`NEEDS_PI`, per standing PI instruction not to assume resolvable.

## Next action

None pending — all three specialists and the independent auditor are idle/complete. This run is at a
natural stopping point. Any further work (Wave 3 candidate T-024 if a future run reopens it, a
possible Wave 3 continuation, or `50_MANUSCRIPT/` drafting) requires new PI authorization.
