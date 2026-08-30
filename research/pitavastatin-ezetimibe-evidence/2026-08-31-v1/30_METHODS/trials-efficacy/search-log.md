# search-log — trials-efficacy-intelligence / Wave 1

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Role: trials-efficacy-intelligence · Wave: 1（Source / Evidence Verification）
Session: `pit-eze-trials-efficacy`

## Cross-session health check（Runbook §12–13）

1. `ListAgents` — 確認本 session 為 `pit-eze-trials-efficacy`；可見 peers：
   `pit-eze-safety-pharmacology`（busy）、`pit-eze-guideline-risk`（busy）、
   `pit-eze-research-director`（idle）。三個必要 peer（Director + 兩位同儕 specialist）
   均為可通訊 socket，非僅 session history。
2. 檢查 `90_CROSS-SESSION-LOG/` — 尚無既有紀錄，本 session 為第一個寫入者。
3. Wave 1 起點依 CLAUDE.md §10 重新確認 MCP 連線狀態（Wave 0 記錄 `research_hub` /
   `llamaparse` / `openevidence` 三者失敗）：
   - `research_hub`：**已恢復連線**（`search_papers`／`download_paper` 可正常呼叫，見下）。
   - `llamaparse`：連線已建立（`parse_pdf_to_markdown` 工具可用），本次 Wave 1 未產生需要
     LlamaParse 解析的已下載 PDF（見 `fulltext-manifest.md` 的下載失敗紀錄），故未實際呼叫。
   - `openevidence`：**仍為 CONNECTION_CLOSED**，本次 Wave 1 未使用（不可用，非本角色可修復
     的問題，已忠實記錄，未嘗試繞過）。
   - `paper-search`（PubMed/PMC/Crossref/Europe PMC/Unpaywall 等子工具）、`tavily`、
     `google-scholar`：正常可用，為本次 Wave 1 主要使用來源。
4. 依 CLAUDE.md §6 格式，向 Research Director 送出 CROSS_SESSION_TEST + STATUS_REPORT（見
   `90_CROSS-SESSION-LOG/`），確認本角色進入 Wave 1 Source/Evidence Verification。

## 檢索策略

Scope 依 CLAUDE.md §5（Prioritized Search Protocol）第 5、6、7、8、9 項（trials-efficacy 主責）
以及第 3 項（safety-pharmacology 主責、trials-efficacy 需交叉引用）。分兩軌：

- **軌道 A（Wave 1 — 驗證舊引用）**：針對 `02_SOURCE-INVENTORY.md` 中已標記
  `assigned owner = trials-efficacy` 的既有 `Tonvasca_2026.md` 引用（citation #19, #20, #21,
  #22, #25, #26, #33），逐條以 DOI/PubMed/Crossref 解析、比對期刊/年份/卷期頁碼/作者，並比對
  `Tonvasca_2026.md` 中已抄錄的數字（LDL-C % change、HR、95% CI、P value）。
- **軌道 B（Wave 1/2 — 補齊 `pitavastatin topic.md` 點名但尚未定位的來源）**：
  `02_SOURCE-INVENTORY.md` 中 T-001（HIJ-PROPER）、T-002（RACING）、T-004（2 mg vs 4 mg /
  add-ezetimibe vs dose-escalation）；T-003（NODM meta-analysis）與 safety-pharmacology 共管，
  僅做初步定位交叉引用，不做完整驗證（避免重複另一角色的工作，Runbook §31）。

## 使用的合法 MCP 來源（CLAUDE.md §10 允許清單內）

`mcp__paper-search__search_pubmed` / `search_crossref` / `get_crossref_paper_by_doi` /
`search_europepmc` / `search_pmc`；`mcp__research_hub__search_papers` /
`download_paper`；`mcp__tavily__tavily_search`。未使用、亦未嘗試使用 `scihub` 或
`download_scihub`（CLAUDE.md §10 明文禁止）。

## 檢索紀錄（依主題分組，非逐字 query log）

