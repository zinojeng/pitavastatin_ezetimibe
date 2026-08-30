# Claude Code Cross-session Research：完整建議、實作經驗與標準 Runbook

> 目的：把多次 Claude Code Cross-session Research 的實際經驗整理成一套可重複、可恢復、可稽核、可交接的研究工作系統。  
> 適用：臨床研究、systematic / evidence review、原始資料分析、manuscript 更新、演講 evidence synthesis，以及多角色長時間研究專案。

---

# 0. Executive Summary

下一次做 Cross-session Research，最重要的不是「開多少個 Claude sessions」，而是建立一個穩定的 **AI Research Operating System**。

核心原則：

> **Cross-session outside, Workflow inside.**

也就是：

- **Persistent session** = 長期存在的專業部門
- **Workflow / subagent** = 部門內暫時的執行人力
- **Cross-session message** = 控制與協調訊息
- **Repository** = 長期可靠的 source of truth
- **Research Director** = 唯一整合與決策入口
- **Independent Auditor** = 最後專門找錯的人

最推薦的研究流程：

```text
Human PI
   ↓
Research Director
   ↓
Persistent Specialist Sessions
   ↓
Workflow / Temporary Subagents
   ↓
Evidence / Data Verification
   ↓
Decision Gate
   ↓
Synthesis / Manuscript
   ↓
Independent Read-only Auditor
   ↓
Final Gate
```

最重要的七條：

1. 先寫 Research Charter，再開始研究。
2. Persistent session 與 temporary subagent 必須分開。
3. 每次重新開始都先做 cross-session health check。
4. 資料與證據先驗證，再開始 interpretation。
5. 研究以 Wave + Gate 方式推進，不要所有角色一起亂跑。
6. Durable knowledge 寫入 repo，不依賴 session conversation。
7. 最後一定安排 independent read-only auditor。

---

# 1. 為什麼要做 Cross-session Research

單一 Claude Code session 很適合：

- 一次性程式修改
- 短期資料分析
- 文稿修改
- 一個明確任務

但長時間研究容易遇到：

- context 越來越長
- 不同工作互相干擾
- 文獻、統計、資料、寫作混在一起
- agent 重複做相同工作
- 中途 session 結束後難以恢復
- 不知道哪個數字是最新版本
- 舊的分析被無意覆寫
- manuscript 與 source 不一致
- 不同研究 project 的 cross-session 訊息混在一起

因此 Cross-session Research 的真正價值不是「多幾個 AI」，而是：

> **把長期研究拆成具有獨立專業記憶、明確責任、可交接的研究部門。**

---

# 2. 核心架構：Persistent Sessions = Departments

建議的一般架構：

```text
Human PI
   │
   ▼
research-director
   │
   ├── data/results-intelligence
   ├── evidence/gap-intelligence
   ├── methods-statistics
   ├── guideline/clinical-safety
   └── manuscript-intelligence
```

但不是每個專案都必須全部建立。

## 2.1 不同研究類型的建議角色

### A. 原始資料研究

```text
research-director
results-data-intelligence
methods-statistics
evidence-intelligence
manuscript-intelligence
```

可再增加：

```text
independent-auditor
```

### B. Clinical Evidence Review

```text
research-director
guideline-intelligence
trials-evidence-intelligence
clinical-safety-intelligence
evidence-methods-intelligence
```

### C. Manuscript Revision

```text
research-director
results-provenance
methods-audit
evidence-citation
manuscript-intelligence
```

最後使用 temporary read-only auditor。

### D. Deep Research / Topic Discovery

```text
research-director
data-feasibility
gap-intelligence
methods-feasibility
domain-intelligence
```

---

# 3. Session 數量：少而強，比多而亂好

建議：

## Persistent Sessions

通常：

```text
4–6 個
```

已足夠。

Persistent session 適合：

- research-director
- data/results-intelligence
- gap/evidence-intelligence
- methods-statistics
- guideline/safety-intelligence
- manuscript-intelligence

## Temporary Subagents

可以很多，例如：

- PubMed scout
- RCT extractor
- full-text reviewer
- CKD data profiler
- medication reviewer
- missingness checker
- DAG reviewer
- power calculator
- table builder
- citation checker
- abstract consistency checker

但它們應該：

```text
spawn
↓
work
↓
report
↓
terminate
```

不要把每個小任務都做成 persistent session。

---

# 4. Golden Architecture

最推薦的心智模型：

```text
Persistent session
      ↓
   Workflow
      ↓
Temporary subagents
      ↓
  Local synthesis
      ↓
Cross-session summary
      ↓
Research Director
```

簡單說：

> Persistent session 維持長期專業知識。  
> Workflow 管理該部門內部的工作。  
> Subagent 負責暫時執行。  
> Cross-session message 只用來協調。  
> Repository 保存真正研究成果。

---

# 5. Research Director 的角色

Research Director 應該是：

> **Orchestrator，不是萬能執行者。**

負責：

- 接收 Human PI 指令
- 定義 project scope
- 建立 Research Charter
- 決定研究角色
- 進行 health check
- dispatch work
- 收集 specialist 結果
- 處理 disagreement
- 控制 research gates
- 決定是否進入下一 wave
- 整合結果
- 管理 decision log
- 最終 synthesis

