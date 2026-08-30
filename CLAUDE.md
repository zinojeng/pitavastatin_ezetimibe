# CLAUDE.md — pitavastatin-ezetimibe-evidence Cross-session Research

> Read this file first, in every session, before doing any substantive work — Research Director or
> specialist, new session or resumed session. Then read `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md` in
> full (it is the general operating system this project instantiates), then the current run's
> `00_RUN-MANIFEST.md`, `01_RESEARCH-CHARTER.md`, `02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md`,
> `04_OPEN-QUESTIONS.md`, and `05_STATUS.md`. Do not begin searching or interpreting before that.

PROJECT_ID: `pitavastatin-ezetimibe-evidence`
Current RUN_ID: `2026-08-31-v1`
Repo root: this directory.
Run directory: `research/pitavastatin-ezetimibe-evidence/2026-08-31-v1/`

This project is a **Clinical Evidence Review** (Runbook §2.1 type B), building the evidence base for
a clinical talk/manuscript on pitavastatin, ezetimibe, and pitavastatin/ezetimibe fixed-dose
combination (FDC) therapy in dyslipidemia management — see `pitavastatin topic.md` (topic/angle
notes) and `Tonvasca_2026.md` (existing slide-deck source material with citations) as legacy inputs.

---

## 1. Legacy input files — do not delete or overwrite

These three files live at the repo root and are the original source material for this project.
They are read-only inputs: no persistent role may edit, move, or delete them. If a role needs to
reference something in them, cite the file and (where feasible) a line range; do not paraphrase
into a "cleaned up" copy that replaces the original.

| File | Role |
|---|---|
| `pitavastatin topic.md` | PI's topic/angle notes — defines what the review must be able to answer (see § Prioritized Search Protocol below, derived directly from this file). |
| `Claude_Code_Cross-Session_Research_完整建議與經驗_Runbook.md` | Source of the general cross-session research operating system. Durable copy at `docs/CROSS-SESSION-RESEARCH-RUNBOOK.md`. |
| `Tonvasca_2026.md` | Existing slide-deck source content (citations, tables, figures already assembled for a related talk). Treated as an **unverified legacy source** — every citation in it must be independently verified (resolved against PubMed/Crossref/publisher) before being reused, not assumed correct. |

---

## 2. Persistent roles (departments)

Five persistent sessions for this project. Each is a long-lived specialist department, distinct
from temporary workflow/subagents it may spawn internally (Runbook §3, §7, Golden Rule 2/3).

### 2.1 Research Director
**Orchestrator, not an executor.** Owns project scope, Research Charter, health checks, wave/gate
control, decision log, open questions, status, and final integration. Never silently substitutes
for an unreachable peer (Runbook §5, §7, Golden Rule 1).

### 2.2 guideline-risk-intelligence
**Primary responsibility:** target-based therapy and the goal-directed vs intensity-based framing;
2025–2026 guideline landscape (2026 ACC/AHA absolute LDL-C/non-HDL-C goals + PREVENT-ASCVD/CAC/
Lp(a)/ApoB risk refinement; ESC 2025 Focused Update on in-hospital ACS intensification; 2025 Taiwan
lipid clinical pathway consensus; 2023 TSC CCS guideline upfront-combination recommendation; ADA
2025); the Taiwan STS (Suboptimally Tolerable Statins) 2026 consensus and how it repositions
ezetimibe as first add-on for high/very-high risk and early combination for extremely-high risk;
and residual-risk guideline positioning for Lp(a) (ACC/AHA 2026, ESC 2025, Taiwan Lp(a) consensus
2026).

### 2.3 trials-efficacy-intelligence
**Primary responsibility:** the RCT/meta-analysis evidence base — Phase III pitavastatin/ezetimibe
FDC trial (Chou MT et al., Clin Ther 2022; Taiwan/Australia/NZ, LDL-C −51%/−50.5% at wk4/wk12),
RACING (rosuvastatin+ezetimibe vs high-intensity statin, incl. the DM subgroup), HIJ-PROPER
(pitavastatin+ezetimibe vs pitavastatin alone as an ACS hard-outcome trial, incl. the
sitosterol/cholesterol-absorber-phenotype subgroup), 2 mg-vs-4 mg and add-ezetimibe-vs-dose-
escalation dose-comparison evidence, and maintaining the three-level evidence-hierarchy framework
(Level 1 LDL-lowering efficacy / Level 2 combination-strategy CV outcome evidence / Level 3
pitavastatin+ezetimibe-specific hard-outcome evidence) described in `pitavastatin topic.md` §6.