| # | 主題 / Search Protocol item | 查詢方向 | 結果摘要 | 對應 citation_id |
|---|---|---|---|---|
| 1 | Chou MT et al. Phase III FDC trial 定位與驗證（item 7） | `mcp__research_hub__search_papers` "Chou pitavastatin ezetimibe fixed dose combination Clin Ther 2022"；`mcp__paper-search__get_crossref_paper_by_doi` 驗證 DOI | 找到並以 Crossref 確認：標題、作者、期刊卷期頁碼與 `Tonvasca_2026.md` 引用字串完全相符 | TE-001 |
| 2 | 同一 Phase III 家族的**日本**獨立試驗，含 2 mg vs 4 mg 劑量比較（item 5） | `mcp__research_hub__search_papers` 同一查詢的相鄰結果；`mcp__paper-search__get_crossref_paper_by_doi`；`mcp__paper-search__search_pubmed` "Tsujita Yokote Ako pitavastatin ezetimibe fixed-dose combination Japan phase III" | 找到 Tsujita K et al. J Atheroscler Thromb 2023（K-924 4-arm RCT：pitavastatin 2mg / 4mg / 2mg+eze10mg / 4mg+eze10mg），**直接回答 Search Protocol item 5** | TE-002 |
| 3 | K-924 長期（52 週）延伸試驗 | 同上 PubMed 查詢的相鄰結果 | 找到 Ako J et al. J Atheroscler Thromb 2024（open-label extension） | TE-003 |
| 4 | HIJ-PROPER 主要發表與數字核對（item 6, 9） | `mcp__paper-search__search_pubmed` "HIJ-PROPER pitavastatin ezetimibe acute coronary syndrome" | 找到 rationale/design 論文（Kawada-Watanabe 2017）與**主要結果論文**（Hagiwara N et al. Eur Heart J 2017）；主要結果論文 abstract 中之數字與 `pitavastatin topic.md`／`Tonvasca_2026.md` 完全一致 | TE-004 |
| 5 | HIJ-PROPER 相關 substudy（非本次驗證重點，僅記錄存在） | 同上查詢的相鄰結果 | 另有 4 篇 substudy（單/多血管病灶、EPA/AA、心衰竭、sitosterol 表型延伸）被檢出，未逐一驗證，列入 `unresolved-questions.md` 供 Wave 2 判斷是否需要 | — |
| 6 | RACING 主要試驗與數字核對（item 8） | `mcp__paper-search__search_pubmed` "RACING trial rosuvastatin ezetimibe moderate-intensity vs high-intensity statin"；後以 "RACING trial Lee rosuvastatin ezetimibe statin monotherapy Lancet 2022 randomized" 精確定位主文 | 找到主要結果論文（Kim BK et al. Lancet 2022）；abstract 數字與 `pitavastatin topic.md` 完全一致 | TE-005 |
| 7 | RACING DM 次族群（item 8） | `mcp__paper-search__search_pubmed`（未命中，PubMed 索引詞不符）→ `mcp__paper-search__search_europepmc` → `mcp__tavily__tavily_search` "RACING trial diabetes subgroup analysis rosuvastatin ezetimibe MACE 10.0% 11.3%" | 找到 Lee YJ et al. Eur Heart J 2023;44(11):972-983（pre-specified DM subgroup, n=1398）；數字與 `pitavastatin topic.md` 完全一致（見 extraction-table） | TE-006 |
| 8 | Sydhom et al. 統合分析定位與驗證（item 8, 交叉 safety-pharmacology） | `mcp__paper-search__search_pubmed` "Sydhom meta-analysis low moderate intensity statin ezetimibe..."；`mcp__paper-search__get_crossref_paper_by_doi` | 找到並確認：BMC Cardiovasc Disord 2024;24(1)，與 `Tonvasca_2026.md` 引用字串相符 | TE-007 |
| 9 | 2024 NODM meta-analysis（item 3，safety-pharmacology 主責，交叉核對） | `mcp__paper-search__search_pubmed` "pitavastatin new-onset diabetes systematic review meta-analysis atorvastatin rosuvastatin" | 找到 Singh H et al. 2024（`pitavastatin topic.md` 中泛稱的「2024 systematic review/meta-analysis」極可能即此篇），**已轉知 safety-pharmacology**（非本角色最終驗證責任） | （safety-pharmacology 主責） |
| 10 | Boekholdt 2014 JACC 驗證（item 9, citation #19） | `mcp__paper-search__search_pubmed` "Boekholdt very low levels atherogenic lipoproteins..." | 找到並以 PubMed 確認：標題/期刊/DOI 相符 | TE-008 |
| 11 | T-SPARCLE（Yeh et al.）驗證（citation #22） | `mcp__paper-search__search_pubmed` "T-SPARCLE Taiwan lipid registry Yeh PLoS One 2017" | 找到並確認：標題/期刊/DOI/年份相符 | TE-009 |
| 12 | CEPHEUS（citation #20）、DYSIS-II（citation #21）、Masana 2020（citation #25）驗證 | 多輪 `search_pubmed` / `search_crossref`（見下） | **未能定位與 `Tonvasca_2026.md` 引用字串逐字相符的原始文獻**；找到之相近文獻journal/vol/page 與引用字串不符，見 `unresolved-questions.md` | 未指派 TE-id，列為未驗證 |
| 13 | Chou 2022 全文取得嘗試 | `mcp__research_hub__download_paper`（DOI）| 下載失敗（13 個資料庫均未收錄可下載全文；Elsevier 全文付費牆）；未嘗試 Sci-Hub | — |
| 14 | `Tonvasca_2026.md` 未讀完剩餘段落（04_OPEN-QUESTIONS 待辦） | `Read` 工具直接讀取 line 1680–2811（本 Wave 0 未讀完的剩餘 36%） | 補齊 Phase III FDC trial 之 AE 表格（見 extraction-table）與 DDI/ADR 段落（歸 safety-pharmacology）；未發現額外未登記之 trials-efficacy 引用 | — |

## 未執行 / 刻意跳過的檢索

- 未使用 `scihub` MCP 工具或 `paper-search` 的 `download_scihub`（CLAUDE.md §10 明文禁止，無例外）。
- 未重複搜尋已由 `02_SOURCE-INVENTORY.md` 標記為 guideline-risk 或 safety-pharmacology 主責的
  citation（Runbook §31：避免 specialist 之間職責重疊／蜘蛛網式互相接管）。
- Taiwan STS 2026 consensus（T-005）、Taiwan Lp(a) consensus（T-006）、ESC 2025 Focused Update
  （T-007）為 guideline-risk 主責項目，本角色未主動搜尋；若後續 synthesis 需要 trials-efficacy
  角度交叉引用，將於收到 guideline-risk 的 EVIDENCE_UPDATE 後處理。