不應：

- 自己取代所有 specialist
- peer 不可用時偷偷建立同名 subagent
- 在 source 未確認時直接寫 final conclusion
- 為了完成任務而猜測缺少的數字

---

# 6. 最重要的實際教訓：Cross-session 不會自動發生

曾經最容易誤判的情況：

```text
research-director
   ↓
workflow
   ├── data subagent
   ├── literature subagent
   └── statistics subagent
```

表面上看起來：

- Data 做了
- Literature 做了
- Statistics 做了

但事實上：

```text
data-intelligence
gap-intelligence
methods-statistics
```

三個真正 persistent peer 根本沒有被使用。

因此：

> **Workflow ≠ Cross-session**

真正的 Cross-session 必須看到：

```text
ListAgents
↓
existing persistent peer
↓
SendMessage
↓
peer receives request
↓
peer executes own workflow
↓
peer reports back
```

---

# 7. Persistent Specialist Rule

Research Director 必須永久遵守：

```text
The following names refer to existing independent persistent peers.

When work belongs to one of these domains:

1. Use ListAgents.
2. Locate the existing peer.
3. Use SendMessage.
4. Allow the peer to use its own workflow/subagents internally.

Do NOT silently create a local substitute agent with the same role.

If a required peer is unreachable:
STOP that branch and report the issue.
```

這條規則非常重要。

因為如果 Director 建立 local substitute：

- specialist 長期 context 消失
- cross-session 架構失去意義
- output provenance 變差
- 無法知道到底哪個角色做了研究

---

# 8. 每次研究開始前：Phase 0 Research Charter

不要一開始就搜尋。

先由 Director 建立：

```text
01_RESEARCH-CHARTER.md
```

內容至少包括：

```text
PROJECT_ID
RUN_ID
研究問題
PICO / PECO
主要目的
Secondary questions
目標產物
已有資料
Source of truth
不能修改的 legacy files
主要 uncertainty
角色分工
停止條件
成功條件
```

範例：

```markdown
# Research Charter

PROJECT_ID: inpatient-severe-hyperglycemia
RUN_ID: 2026-08-31-v1

## Primary Question

Adult hospitalized non-ICU patients with persistent glucose
300–500 mg/dL without initial DKA/HHS:

Does temporary IV insulin provide benefit over optimized
scheduled SC insulin?

## Final Outputs

- evidence map
- guideline comparison
- clinical synthesis
- unresolved evidence gaps
- presentation-ready conclusions

## Source of Truth

- guideline PDFs
- trial full texts
- extracted evidence tables
- repository synthesis files
```

---

# 9. 每次 Run 建立固定檔案

建議每次研究建立：

```text
research/<PROJECT_ID>/<RUN_ID>/

00_RUN-MANIFEST.md
01_RESEARCH-CHARTER.md
02_SOURCE-INVENTORY.md
03_DECISION-LOG.md
04_OPEN-QUESTIONS.md
05_STATUS.md

10_DATA/
20_EVIDENCE/
30_METHODS/
40_SYNTHESIS/
50_MANUSCRIPT/
90_CROSS-SESSION-LOG/
99_FINAL-QA.md
```

---

# 10. RUN_MANIFEST：整個研究的身份證

`00_RUN-MANIFEST.md` 建議記錄：

```text
PROJECT_ID
RUN_ID
Date
Git branch
Git commit
Working tree status
Persistent session names
Input files
Source checksums
Previous run
Output folders
File ownership
Current research gate
Unresolved blockers
```

如果有重要 source files，建議加入：

```text
filename
size
modified time
SHA-256
source role
```

這對 manuscript revision 特別重要。

---

# 11. Source Inventory

`02_SOURCE-INVENTORY.md` 用來回答：

> 目前我們到底有哪些 source？

分類：

```text
PRIMARY DATA
NEW ANALYSIS
OLD ANALYSIS
GUIDELINES
RCTs
META-ANALYSES
SYSTEMATIC REVIEWS
OBSERVATIONAL STUDIES
LEGACY MANUSCRIPTS
SLIDES
TABLES
SUPPLEMENTARY FILES
```

每個 source 建議記：

```text
source_id
filename/title
date
version
source type
relevance
verified?
superseded?
notes
```

---

# 12. 每次重新登入：Cross-session Health Check

這一步應該變成 mandatory。

流程：

```text
cd <research-repo>
↓
open Research Director
↓
ListAgents
↓
confirm persistent peers
↓
PING each peer
↓
receive READY
↓
dispatch
```

成功標準：

```text
data-intelligence → READY
gap-intelligence → READY
methods-statistics → READY
```

---

# 13. 一個重要實際經驗：Session History ≠ Reachable Peer

曾經會看到：

```text
data-intelligence       Completed
gap-intelligence        Completed
methods-statistics      Completed
```

以前的 conversation 還存在。

但 Director：

```text
ListAgents
```

卻看不到。

這表示：

> 有歷史紀錄，不代表目前有可通訊 socket。

因此不能假設：

```text
old session exists
=
cross-session usable
```