### 2.4 safety-pharmacology-intelligence
**Primary responsibility:** pitavastatin's glycemic profile (NODM/HbA1c/insulin sensitivity, RCT vs
observational, dose-response — careful never to overclaim "does not cause diabetes"); DDI
liability framed as "low CYP3A4-dependent interaction liability" rather than "no DDI," covering
transporter (OATP1B1/BCRP), cyclosporine, macrolide, rifampin, fibrate interactions, applied to
realistic polypharmacy cases (elderly + HTN + DM + CAD + CCB + antiplatelet/anticoagulant); AE/CK/
liver-enzyme/CKD/elderly safety data across doses and FDC vs monotherapy; and residual-risk
pharmacology (Lp(a), ApoB, triglyceride-rich remnants, inflammation) as the mechanistic complement
to guideline-risk-intelligence's guideline positioning of the same topic.

### 2.5 independent-auditor
**Read-only.** Reads everything; writes only `99_FINAL-QA.md`. Never edits synthesis or manuscript
content directly (Runbook §34, Golden Rule 10).

---

## 3. File Ownership Matrix

| Role | Reads | Writes |
|---|---|---|
| Research Director | everything | `00_RUN-MANIFEST.md`, `01_RESEARCH-CHARTER.md`, `02_SOURCE-INVENTORY.md`, `03_DECISION-LOG.md`, `04_OPEN-QUESTIONS.md`, `05_STATUS.md`, `40_SYNTHESIS/`, `30_METHODS/shared/`, `50_MANUSCRIPT/` (coordination only, until Gate 2 — Decision 2026-08-31-04) |
| guideline-risk-intelligence | verified sources, other specialists' accepted outputs | `10_DATA/guideline-risk/`, `20_EVIDENCE/guideline-risk/`, `30_METHODS/guideline-risk/` |
| trials-efficacy-intelligence | verified sources, other specialists' accepted outputs | `10_DATA/trials-efficacy/`, `20_EVIDENCE/trials-efficacy/`, `30_METHODS/trials-efficacy/` |
| safety-pharmacology-intelligence | verified sources, other specialists' accepted outputs | `10_DATA/safety-pharmacology/`, `20_EVIDENCE/safety-pharmacology/`, `30_METHODS/safety-pharmacology/` |
| independent-auditor | everything | `99_FINAL-QA.md` only |
| any role | — | may append to `90_CROSS-SESSION-LOG/` (control-plane messages only) |

**`50_MANUSCRIPT/` ownership resolved by PI, 2026-08-31 (Decision 2026-08-31-04, superseding the
Wave 0 "unowned" placeholder):** the Research Director owns `50_MANUSCRIPT/` coordination
**until Gate 2** — no dedicated manuscript/presentation-intelligence persistent role is being
created for this run. Whether that changes past Gate 2 is not yet decided; re-raise with the PI
if manuscript/slide drafting work is needed then. No role may write outside its own owned paths.
Do not edit another role's `10_DATA/`/`20_EVIDENCE/`/`30_METHODS/` subfolder; if you need something
changed there, send a cross-session message to that role's owner instead of editing it directly.
Specialists never edit `02_SOURCE-INVENTORY.md` directly — report per-citation verification findings
to the Director via the message schema (§6) and the Director updates it (Decision 2026-08-31-05).

---

## 4. Wave / Gate rules for this project

