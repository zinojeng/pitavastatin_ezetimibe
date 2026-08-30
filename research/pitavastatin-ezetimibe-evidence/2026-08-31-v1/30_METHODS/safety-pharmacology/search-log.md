# search-log — safety-pharmacology-intelligence

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: safety-pharmacology-intelligence · Wave: 1（Source/Evidence Verification，含部分 Wave-2-shaped
new-source discovery，經 Director 2026-08-31 核准，見 `90_CROSS-SESSION-LOG/safety-pharmacology-log.md`）

本檔記錄「搜尋過程」本身（誰、用什麼工具、搜了什麼、找到/沒找到什麼），不含最終證據內容 —
證據內容見 `20_EVIDENCE/safety-pharmacology/evidence-map.md`。

---

## 執行方式

本角色使用 3 個內部 subagent（workflow-internal temporary labor，非 persistent peer）平行執行：

| Subagent | 任務範圍 | 對應 activity tag |
|---|---|---|
| `safety-citation-verify` | 驗證 `Tonvasca_2026.md` 中指派給本角色的 16 筆既有引用；補讀先前 Wave 0 未讀完的 lines 1795–2811 | LEGACY_VERIFICATION |
| `safety-glycemic-search` | Search Protocol item 3（glycemic/NODM，含「2024 systematic review」的具體定位） | NEW_SOURCE_DISCOVERY |
| `safety-ddi-dose-search` | Search Protocol item 4（DDI）+ item 5（2mg vs 4mg dose comparison，與 trials-efficacy 共同）+ STS vs 正式 statin intolerance 定義 | NEW_SOURCE_DISCOVERY |

## 工具可用性（重要 — 各 subagent session 不一致）

- 本 persistent session（safety-pharmacology-intelligence 本體）：`research_hub`、`llamaparse` 兩個
  MCP 皆可透過 ToolSearch 載入（與 Wave 0 manifest 記載的 ENOENT 失敗狀態不同）；`openevidence`
  持續 CONNECTION_CLOSED。已回報 Director 供其覆核並更新 `00_RUN-MANIFEST.md`/`04_OPEN-QUESTIONS.md`
  （本角色不擁有那兩個檔案的寫入權，僅回報）。
- `safety-citation-verify` subagent：`research_hub`/`paper-search` 皆未出現在其 deferred-tool
  index 中，改用 PubMed E-utilities（直接 API）、Crossref REST API、Europe PMC REST API —— 均為
  `CLAUDE.md` §10 明文允許的合法來源。未使用 Sci-Hub。
- `safety-glycemic-search` subagent：`paper-search`/`google-scholar`/`tavily` 皆未連上，改用直接
  PubMed（NCBI E-utilities）+ WebSearch。未使用 Sci-Hub。
- `safety-ddi-dose-search` subagent：`paper-search`/`research_hub`/`google-scholar` 皆未連上，改用
  WebSearch + WebFetch；PubMed/ScienceDirect 多數觸發 403/cookie-wall，DailyMed、Crossref API、
  PMC、J-Stage 可正常存取。未使用 Sci-Hub / `download_scihub`。

**結論**：MCP 連線狀態在不同 session（甚至同一角色下的不同 subagent session）之間並不一致 —
不可假設「本 session 測到可連」＝「全專案都可連」，反之亦然。凡本輪因連線問題改用替代合法來源
（PubMed 直接 API、Crossref、DailyMed、WebFetch）取得的資訊，信心層級標記為
`MODERATE`（多為 abstract/label-level 而非全文逐字核對），已個別在 `evidence-map.md` 標示；未達
`HIGH` 信心的項目建議在 `research_hub`/`paper-search` 確認可連後重新核對一次。

## 搜尋範圍與結果總覽

### A. Legacy citation verification（LEGACY_VERIFICATION）— 16 筆全數 VERIFIED_MATCH

對應 `02_SOURCE-INVENTORY.md` 表格編號 #3–16、#23、#26（#26 與 trials-efficacy 共同）。逐筆結果、
DOI/PMID、精確數字見 `evidence-map.md` 與 `10_DATA/safety-pharmacology/extraction-table.csv`。
兩項 internal-consistency flag（皆非本角色可修正範圍，已回報 Director）：
1. `Tonvasca_2026.md` line 2796 上標註 `13`，但內容對應 ref 12（Sydhom）而非 ref 13
   （Katzmann）— `FLAG = POSSIBLE_ERROR`, `ACTION = NEEDS_ANALYST`，未逕行更正。
2. Chou MT et al. 同一篇文獻在文件中以兩種格式引用（line 1958 用 in-press PII
   `S0149-2918(22)00286-7`；line 2803 用最終頁碼 `44(10):1272-1281`）— 經 Crossref 確認為同一篇
   （DOI 10.1016/j.clinthera.2022.08.006），非數字錯誤，僅為引用格式不一致。

### B. Tonvasca_2026.md 補讀（lines 1795–2811，回應 Decision 2026-08-31-02 的 NEEDS_ANALYST 項目）