---

# 14. Peer Recovery SOP

如果 peer 不 reachable：

## Step 1

回到 Claude Agents / session view。

## Step 2

找到原 persistent conversation。

## Step 3

喚醒，例如：

```text
Resume as the persistent data-intelligence peer.

Remain available for cross-session requests from research-director.

When a task arrives:

- use workflows/subagents internally when useful
- save durable results to the repository
- report concise results back to research-director
- do not create another research-director

This is a persistent specialist role.
```

## Step 4

回 Director：

```text
ListAgents
```

## Step 5

再次：

```text
CROSS_SESSION_TEST
```

## Step 6

收到 reply 後才正式 dispatch。

---

# 15. 建議的研究順序：Wave + Gate

不要：

```text
全部 agents
↓
同時研究
↓
同時修改
↓
Director 最後拼湊
```

推薦：

```text
Wave 0
Orientation

Wave 1
Source / Data Verification

Gate 1

Wave 2
Methods + Evidence

Gate 2

Wave 3
Integration / Manuscript

Gate 3

Wave 4
Independent Audit

Final Gate
```

---

# 16. Wave 0：Orientation

每個 specialist 開始前先讀：

```text
CLAUDE.md
00_RUN-MANIFEST.md
01_RESEARCH-CHARTER.md
02_SOURCE-INVENTORY.md
03_DECISION-LOG.md
04_OPEN-QUESTIONS.md
previous accepted outputs
```

不要一進 session 就開始 PubMed 搜尋。

---

# 17. Wave 1：建立「事實」

最重要的 research discipline：

```text
SOURCE / DATA
     ↓
EXTRACTION
     ↓
PROVENANCE
     ↓
VERIFICATION
     ↓
INTERPRETATION
```

不是：

```text
看到結果
↓
解釋
↓
找 citation 補
```

例如新的 analysis file：

results-intelligence 只做：

```text
source identity
exact extraction
old vs new comparison
provenance
conflict detection
missing values
```

此時：

- 不寫 Discussion
- 不下臨床結論
- 不改 manuscript

---

# 18. 數值處理的硬規則

對任何 numeric result：

> **Preserve every numeric token exactly.**

禁止：

- 自動改 p-value
- 自動補 CI
- 自動改 decimal
- 自動轉 unit
- 根據常識修正 source
- 覺得 typo 就直接改

若懷疑錯誤：

```text
SOURCE_VALUE = 原值
FLAG = POSSIBLE_ERROR
ACTION = NEEDS_ANALYST / NEEDS_PI
```

不要直接修。

---

# 19. Wave 2：Methods + Evidence 可以平行

當 facts verified 後：

```text
              VERIFIED FACTS
                   │
          ┌────────┴────────┐
          ▼                 ▼
      Methods            Evidence
       Review              Review
```

Methods 可研究：

- cohort definition
- estimand
- exposure
- outcome
- index date
- baseline window
- confounders
- mediators
- colliders
- reverse causality
- missing data
- regression model
- survival analysis
- repeated measures
- sensitivity analyses
- precision/power

Evidence 可研究：

- guideline
- RCT
- cohort
- meta-analysis
- systematic review
- similar registry
- competing publications
- research gap
- clinical context

---

# 20. 哪些事情不應該太早平行

不推薦：

```text
raw new analysis
   ├── Results
   ├── Methods
   ├── Evidence
   └── Manuscript
```

因為：

- data 還沒確認
- methods 可能分析錯 target
- manuscript 可能引用 stale numbers
- literature synthesis 可能回答錯問題

---

# 21. Gate System

每個 Wave 後要有明確 Gate。

推薦狀態：

```text
READY_FOR_NEXT_WAVE
READY_WITH_PENDING_ITEMS
BLOCKED_FOR_SOURCE
BLOCKED_FOR_ANALYST
BLOCKED_FOR_PI
BLOCKED_FOR_METHODS
BLOCKED_FOR_EVIDENCE
```

重要觀念：

> **BLOCKED 是正常研究結果，不是失敗。**

---

# 22. Decision Taxonomy

對每個 discrepancy 可使用：

```text
VERIFIED_AND_REPLACE
VERIFIED_NEW_SENSITIVITY
NO_CHANGE
RETIRE_OLD_VALUE
NEEDS_ANALYST
NEEDS_PI
INSUFFICIENT_EVIDENCE
SOURCE_CONFLICT
```

這樣可以避免：

```text
「我覺得新的比較合理，所以直接換掉」
```

---

# 23. Evidence Hierarchy 必須清楚標示

對臨床研究非常重要。

每個 conclusion 建議標：

```text
DIRECT EVIDENCE
INDIRECT EVIDENCE
GUIDELINE / CONSENSUS
OBSERVATIONAL EVIDENCE
MECHANISTIC SUPPORT
INSTITUTIONAL PRACTICE
EXPERT INTERPRETATION
INSUFFICIENT EVIDENCE
```

例如：

> 沒有 RCT 或 guideline 支持某個 cutpoint。

應寫：

```text
No direct evidence identified.
Current practice appears to reflect institutional practice
rather than a validated evidence-based threshold.
```