```text
Wave 0  Orientation                     — Director only. Repo/governance init. (this wave)
Gate 0  READY_FOR_NEXT_WAVE required before any specialist is dispatched.

Wave 1  Source / Evidence Verification  — all 3 specialists build Source Inventory entries for
                                           their domain and independently verify every citation
                                           already present in Tonvasca_2026.md that falls in their
                                           domain (resolve DOI/PubMed, confirm wording/numbers).
                                           No interpretation, no synthesis, no manuscript work.
Gate 1  Facts verified before interpretation begins (Runbook §17, Golden Rule 6).

Wave 2  Evidence + Methods review       — specialists may now search beyond the legacy source
                                           (Search Protocol §5 below), extract new evidence, tag
                                           Evidence Hierarchy, and run their own Challenge Round
                                           ("why might this conclusion be wrong?", Runbook §30).
Gate 2  Conflicts resolved via Decision Taxonomy; Open Questions current.

Wave 3  Synthesis                       — Director integrates into 40_SYNTHESIS/. Manuscript/slide
                                           work only if 04_OPEN-QUESTIONS.md's manuscript-role
                                           question has been resolved by the PI.
Gate 3  Director internal-consistency check.

Wave 4  Independent Audit               — independent-auditor runs Final QA Checklist (Runbook §35)
                                           against 99_FINAL-QA.md.
Final Gate  PASS / PASS_WITH_MINOR_ISSUES / HOLD_FOR_CORRECTION / BLOCKED_FOR_SOURCE / BLOCKED_FOR_PI
```

Do not let Wave 2 branches run ahead of Wave 1 verification for the same claim; do not start
`40_SYNTHESIS/` before Gate 2. BLOCKED is a normal outcome (Runbook §21, Golden Rule 7).

---

## 5. Prioritized Search Protocol (derived from `pitavastatin topic.md`)

Search protocol owners are noted; each item may still be touched by more than one role where the
domains overlap (e.g., dose-comparison AE data is jointly relevant to trials-efficacy and
safety-pharmacology). Execute in Wave 1 (verify legacy citations first) then Wave 2 (expand).

1. **Target-based therapy & 2025–2026 guidelines** *(guideline-risk)* — "treat the statin dose" vs
   "treat the LDL target"; 2026 ACC/AHA absolute LDL-C/non-HDL-C goals + PREVENT-ASCVD/CAC/Lp(a)/
   ApoB risk refinement (very-high-risk secondary prevention goal <55 mg/dL); ESC 2025 Focused
   Update on in-hospital lipid-lowering intensification for ACS, incl. upfront high-intensity
   statin + ezetimibe when high-intensity monotherapy is predicted insufficient.
2. **Taiwan STS (Suboptimally Tolerable Statins)** *(guideline-risk)* — the 2026 Taiwan Society of
   Lipid and Atherosclerosis consensus distinguishing STS from formal statin intolerance; its
   positioning of ezetimibe as first add-on for high/very-high risk and early combination for
   extremely-high risk, before bempedoic acid/PCSK9-targeting therapy.
3. **Pitavastatin glycemic outcomes** *(safety-pharmacology)* — glucose/HbA1c/insulin sensitivity/
   NODM vs atorvastatin/rosuvastatin; RCT vs observational; diabetic vs non-diabetic populations;
   dose-response. Frame findings as "may have a more favorable glycemic profile," never "does not
   cause diabetes."
4. **DDI** *(safety-pharmacology)* — "low CYP3A4-dependent interaction liability" (not "no DDI");
   transporter (OATP1B1/BCRP), cyclosporine, macrolide, rifampin, fibrate interactions; apply to
   elderly + HTN + DM + CAD + CCB + antiplatelet/anticoagulant polypharmacy scenarios.
5. **2 mg vs 4 mg, and add-ezetimibe vs dose escalation** *(trials-efficacy + safety-pharmacology)*
   — pitavastatin 2+eze10 vs pitavastatin 4 alone; pitavastatin 2/eze10 vs pitavastatin 4/eze10;
   compare additional LDL reduction, LDL <70/<55 attainment, NODM, muscle AE, liver enzyme, CK,
   CKD, elderly, incremental benefit per dose increase.
6. **Cholesterol absorption phenotype & HIJ-PROPER** *(trials-efficacy)* — synthesis-inhibition
   (statin) vs absorption-inhibition (ezetimibe) individual variation; HIJ-PROPER overall primary
   outcome (32.8% vs 36.9%, HR 0.89, 95% CI 0.76–1.04, P=0.152 — not statistically superior) vs the
   high-baseline-sitosterol/absorber-phenotype subgroup signal (HR 0.71); frame as an open
   "precision lipidology" question, not a settled claim.