已完整讀畢。該範圍多為表格/mermaid 圖/藥證與專利資訊，引用集中在結尾「總結」投影片
（lines 2765–2803），共識別 12 筆引用/角注。其中屬於本角色領域的新增候選：
- Corsini A, et al. Curr Med Res Opin. 2011;27(8):1551-1562.（DDI/CYP3A4，全文亦見於文件中未讀
  範圍外的 lines 2066、2236 — 本輪尚未獨立驗證，列入 `unresolved-questions.md`）
- Katzmann JL, et al. Clin Res Cardiol. 2022;111(3):243-252.（FDC adherence — 主要屬
  trials-efficacy 領域，但因涉及安全性/依從性交集，一併記錄）

其餘（Mach F/Huang PH/Chen PS/ADA/Masana L 屬 guideline-risk；Chou MT 屬 trials-efficacy；Meng LC
屬既有 guideline-risk 指派）已在 90_CROSS-SESSION-LOG 回報 Director 轉交對應角色，未由本角色處理。

### C. New-source discovery（NEW_SOURCE_DISCOVERY）

- **Glycemic/NODM（item 3）**：確認 `pitavastatin topic.md` 所稱「2024 systematic review/
  meta-analysis」為 **Singh H et al. 2024（PMID 39587804）**，並非 Sydhom P et al. 2024（兩者
  常被混淆，已個別列出、明確不予合併）。另找到 14 筆 head-to-head/cohort 證據（含台灣 PAPAGO-T、
  Chang Gung 回溯研究、CAPITAIN/PREVAIL-US 高劑量資料），2 篇僅有 protocol 無 result（CAMPUS、
  LESS-DM），"J-PREDICT" 試驗查無此名稱，列為待查。
- **DDI（item 4）**：以 LIVALO（pitavastatin calcium）FDA 藥品仿單（DailyMed）為主要來源，逐字擷取
  cyclosporine/erythromycin/rifampin/gemfibrozil/fenofibrate 交互作用數據；OATP1B1/BCRP 機轉、
  clarithromycin 特異性數據為缺口，列 `unresolved-questions.md`。
- **Dose comparison（item 5，與 trials-efficacy 共同）**：Chou MT 2022（1PC111，Taiwan/Australia/
  NZ）安全性表格本輪未能取得逐字數據（付費牆），僅一筆低信心、來源不明的 ADR 數字（8.6%/6.1%/
  7.0%）——**未列入 evidence-map，需 NEEDS_ANALYST 才可使用**。改以 K-924（Japan, Kowa）
  2mg/4mg±ezetimibe 12 週 RCT + 52 週延伸研究取得完整 AE/CK/liver/glucose 逐字數據，惟明確標示
  為不同產品/族群的 INDIRECT 佐證，非 Taiwan FDC 試驗本身。CKD/elderly 次族群安全性資料兩試驗
  均未報告 — 列為 BLOCKED_FOR_SOURCE 候選。
- **STS vs 正式 statin intolerance**：Taiwan STS 2026 共識（Wu YJ et al., J Formos Med Assoc,
  DOI 10.1016/j.jfma.2026.04.111）經 Crossref 確認存在且可取得完整作者/DOI，內文僅取得摘要層級
  （全文付費牆），信心層級 MODERATE。並列 2019 台灣脂肪與動脈硬化學會 statin intolerance 共識
  （Chien SC et al. 2019 — 本身也是本角色 16 筆既有引用之一 #15，經 citation-verify 確認即為
  2026 STS 共識之前身文件）、NLA 2022、EAS 2015 兩份國際正式定義作為對照基準。

## 未使用之工具

`llamaparse`（本 session 雖可連線，但本輪未取得任何需要全文 PDF 解析的檔案 — 所有來源皆為
abstract/label/摘要層級，無下載全文）；`scihub`/`download_scihub`（依 CLAUDE.md §10 全程禁止，
未曾呼叫）。

**追加限制（2026-08-31，Director 轉知，Decision 2026-08-31-08）**：guideline-risk-intelligence
發現 `mcp__research_hub__download_paper` 內部搜尋邏輯包含 Sci-Hub 且無法選擇退出。本角色即日起
**禁止呼叫此工具**；`research_hub` 的 metadata-only 工具（如 `search_papers`）不受影響仍可使用。
本輪（Wave 1）自始未曾呼叫 `download_paper`，亦未取得任何來源全文，無回溯處理需求。詳見
`fulltext-manifest.md`。

## Worktree isolation note

本 session 為 background job，寫入 shared checkout 時被 harness 攔下，要求先 EnterWorktree。本檔
與其餘本輪輸出實際寫入 `.claude/worktrees/safety-pharm-wave1/`（branch
`worktree-safety-pharm-wave1`），**尚未 commit、亦未 merge 回 main** — 依任務指示本角色不執行
git commit/push。此與 Director 回報的自身 worktree 同步問題（push 被權限分類器擋下）性質相同，
屬本次 run 的環境層級議題，已在 `90_CROSS-SESSION-LOG/safety-pharmacology-log.md` 與回報 Director
的訊息中一併說明，非本角色可獨力解決。