不要把：

```text
common practice
```

寫成：

```text
guideline recommendation
```

---

# 24. Cross-session Message = Control Plane

Cross-session message 不要塞完整研究成果。

建議格式：

```text
[PROJECT]
[RUN]
[FROM]
[TO]
[TYPE]
[QUESTION]
[FINDING]
[IMPACT]
[ACTION]
[OUTPUT_PATHS]
[CONFIDENCE]
[STATUS]
```

範例：

```text
[PROJECT]
inpatient-severe-hyperglycemia

[RUN]
2026-08-31-v1

[TYPE]
EVIDENCE_UPDATE

[FINDING]
No comparative trial identified supporting IV insulin
solely because glucose is 300–500 mg/dL without DKA/HHS.

[IMPACT]
Do not frame this glucose range alone as an evidence-based
indication for IV insulin.

[ACTION]
Methods/Safety teams should evaluate whether escalation
criteria should instead be clinical/physiologic.

[OUTPUT_PATHS]
20_EVIDENCE/trials-review.md

[CONFIDENCE]
HIGH

[STATUS]
READY_FOR_INTEGRATION
```

---

# 25. Repository = Knowledge Plane

真正完整內容放：

```text
repo
```

不是 message。

應放 repo 的包括：

- evidence tables
- exact extraction
- statistical outputs
- code
- literature notes
- full-text review
- methods decisions
- manuscript sections
- QA reports
- final synthesis

這樣即使 session 消失：

```text
new session
↓
read repo
↓
resume
```

不需要重建全部 context。

---

# 26. Project ID + Run ID：避免不同研究混在一起

每個 message、output 都應帶：

```text
PROJECT_ID
RUN_ID
```

例如：

```text
PROJECT_ID:
tirzepatide-clinical-evidence

RUN_ID:
2026-08-31-v2
```

比只用：

```text
gap-intelligence
methods-statistics
```

安全很多。

---

# 27. Session 命名建議

大型專案可使用：

```text
tirzepatide-research-director
tirzepatide-evidence-intelligence
tirzepatide-methods-intelligence
tirzepatide-clinical-intelligence
```

原始資料：

```text
zinc-research-director
zinc-results-intelligence
zinc-methods-statistics
zinc-evidence-intelligence
```

如果 specialist 跨 project 共用，message 必須強制：

```text
[PROJECT]
[RUN]
```

---

# 28. File Ownership Matrix

這是降低 cross-session 衝突最有效的方法之一。

範例：

| Role | Read | Write |
|---|---|---|
| Director | all | decision log, integration |
| Results | source data, old/new results | `10_DATA/` |
| Methods | verified results | `30_METHODS/` |
| Evidence | verified questions | `20_EVIDENCE/` |
| Manuscript | approved facts/methods/evidence | `50_MANUSCRIPT/` |
| Auditor | all | `99_FINAL-QA.md` only |

不要：

```text
所有 sessions 都直接改 manuscript.md
```

---

# 29. Additive Versioning

不要覆寫過去 accepted output。

推薦：

```text
analysis/
  2026-08-25/
  2026-08-31/

manuscript/
  2026-08-25/
  2026-08-31/
```

或：

```text
RUN_2026-08-31_v1
```

舊結果保留作：

- provenance
- comparison
- audit
- rollback

---

# 30. Challenge Round：專門問「哪裡可能錯」

第一次 specialist 回報後，不要直接 integration。

再做一輪：

```text
Why might this conclusion be wrong?
```

例如：

## Guideline Intelligence

```text
Which statements go beyond the actual wording
of the guideline?
```

## Trials Intelligence

```text
Which conclusions are being extrapolated beyond
the actual trial population?
```

## Safety Intelligence

```text
Which recommendation could create patient risk?
```

## Methods Intelligence

```text
Which claim confuses association with causation?
Which indirect evidence is being treated as direct evidence?
```

這個 adversarial review 的價值通常高於再多找十幾篇 paper。

---

# 31. Specialist 之間不要自由形成蜘蛛網

不推薦：

```text
temporary subagent
   ↓
直接 message 另一個 specialist
   ↓
再叫第三個 specialist
```

容易造成：

- ownership 不清
- Director 不知道發生什麼
- message explosion
- conflicting tasks

推薦：

```text
temporary subagent
   ↓
parent persistent session
   ↓
identify dependency
   ↓
Research Director / parent orchestrator
   ↓
SendMessage to needed specialist
```

原則：

> **Subagents identify dependencies.  
> Persistent sessions orchestrate cross-session work.**

---

# 32. Research Director 等待 specialist 回覆時

Director 不應重做 specialist 的工作。

推薦指令：

```text
Wait for the assigned persistent peers to return.

Do not duplicate their assigned work locally.

When a peer reports:

1. acknowledge
2. record output path
3. update status
4. identify conflicts
5. send follow-up only if needed

Run synthesis only after required gates are satisfied.
```

---

# 33. Manuscript 應該是下游，而不是 parallel starting point

正確：

```text
Results verified
↓
Methods reconciled
↓
Evidence reconciled
↓
Director Gate
↓
Manuscript
```

不要：

