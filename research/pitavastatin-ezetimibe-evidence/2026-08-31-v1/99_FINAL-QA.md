# 99_FINAL-QA — pitavastatin-ezetimibe-evidence / 2026-08-31-v1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

**Owner: independent-auditor only.** This file is written exclusively by the read-only independent
auditor role in Wave 4 (`CLAUDE.md` §2.5, §14.4). No other role may write to this file. Until Wave 4
begins, this file is a skeleton only — do not populate findings prematurely.

## Status

Not yet started. Audit begins only after Gate 3 (Director internal-consistency check) passes —
see `05_STATUS.md` for current Wave/Gate.

## Final QA Checklist (to be executed in Wave 4, per Runbook §35 and CLAUDE.md §14.4)

### Numbers
- [ ] Every N, denominator, percentage traceable to source
- [ ] Every mean/SD, median/IQR traceable to source
- [ ] Every effect size (OR/HR/RR) with CI traceable to source
- [ ] Every p-value, unit, decimal precision traceable to source
- [ ] No numeric token silently altered from its source (Numeric Integrity Rule, CLAUDE.md §9)

### Methods / Evidence
- [ ] Every claim carries a correct Evidence Hierarchy tag (CLAUDE.md §7)
- [ ] RACING is never cited as pitavastatin-specific hard-outcome evidence
- [ ] HIJ-PROPER's absorber-phenotype subgroup is framed as hypothesis-generating, not confirmed
- [ ] Taiwan STS consensus is cited as GUIDELINE/CONSENSUS, not as outcome evidence
- [ ] Phase III FDC trial claims stay scoped to LDL-lowering efficacy (Level 1), not CV outcomes
- [ ] Population comparability caveats present wherever a cited trial used a different statin/agent

### Writing
- [ ] No "Pitavastatin does not cause diabetes" or equivalent overclaim anywhere
- [ ] No "Pitavastatin has no DDI" or equivalent overclaim anywhere — only "low CYP3A4-dependent
      interaction liability" framing
- [ ] Abstract/summary ↔ evidence tables ↔ synthesis internally consistent
- [ ] No unsupported causal language from observational/indirect evidence
- [ ] No unresolved placeholders
- [ ] Lp(a)/residual-risk content stays bounded (~10–15% of final output), per Research Charter

### Provenance
- [ ] Every important claim/number traceable to a specific file + source in `02_SOURCE-INVENTORY.md`
- [ ] No silent corrections anywhere in `10_DATA/`, `20_EVIDENCE/`, `40_SYNTHESIS/`
- [ ] All `03_DECISION-LOG.md` entries reflected consistently in downstream outputs
- [ ] MCP source policy respected — no Sci-Hub / unauthorized-access provenance anywhere

## Final Gate recommendation

*(to be set by independent-auditor in Wave 4)*

`PASS` | `PASS_WITH_MINOR_ISSUES` | `HOLD_FOR_CORRECTION` | `BLOCKED_FOR_SOURCE` | `BLOCKED_FOR_PI`