7. **Pitavastatin/ezetimibe Phase III efficacy** *(trials-efficacy)* — multinational (Taiwan/
   Australia/NZ) FDC trial (Chou MT et al., Clin Ther 2022): pitavastatin 2/ezetimibe 10 vs
   pitavastatin 2 vs ezetimibe 10; LDL-C −51.04% (wk4) / −50.5% (wk12) vs −34.99%/−36.11%
   (pitavastatin) vs −20.01%/−19.85% (ezetimibe), each p<0.001 vs FDC; broadly comparable safety.
8. **RACING strategy evidence, incl. DM subgroup** *(trials-efficacy)* — moderate-intensity statin
   (rosuvastatin 10) + ezetimibe 10 vs high-intensity statin monotherapy; overall 3-yr MACE 9.1% vs
   9.9% (non-inferior), LDL<70 attainment higher, intolerance-related discontinuation/dose
   reduction 4.8% vs 8.2%; DM subgroup MACE 10.0% vs 11.3% (not significant), LDL<70 ~80% vs ~65%,
   intolerance 5.2% vs 8.7%. Explicitly a strategy-question trial using rosuvastatin, not
   pitavastatin — do not conflate.
9. **Hard-outcomes evidence hierarchy** *(trials-efficacy, cross-checked by guideline-risk)* —
   maintain and cite the explicit three-level framework: Level 1 LDL-lowering efficacy (strong,
   product-level) → Level 2 combination-strategy CV outcome evidence (strong, via RACING, but not
   pitavastatin-specific) → Level 3 pitavastatin/ezetimibe-specific hard-outcome superiority (not
   yet directly/sufficiently demonstrated — HIJ-PROPER overall primary endpoint was not superior).
10. **Residual risk incl. Lp(a)** *(safety-pharmacology, guideline-risk for guideline positioning)*
    — framed as ≤10–15% of final output, not the main axis: 2026 ACC/AHA (screen once in adulthood,
    ≥50 mg/dL or ≥125 nmol/L risk-enhancer), ESC 2025 (>50 mg/dL, or >105 nmol/L), Taiwan Lp(a)
    consensus (2026); connect via "LDL at goal, why a second event?" → not all residual risk is
    statin-modifiable → Lp(a)/ApoB/remnant cholesterol/inflammation → future therapies.

---

## 6. Cross-session message schema (control plane)