```text
Results + Methods + Evidence + Manuscript
全部同時開始
```

否則最容易出現：

- manuscript 使用舊數字
- abstract 與 table 不一致
- Discussion 解讀 superseded result
- citation 支持不到 claim

---

# 34. Independent Auditor：最後一定要有

Auditor 最好：

```text
READ ONLY
```

可以讀：

- all source
- analysis
- evidence
- methods
- manuscript
- decision log

只能寫：

```text
99_FINAL-QA.md
```

不能直接修改 manuscript。

---

# 35. Final QA Checklist

Auditor 至少檢查：

## Numbers

- N
- denominators
- percentages
- mean / SD
- median / IQR
- effect sizes
- OR / HR / RR
- CI
- p-values
- units
- decimal precision

## Methods

- model
- covariates
- index date
- follow-up
- missing data
- interaction
- subgroup
- sensitivity analyses

## Evidence

- citation supports exact claim?
- direct vs indirect evidence?
- guideline wording exact?
- population comparable?
- current evidence?
- superseded study?

## Writing

- Abstract ↔ Results
- Results ↔ Tables
- Results ↔ Discussion
- Discussion ↔ Conclusion
- no stale values
- no unsupported causal language
- no unresolved placeholders

## Provenance

- every important number traceable?
- source version known?
- old values retired appropriately?
- no silent corrections?

---

# 36. Final Gate

最後狀態可定義：

```text
PASS
PASS_WITH_MINOR_ISSUES
HOLD_FOR_CORRECTION
BLOCKED_FOR_SOURCE
BLOCKED_FOR_PI
```

只有：

```text
PASS
PASS_WITH_MINOR_ISSUES
```

才可標示：

```text
FINAL
```

---

# 37. 研究工作推薦的八階段

最簡單記法：

```text
0 DEFINE
1 ORIENT
2 CONNECT
3 ACQUIRE
4 VERIFY
5 RECONCILE
6 SYNTHESIZE
7 AUDIT
```

## 0 DEFINE

- research question
- scope
- outputs
- team

## 1 ORIENT

- repo
- legacy work
- source inventory
- old decisions

## 2 CONNECT

- ListAgents
- health check
- peer recovery

## 3 ACQUIRE

- data
- guidelines
- literature
- full text

## 4 VERIFY

- provenance
- exact extraction
- data/method validity

## 5 RECONCILE

- conflicts
- old vs new
- methods vs evidence
- PI decisions

## 6 SYNTHESIZE

- final evidence synthesis
- manuscript
- clinical summary

## 7 AUDIT

- independent QA
- final gate

---

# 38. Research Workflow 的正確順序

若是 exploratory research：

```text
IDEA
 ↓
DATA FEASIBILITY
 ↓
RESEARCH GAP
 ↓
METHODS FEASIBILITY
 ↓
CANDIDATE QUESTIONS
 ↓
PI SELECT
 ↓
SAP
 ↓
ANALYSIS
 ↓
VALIDATION
 ↓
INTERPRETATION
 ↓
MANUSCRIPT
```

不要：

```text
先決定 hypothesis
↓
再逼 data / literature 支持它
```

---

# 39. Data Intelligence 的標準問題

Data specialist 的核心不是「跑統計」。

而是：

> 我們的資料真的能回答這個問題嗎？

應檢查：

- schema
- variables
- definitions
- missingness
- temporal coverage
- repeated measurements
- medications
- outcome frequency
- cohort size
- follow-up
- data quality
- longitudinal feasibility
- measurement frequency
- source consistency

---

# 40. Gap / Evidence Intelligence 的標準問題

核心：

> 就算資料做得到，這題現在還值得研究嗎？

應檢查：

- recent literature
- systematic reviews
- RCTs
- cohorts
- registries
- similar analyses
- competing papers
- research novelty
- unresolved controversy
- clinical relevance
- publication positioning

---

# 41. Methods-Statistics 的標準問題

核心：

> 研究設計是否真的站得住腳？

應定義：

- target population
- exposure
- comparator
- outcome
- index date
- baseline period
- follow-up
- estimand
- confounders
- mediators
- colliders
- reverse causality
- competing risk
- missing data
- statistical model
- sensitivity analyses
- multiplicity
- power / precision

---

# 42. Clinical / Safety Intelligence 的標準問題

臨床題目尤其重要：

- 哪些 evidence 可直接用？
- 哪些是 extrapolation？
- safety downside 是什麼？
- 哪些族群不適用？
- guideline recommendation 強度？
- institutional practice vs evidence？
- contraindications?
- monitoring?
- real-world implementation?

---

# 43. Manuscript Intelligence 的標準任務

Manuscript agent 不應重新研究全部。

只能使用：

```text
Director-approved facts
Director-approved methods
Director-approved evidence
```

負責：

- structure
- narrative
- consistency
- clarity
- journal style
- tables/figures description
- abstract
- discussion positioning

不能：

- 自己改數字
- 自己換 model
- 自己增加 unsupported claim

---

# 44. Decision Log 非常重要

每個重要改變寫：

```text
03_DECISION-LOG.md
```

範例：

```markdown
## Decision 2026-08-31-03

Issue:
Old manuscript used OR 1.42.

New analysis reports OR 1.31.

Decision:
VERIFIED_AND_REPLACE

Reason:
New analysis is the prespecified updated model.

Affected files:
- manuscript/results.md
- manuscript/abstract.md

Source:
10_DATA/new-analysis.md

Approved by:
Research Director
```

---

# 45. Open Questions

不要把 unresolved questions 放在 conversation 裡消失。

寫：

```text
04_OPEN-QUESTIONS.md
```

分類：

```text
NEEDS_SOURCE
NEEDS_ANALYST
NEEDS_METHODS
NEEDS_PI
```

例如：

```markdown
- [NEEDS_ANALYST] Formal interaction p-value unavailable.
- [NEEDS_SOURCE] Original trial protocol not yet obtained.
- [NEEDS_PI] Decide whether sensitivity analysis belongs in main manuscript.
```

---

# 46. Status File

可維護：

```text
05_STATUS.md
```

例如：

```markdown
Current Gate:
READY_WITH_PENDING_ITEMS

Wave:
2 - Methods + Evidence

Completed:
- Results extraction
- Source identity
- Old-vs-new reconciliation

Pending:
- Interaction p-value
- Full text of study X

Blocked:
None
```

這能讓任何新 session 30 秒內理解整個專案。

---

# 47. 對下一個 LLM 最重要的要求

如果你之後讓另一個 LLM 幫忙操作 Claude Code，不要只說：

```text
幫我建立 5 個 agents
```

應該要求它：

> 建立一個可恢復、可追蹤、可稽核的 Cross-session Research system。

---

# 48. 可直接交給下一個 LLM 的 Master Prompt

```text
Please design and implement a Claude Code Cross-session Research architecture
for this research project.

Do not merely create multiple agents.

Build a recoverable, auditable, staged research system.

CORE ARCHITECTURE

Human PI
→ persistent Research Director
→ persistent specialist peer sessions
→ each peer may use workflows / temporary subagents internally
→ Director integration
→ explicit decision gates
→ drafting / synthesis
→ independent read-only QA

MANDATORY PRINCIPLES

1. Cross-session outside, workflow inside.

2. Persistent specialist sessions and temporary subagents must remain distinct.

3. The Research Director must never silently create a local substitute for
   an existing but unreachable persistent peer.

4. Every resumed research run must start with a cross-session health check.

5. Every cross-session message must include:
   PROJECT_ID
   RUN_ID
   TYPE
   STATUS
   OUTPUT_PATHS

6. Cross-session communication is the control plane.
   Durable research outputs must be written to the repository.

7. The repository is the durable source of truth.
   Conversation history must never be the only research record.

8. Every run must create and maintain:
   - RUN_MANIFEST
   - RESEARCH_CHARTER
   - SOURCE_INVENTORY
   - DECISION_LOG
   - OPEN_QUESTIONS
   - STATUS
   - CROSS_SESSION_LOG

9. Source and data acquisition must precede interpretation.

10. Unverified data must not enter the manuscript or final synthesis.

11. Use staged research waves rather than allowing every agent to work
    simultaneously from the beginning.

12. Create explicit research gates between waves.

13. Valid statuses should include:
    READY_FOR_NEXT_WAVE
    READY_WITH_PENDING_ITEMS
    BLOCKED_FOR_SOURCE
    BLOCKED_FOR_ANALYST
    BLOCKED_FOR_PI

14. Never silently correct numbers, confidence intervals, units, p-values,
    effect sizes, or source text.

15. Define explicit file ownership for every persistent role.

16. Temporary subagents may identify cross-domain dependencies,
    but persistent parent sessions or the Research Director must orchestrate
    cross-session communication.

17. Run an adversarial challenge round before integration.

18. The final stage must include an independent read-only auditor.
    The auditor may not edit the manuscript.
    It may only generate a QA report and final gate recommendation.

19. Preserve old outputs.
    New work should be additive and versioned by date or RUN_ID.

20. Evidence must be classified as:
    DIRECT EVIDENCE
    INDIRECT EVIDENCE
    GUIDELINE / CONSENSUS
    OBSERVATIONAL EVIDENCE
    MECHANISTIC SUPPORT
    INSTITUTIONAL PRACTICE
    EXPERT INTERPRETATION
    INSUFFICIENT EVIDENCE

21. When evidence, data, or source information is missing or contradictory,
    BLOCK the relevant branch rather than guessing.

22. Optimize for:
    traceability
    recoverability
    non-duplication
    provenance
    scientific integrity
    reproducibility

FIRST:

Analyze the nature of this research project and decide which persistent
specialist sessions are truly necessary.

Do not mechanically reuse a fixed role list.

THEN PRODUCE:

1. recommended session topology
2. persistent session responsibilities
3. temporary workflow/subagent strategy
4. file ownership matrix
5. repository directory structure
6. initialization order
7. cross-session health-check procedure
8. peer recovery procedure
9. staged research waves
10. gate/status taxonomy
11. cross-session message schema
12. evidence hierarchy
13. discrepancy-resolution taxonomy
14. adversarial challenge plan
15. independent QA criteria
16. master prompt for each persistent session
17. orchestration prompt for Research Director
18. resume/recovery prompt for future sessions
19. minimal daily operating SOP
20. final checklist before declaring the research complete

The objective is not to maximize agent activity.

The objective is to build a reliable research system in which every important
claim, number, decision, and output can be traced and resumed.
```