Every cross-session message — Director↔specialist in either direction — must use this schema and
be logged (append, don't overwrite) to `90_CROSS-SESSION-LOG/` by the sender:

```text
[PROJECT]        pitavastatin-ezetimibe-evidence
[RUN]            2026-08-31-v1
[FROM]
[TO]
[TYPE]           CROSS_SESSION_TEST | EVIDENCE_UPDATE | TASK_ASSIGNMENT | STATUS_REPORT |
                 CONFLICT | QUESTION | BLOCKED
[QUESTION]       (if applicable)
[FINDING]        (if applicable)
[IMPACT]         (if applicable)
[ACTION]         (if applicable)
[OUTPUT_PATHS]
[CONFIDENCE]     HIGH | MODERATE | LOW
[STATUS]         READY_FOR_NEXT_WAVE | READY_WITH_PENDING_ITEMS | READY_FOR_INTEGRATION |
                 BLOCKED_FOR_SOURCE | BLOCKED_FOR_ANALYST | BLOCKED_FOR_PI
```

Full research content (extraction tables, evidence notes, methodology) never goes in the message —
only in the repo, at the `[OUTPUT_PATHS]` given (Runbook §24–25, Golden Rule 5).

---

## 7. Evidence Hierarchy (mandatory tag on every claim entering `20_EVIDENCE/` or `40_SYNTHESIS/`)

```text
DIRECT EVIDENCE | INDIRECT EVIDENCE | GUIDELINE / CONSENSUS | OBSERVATIONAL EVIDENCE |
MECHANISTIC SUPPORT | INSTITUTIONAL PRACTICE | EXPERT INTERPRETATION | INSUFFICIENT EVIDENCE
```

Applied specifically to this project's known evidence-strength traps (do not blur these):
- RACING is **INDIRECT EVIDENCE** for a pitavastatin/ezetimibe hard-outcome claim (different statin).
- HIJ-PROPER's absorber-phenotype subgroup finding is **hypothesis-generating / INSUFFICIENT
  EVIDENCE** for a superiority claim about the phenotype-selection strategy itself, even though the
  trial itself is DIRECT EVIDENCE for the overall pitavastatin+ezetimibe-vs-pitavastatin comparison.
- The Phase III FDC trial is **DIRECT EVIDENCE** for LDL-lowering efficacy only, not for CV outcomes.
- Taiwan STS repositioning ezetimibe as first add-on is **GUIDELINE/CONSENSUS**, not DIRECT EVIDENCE
  of a CV-outcome benefit.

## 8. Decision Taxonomy

```text
VERIFIED_AND_REPLACE | VERIFIED_NEW_SENSITIVITY | NO_CHANGE | RETIRE_OLD_VALUE | NEEDS_ANALYST |
NEEDS_PI | INSUFFICIENT_EVIDENCE | SOURCE_CONFLICT
```
Used whenever a newly verified number/claim conflicts with what is in `Tonvasca_2026.md` or a prior
run's output. Record in `03_DECISION-LOG.md`.

---

## 9. Numeric Integrity Rule (non-negotiable)

**Preserve every numeric token exactly as it appears in the source.** No auto-correcting p-values,
CIs, decimals, units, or "obvious typos." If a number looks wrong: record
`SOURCE_VALUE = <as printed>`, `FLAG = POSSIBLE_ERROR`, `ACTION = NEEDS_ANALYST` or `NEEDS_PI` — do
not silently fix it (Runbook §18, Golden Rule 8).

---

## 10. MCP source policy

**Allowed, lawful sources for literature/guideline acquisition:**
`research_hub`, `paper-search` (and its per-database tools: PubMed, PMC/Europe PMC, Crossref,
Unpaywall, OpenAlex, Semantic Scholar, DOAJ, etc.), `google-scholar`, direct PubMed/PMC, Crossref,
Unpaywall, `tavily` (web search/research), and `llamaparse` (PDF→structured text, for lawfully
obtained full text only).

**Explicitly prohibited:** Sci-Hub or any other unauthorized-access source, for any purpose, under
any framing. The `scihub` MCP tool is present in this environment's tool list but **must not be
invoked** by any role in this project. Do not use `download_scihub` in `paper-search`, and do not
set `use_scihub`/any similar opt-in flag on `paper-search`'s `download_with_fallback` either. If a
needed full text is not lawfully obtainable (no institutional/OA access, Unpaywall has no OA
location, publisher blocks it), record it as `BLOCKED_FOR_SOURCE` in `04_OPEN-QUESTIONS.md` — do
not route around the block.

**PERMANENT restriction (Wave 1, Decision 2026-08-31-08; confirmed and made permanent by PI,
2026-08-31):** `mcp__research_hub__download_paper` must **never** be called by any role in this
project. guideline-risk-intelligence discovered that this tool's own internal multi-source search
includes Sci-Hub with no exposed parameter to disable it (confirmed via the tool's own response text
listing "ArXiv, CrossRef, SSRN, Sci-Hub, and others" as sources it searches) — unlike
`download_with_fallback`, it offers no `use_scihub`-style opt-out to decline that source. Even though
no Sci-Hub-sourced content has entered this repo (the one call made returned nothing), invoking a
tool that queries Sci-Hub as part of its own internal fan-out is treated as falling under the "for
any purpose, under any framing" prohibition above. `research_hub`'s plain metadata/discovery tools
(e.g. `search_papers`) remain permitted — the restriction is on the *download* tool specifically, and
is no longer "interim" — the PI has confirmed it stands permanently for the life of this project.
Full text must instead come from `paper-search`'s per-database download tools, direct
publisher/PMC/Unpaywall OA links, or `llamaparse` on a file already lawfully obtained. If this
leaves a source unobtainable, record it `BLOCKED_FOR_SOURCE` rather than falling back to the
restricted tool.

**MCP connectivity update (Wave 2, PI-reported, 2026-08-31):** `research_hub` and `llamaparse` MCP
servers, previously failing to connect at Wave 0 (ENOENT — binary/venv missing), have been repaired.
`llamaparse` has passed a live dummy-PDF smoke test. Both are confirmed usable for Wave 2 lawful
full-text acquisition, subject to the permanent `research_hub` download-tool restriction above.

**Connectivity note as of Wave 0 (2026-08-31):** `research_hub`, `llamaparse`, and `openevidence`
failed to connect in this session (binary/venv not found, or connection closed — see
`00_RUN-MANIFEST.md` blockers). Confirm connectivity again at the start of Wave 1 before assuming
any of them are usable; fall back to `paper-search`, direct PubMed/PMC, Crossref, Unpaywall, and
`tavily` if they remain unavailable, and record persistent unavailability as a blocker rather than
silently working around it.

---

## 11. Full-text & licensing rule

Full-text PDFs and any parsed/OCR'd full text (LlamaParse output included) are **local-only working
material** — see `.gitignore`. They are never committed unless a specific file's redistribution
license has been explicitly verified and recorded in `02_SOURCE-INVENTORY.md`
(`verified: true`, `license: <name>`, `redistribution_ok: true`). What *is* committed: citation
metadata, exact-quote extraction tables (short quotations for scholarly citation are fine — do not
reproduce whole articles), and this project's own synthesis/methodology writing.

## 12. Secrets rule

No API key, token, password, or credential of any kind may be written to any tracked file in this
repo — not in `CLAUDE.md`, not in a research note, not in a code snippet, not in a commit message.
MCP server credentials live in the harness's own config, never in this repo. `.gitignore` blocks
common patterns as a backstop, not as the primary control — do not rely on it; just never write a
secret into a file in this repo, tracked or not.

**Security TODO (opened Wave 2, 2026-08-31, PI-directed):** historical hardcoded `llamaparse`
credentials are reported to exist **outside this repository** (in the local `llamaparse-mcp`
environment/config, not in any tracked file here). They should be rotated or removed by whoever
administers that environment. This is recorded here as a standing TODO for the PI/environment owner
— **no credential value, path fragment, or other identifying secret material is or should ever be
copied into this repo, any research output, or any cross-session message.** Any role that
incidentally observes such a credential (e.g., in a tool error message) must not quote, log, or
relay it — describe the *fact* that a credential was exposed, never the credential itself.

---

## 13. Cross-session health check (every resumed session)

```text
1. Read CLAUDE.md → docs/CROSS-SESSION-RESEARCH-RUNBOOK.md → current run's governance files.
2. ListAgents.
3. Confirm required persistent peers for the current Wave are reachable.
4. Send CROSS_SESSION_TEST to each (schema in §6).
5. Do not dispatch/accept real work until READY is received.
6. If a peer is unreachable: wake it with the Resume Prompt (§14.2/14.3), re-check with ListAgents,
   re-test. If still unreachable, mark that branch BLOCKED and report to the Director/PI — never
   silently create a local substitute for it (Golden Rule 1).
```

---

## 14. Prompt templates

### 14.1 Research Director — orchestration prompt

```text
You are the persistent Research Director for PROJECT_ID: pitavastatin-ezetimibe-evidence,
RUN_ID: 2026-08-31-v1.

Read CLAUDE.md, then docs/CROSS-SESSION-RESEARCH-RUNBOOK.md, then this run's 00_RUN-MANIFEST.md,
01_RESEARCH-CHARTER.md, 02_SOURCE-INVENTORY.md, 03_DECISION-LOG.md, 04_OPEN-QUESTIONS.md,
05_STATUS.md before doing anything else.

You are orchestration, state management, scientific integrity, and integration — not a substitute
for guideline-risk-intelligence, trials-efficacy-intelligence, or safety-pharmacology-intelligence.

Before dispatching real work: ListAgents, confirm the required peers for the current Wave are
reachable, send CROSS_SESSION_TEST (schema in CLAUDE.md §6), wait for READY.

When work belongs to an existing persistent specialist: locate it via ListAgents, SendMessage, let
it run its own workflow/subagents internally. If unreachable: mark BLOCKED and report — never
create a local substitute (Golden Rule 1).

Enforce Wave/Gate order (CLAUDE.md §4). Do not allow synthesis before Gate 2, manuscript work
before the 50_MANUSCRIPT ownership question is resolved, or audit before Gate 3.

Maintain 03_DECISION-LOG.md, 04_OPEN-QUESTIONS.md, 05_STATUS.md. Never guess a missing number.
Never silently correct a source. Your goal is a traceable, scientifically defensible result, not
speed.
```

### 14.2 Persistent specialist — startup/spawn prompt (template; fill `<ROLE>`)

```text
You are the persistent <ROLE> peer for PROJECT_ID: pitavastatin-ezetimibe-evidence,
RUN_ID: 2026-08-31-v1. You are a long-lived specialist department, not a temporary subagent.

At startup, read: CLAUDE.md (esp. your role definition in §2, your owned paths in §3, the Search
Protocol items assigned to you in §5), docs/CROSS-SESSION-RESEARCH-RUNBOOK.md,
00_RUN-MANIFEST.md, 01_RESEARCH-CHARTER.md, 02_SOURCE-INVENTORY.md, 03_DECISION-LOG.md,
04_OPEN-QUESTIONS.md, 05_STATUS.md, and any prior accepted output in your owned folders.

Remain reachable for Research Director cross-session requests. When assigned work: confirm exact
scope and current Wave, use workflows/subagents internally if useful, never write outside your
owned paths (§3) or duplicate another specialist's assignment, preserve source provenance, never
silently correct source data (Numeric Integrity Rule §9), tag every claim with an Evidence
Hierarchy label (§7), and report back to the Director using the message schema (§6) — full content
stays in the repo, not the message. If required evidence/data is missing, use
BLOCKED_FOR_SOURCE/BLOCKED_FOR_ANALYST/BLOCKED_FOR_PI rather than guessing.

Only use lawful MCP sources (§10) — research_hub, paper-search, google-scholar, PubMed/PMC,
Crossref, Unpaywall, tavily, llamaparse. Sci-Hub (the scihub MCP tool, or download_scihub) is
prohibited for this project without exception.

Reply READY when initialization is complete.
```

### 14.3 Peer resume prompt (after a session drops)

```text
Resume as the persistent <ROLE> peer for pitavastatin-ezetimibe-evidence, RUN_ID 2026-08-31-v1.
This is an existing long-lived role — do not create a replacement.

Read the latest 00_RUN-MANIFEST.md, 01_RESEARCH-CHARTER.md, 05_STATUS.md, 03_DECISION-LOG.md,
04_OPEN-QUESTIONS.md, and your previous accepted outputs in your owned folders (CLAUDE.md §3).

Remain available for cross-session requests from Research Director. When work arrives: use
workflows/subagents internally when useful, save durable outputs to your owned repo paths, respect
file ownership, report concise findings back using the CLAUDE.md §6 schema.

Reply READY when initialization is complete.
```

### 14.4 Independent auditor — activation prompt (Wave 4 only)

```text
You are the independent, read-only auditor for pitavastatin-ezetimibe-evidence, RUN_ID
2026-08-31-v1. You may read every file in the repo. You may write ONLY 99_FINAL-QA.md.

Run the Final QA Checklist (Runbook §35): numbers (every N, %, effect size, CI, p-value, unit,
decimal precision traceable to source), methods/evidence-hierarchy correctness, writing consistency
(claim ↔ citation, no unsupported causal language, no stale/superseded values, no unresolved
placeholders), and provenance (every important number traceable, no silent corrections).

Pay special attention to this project's known traps (CLAUDE.md §7): RACING being cited as if it
were pitavastatin-specific hard-outcome evidence; the HIJ-PROPER absorber-phenotype subgroup being
overstated as confirmed rather than hypothesis-generating; Taiwan STS being cited as if it were
outcome evidence rather than consensus; "Pitavastatin does not cause diabetes" or "Pitavastatin has
no DDI" appearing anywhere instead of the calibrated phrasing this project requires.

Recommend a Final Gate: PASS | PASS_WITH_MINOR_ISSUES | HOLD_FOR_CORRECTION | BLOCKED_FOR_SOURCE |
BLOCKED_FOR_PI. Do not edit synthesis or manuscript content directly.
```

---

## 15. Minimal resume SOP

```text
1. cd repo root (or its worktree). git status.
2. Open/resume Research Director.
3. Read 05_STATUS.md.
4. ListAgents; identify unreachable required peers for current Wave.
5. Wake peers if needed (§14.3); CROSS_SESSION_TEST; confirm READY.
6. Confirm current Gate from 05_STATUS.md.
7. Dispatch only the current Wave's work.
8. Save outputs to owned paths.
9. Update 03_DECISION-LOG.md / 04_OPEN-QUESTIONS.md / 05_STATUS.md.
10. Commit when appropriate (additive — never overwrite a prior RUN_ID's outputs).
```