---

# 49. Research Director Orchestration Prompt Template

```text
You are the persistent Research Director for this project.

Your primary responsibility is orchestration, state management,
scientific integrity, and integration.

You are NOT a substitute for the persistent specialist peers.

Before beginning work:

1. Read the Research Charter.
2. Read the Run Manifest.
3. Read the Source Inventory.
4. Read the Decision Log.
5. Read Open Questions and current Status.
6. Use ListAgents.
7. Confirm all required persistent peers are reachable.
8. Send a CROSS_SESSION_TEST to each required peer.
9. Do not dispatch real work until required peers respond.

Persistent specialist rule:

When work belongs to an existing persistent specialist:

- locate the peer with ListAgents
- use SendMessage
- allow the peer to execute its own workflow/subagents
- do not create a local substitute

If the peer is unreachable:
mark that branch BLOCKED and report it.

Research proceeds in Waves.

Wave 0:
Orientation.

Wave 1:
Source/data verification.

Gate 1:
No interpretation or manuscript drafting until facts are verified.

Wave 2:
Methods and evidence review.

Gate 2:
Resolve conflicts and missing requirements.

Wave 3:
Synthesis / manuscript.

Gate 3:
Check internal consistency.

Wave 4:
Independent read-only QA.

Final Gate:
Only mark FINAL after QA passes.

All durable findings must be saved to the repository.

Cross-session messages should remain concise and include:
PROJECT
RUN
TYPE
FINDING
IMPACT
ACTION
OUTPUT_PATHS
CONFIDENCE
STATUS

Maintain:
- DECISION_LOG
- OPEN_QUESTIONS
- STATUS
- CROSS_SESSION_LOG

Never guess missing numbers.
Never silently correct sources.
Never allow narrative convenience to override provenance.

Your goal is not to finish quickly.
Your goal is to produce a traceable and scientifically defensible result.
```

---

# 50. Persistent Specialist Prompt Template

```text
You are the persistent <ROLE_NAME> peer for:

PROJECT_ID: <PROJECT>
RUN_ID: <RUN>

You are a long-lived specialist department.

You are NOT a temporary subagent.

PRIMARY RESPONSIBILITY:
<ROLE RESPONSIBILITY>

At startup:

1. Read:
   - RUN_MANIFEST
   - RESEARCH_CHARTER
   - SOURCE_INVENTORY
   - relevant prior accepted outputs
   - current STATUS

2. Remain reachable for Research Director cross-session requests.

When assigned work:

1. Confirm exact scope.
2. Use workflows / temporary subagents internally if helpful.
3. Do not duplicate another persistent specialist's assignment.
4. Save complete durable outputs into your owned repository paths.
5. Preserve source provenance.
6. Do not silently correct source data.
7. Identify unresolved dependencies.
8. Return only a concise cross-session summary to Research Director.

Your cross-session reply must contain:

[PROJECT]
[RUN]
[TYPE]
[FINDING]
[IMPACT]
[ACTION]
[OUTPUT_PATHS]
[CONFIDENCE]
[STATUS]

If required evidence/data is missing:

do not guess.

Use:
BLOCKED_FOR_SOURCE
BLOCKED_FOR_ANALYST
BLOCKED_FOR_PI
as appropriate.

Do not create another Research Director.
Do not take ownership of files belonging to another persistent role.
```

---

# 51. Peer Resume Prompt

```text
Resume as the persistent <ROLE_NAME> peer.

PROJECT_ID: <PROJECT>

This is an existing long-lived specialist role.

Do not create a replacement role.

Read:

- latest RUN_MANIFEST
- RESEARCH_CHARTER
- STATUS
- DECISION_LOG
- OPEN_QUESTIONS
- your previous accepted outputs

Remain available for cross-session requests from Research Director.

When work arrives:

- use workflows/subagents internally when useful
- save durable outputs to the repository
- respect file ownership
- report concise findings back to Research Director

Reply READY when initialization is complete.
```

---

# 52. Minimal Daily / Resume SOP

每次重新開始：

```text
1. SSH / open Mac mini
2. cd research repo
3. check git status
4. open Research Director
5. read STATUS.md
6. ListAgents
7. identify unreachable peers
8. wake peers if required
9. CROSS_SESSION_TEST
10. confirm current Gate
11. dispatch only current Wave
12. save outputs
13. update Decision Log / Open Questions / Status
14. commit checkpoint when appropriate
```

---

# 53. 什麼時候應該開新 Session

應開 persistent session：

- 任務會跨數天/數週
- 專業 context 需要持續累積
- 會反覆被 Director 呼叫
- 有清楚且穩定的專業責任

例如：

```text
methods-statistics
evidence-intelligence
data-intelligence
```

---

# 54. 什麼時候不應開新 Persistent Session

不要因為：

- 找 5 篇 RCT
- 讀一個 PDF
- 做一個 subgroup table
- 檢查 references
- 跑一段 code
- 修改 abstract

就建立 persistent session。

這些是：

```text
workflow / subagent
```

---

# 55. 常見錯誤與改善方式

## Error 1：Director 自己做全部

### 問題

Cross-session 只是名義存在。

### 改善

```text
ListAgents → SendMessage → Peer workflow
```

---

## Error 2：Workflow 被誤認為 Cross-session

### 問題

`Agent finished` 不代表另一個 persistent session 做完。

### 改善

必須確認 peer identity 與 message routing。

---

## Error 3：Completed session 無法收 message

### 問題

history 還在，socket 已消失。

### 改善

wake old session → ListAgents → PING。

---

## Error 4：全部角色同時開工

### 問題

未驗證 source 就開始 interpretation/manuscript。

### 改善

Wave + Gate。

---

## Error 5：每個 session 都改同一份文件

### 問題

版本衝突、難以追蹤。

### 改善

file ownership。

---

## Error 6：完整成果留在 conversation

### 問題

session 一換就失去 durability。

### 改善

repo = source of truth。

---

## Error 7：不同 project 訊息混在一起

### 問題

不知道 finding 屬於哪個 project。

### 改善

所有訊息強制：

```text
PROJECT_ID
RUN_ID
```

---

## Error 8：Claude 為了完成工作自行補缺失資訊

### 問題

scientific hallucination。

### 改善

允許：

```text
NEEDS_SOURCE
NEEDS_ANALYST
NEEDS_PI
```

---

## Error 9：沒有 adversarial review

### 問題

所有 agents 都朝同一方向確認。

### 改善

Challenge Round：

```text
Why might this be wrong?
```

---

## Error 10：最後沒人專門找錯

### 問題

漂亮的 narrative 掩蓋 inconsistency。

### 改善

Independent read-only auditor。

---

# 56. 最終 Golden Rules

## Golden Rule 1

> Cross-session 不會自動發生。

必須真正：

```text
ListAgents → SendMessage
```

---

## Golden Rule 2

> Workflow 不等於 Cross-session。

Temporary subagent 不是 persistent peer。

---

## Golden Rule 3

> Session history 不等於 active peer。

真正可用要看 reachable socket。

---

## Golden Rule 4

> Persistent sessions are departments.

Workflow/subagents are temporary labor.

---

## Golden Rule 5

> Repository is the durable source of truth.

Conversation 只做互動與控制。

---

## Golden Rule 6

> Facts before interpretation.

Source verification 一定在 synthesis 前。

---

## Golden Rule 7

> Blocked is a valid research outcome.

沒有 evidence 就說沒有。

---

## Golden Rule 8

> Never silently repair research data.

疑似錯誤必須 flag，不得偷偷改。

---

## Golden Rule 9

> Every important research change needs provenance.

所有重要決策都應可回答：

```text
誰決定？
根據什麼？
何時決定？
取代哪個版本？
影響哪些檔案？
```

---

## Golden Rule 10

> Final writing is not the final quality step.

最後一步是 independent audit。

---

# 57. 最簡化的實務版

如果未來很忙，只記得下面流程即可：

```text
Research Charter
      ↓
Health Check
      ↓
Source Verification
      ↓
Methods + Evidence
      ↓
Decision Gate
      ↓
Synthesis
      ↓
Independent QA
```

與：

```text
Persistent Session = Department
Workflow = Internal Process
Subagent = Temporary Worker
Cross-session Message = Control Plane
Repository = Knowledge Plane
Research Director = Orchestrator
Auditor = Error Finder
```

---

# 58. 建議未來專案預設建立的共用 Runbook

可以把這份檔案放在：

```text
docs/CROSS-SESSION-RESEARCH-RUNBOOK.md
```

每個新 research repo 再建立：

```text
CLAUDE.md
research/<PROJECT_ID>/<RUN_ID>/
```

新的 Research Director 第一個 prompt 只需要：

```text
Read docs/CROSS-SESSION-RESEARCH-RUNBOOK.md first.

Then read the current project Research Charter and Run Manifest.

Do not begin substantive research until you have:
1. understood the project
2. confirmed the persistent session topology
3. completed the cross-session health check
4. identified the current research Wave and Gate
```

如此不同題目可以沿用相同 operating system，而不必每次重新教 Claude Code 如何合作。

---

# 59. 最後結論

理想的 Claude Code Cross-session Research 不應該看起來像：

```text
很多 Claude 同時工作
```

而應該像：

```text
一個有研究治理的團隊
```

也就是：

```text
Human PI
      ↓
Research Director
      ↓
Specialist Departments
      ↓
Verified Evidence / Data
      ↓
Explicit Decisions
      ↓
Versioned Repository
      ↓
Independent Audit
```

最值得持續優化的不是增加更多 agents，而是：

- state management
- provenance
- project isolation
- file ownership
- gating
- recovery
- adversarial review
- QA
- reproducibility

當這些做好後，Cross-session Research 才真正從「多 agent 實驗」變成可以長期使用的 **AI-assisted research infrastructure**。
