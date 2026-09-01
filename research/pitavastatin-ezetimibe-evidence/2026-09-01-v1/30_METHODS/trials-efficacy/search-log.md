# search-log — trials-efficacy-intelligence / Wave 1 (RUN 2026-09-01-v1)

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Role: trials-efficacy-intelligence · Wave: 1（focus areas 2–3 per 01_RESEARCH-CHARTER.md）

本檔案為本 run 新增紀錄，前一 run（2026-08-31-v1）的完整搜尋歷程見該 run 自己的
`30_METHODS/trials-efficacy/search-log.md`，此處不重複。

## 環境狀態（health check，已回報 Director）

- `paper-search`、`tavily`、`openevidence` 三者於本 session 皆為 `ENOENT`（`uv`/`npx`/`node`
  executable 不在 $PATH）— 與 Director Wave 0 recon 結果一致。Director 於工作中途回報
  openevidence 已在其環境修復，但本角色重新 `ToolSearch` 後**仍為 ENOENT**（node 不在本 session
  $PATH）— 修復未傳播到本 session，已回報 Director，不強行視為可用。
- 可用：`research_hub`（metadata-only search，`download_paper` 永久禁用）、`google-scholar`
  （`search_google_scholar_key_words`、`search_google_scholar_advanced`）、`llamaparse`（本次
  Wave 1 未實際呼叫，因無新下載之全文 PDF）。
- 新增可用（非本專案原先允許清單，但屬本 harness 內建、非 MCP 工具）：`WebSearch`、`WebFetch`。
  使用時嚴格遵守 `CLAUDE.md` §9「Tool-confabulation caution」——僅信任明確回報成功/內容存在的
  結果；`WebFetch` 若回報 403/paywall/challenge 頁，一律照實記錄為取得失敗，不繼續引用其可能
  出現的任何數字。PMC（`pmc.ncbi.nlm.nih.gov`）頁面視為合法公開來源（NIH 公共典藏，非
  publisher 付費牆），可用 `WebFetch` 直接讀取；ScienceDirect／Nature 等 publisher landing page
  則預期為付費牆，`WebFetch` 若回傳純粹的 HTTP 錯誤（如 403）而非確信地引述內容，視為工具正確
  拒絕而非 confabulation，予以信任該「失敗」判斷本身。

## Focus area 2（direct FDC evidence 延伸 + RWE）檢索紀錄

| # | 查詢方向 | 工具 | 結果摘要 |
|---|---|---|---|
| 1 | pitavastatin+ezetimibe FDC real-world evidence／registry／claims database | `research_hub__search_papers`（多輪不同關鍵字組合） | **未發現**新的、專屬 pitavastatin+ezetimibe FDC 的 RWE，超出前一 run 已找到的 TE-013（Lu YW et al. Acta Cardiol Sin 2026, Taiwan post-PCI real-world cohort）。找到一篇**同類但非 pitavastatin**的 RWE 供對照（atorvastatin/ezetimibe FDC real-world goal attainment, ACC 2026 abstract, DOI 10.1016/j.jacc.2026.02.425）——顯示同類 FDC 藥物有更多 RWE 累積中，但 pitavastatin+ezetimibe 本身的 RWE 目前仍僅有 TE-013 一篇，此為 Q5 的初步答案（見下方 evidence-map.md） |
| 2 | pitavastatin 2mg/4mg 劑量比較、CKD/elderly 安全性新資料 | `research_hub__search_papers` | 未發現超出前一 run 已建立的 TE-002（Tsujita 2023）/TE-015（Jeong 2022）之外的新資料 |

## Focus area 3（Level 3 gap 再確認 + 新 substudy 發現）檢索紀錄

| # | 查詢方向 | 工具 | 結果摘要 |
|---|---|---|---|
| 3 | HIJ-PROPER 是否有更新的 follow-up 或新試驗關閉 Level 3 缺口 | `research_hub__search_papers` | **未發現**任何新試驗關閉此缺口，維持前一 run 的判斷不變 |
| 4 | HIJ-PROPER substudy 廣泛掃描 | `research_hub__search_papers`、`google-scholar` | 發現前一 run 未登記的**兩篇新 substudy**（見下方 TE-016、TE-017），皆直接對應本專案核心的 sitosterol/absorber-phenotype 與 baseline-LDL-C-stratified 次族群主題 |
| 5 | TE-016（Yamaguchi 2018 sitosterol substudy）內容核實 | `research_hub__search_papers`（身份驗證）+ `WebSearch`（摘要片段）+ `WebFetch`（ScienceDirect abstract page，回傳 403，未取得內容） | 身份 VERIFIED（DOI/期刊/年份經 Crossref 交叉核對）；**數字內容僅來自 WebSearch 聚合摘要，未經獨立全文核實**，信心度標記為 MODERATE，非 HIGH |
| 6 | TE-017（Sci Rep 2021 baseline-LDL-C substudy）內容核實 | `research_hub__search_papers`（身份驗證）+ `WebFetch`（PMC8021554，合法 open access 頁面，成功取得內容）+ `WebSearch`（獨立交叉比對） | 身份 VERIFIED；數字內容經 **兩個獨立管道**（WebFetch 直接讀取 PMC 頁面 + WebSearch 聚合摘要）交叉比對一致（N=686/743、cutoff 131 mg/dL 兩者相符）；HR/CI/p-value 僅見於 WebFetch 單一結果，未見第二來源交叉驗證，故 HR/CI 部分信心度標記為 MODERATE，N 與 cutoff 部分標記 HIGH。嘗試 `curl` 直接下載 PMC PDF 供 LlamaParse 解析以求最高確定性，遭遇與前一 run 相同的 PMC proof-of-work 反機器人 challenge（回傳 1817 bytes HTML challenge 頁，非真實 PDF）——未嘗試破解，維持現有信心度標記 |

## Attack/defense 章節（focus area 5，trial-side 貢獻）檢索紀錄

| # | 查詢方向 | 工具 | 結果摘要 |
|---|---|---|---|
| 7 | Bempedoic acid hard-outcome trial | `research_hub__search_papers` | CLEAR-Outcomes 主要發表確認：Nissen SE et al. NEJM 2023, DOI 10.1056/NEJMoa2215024 |
| 8 | PCSK9-targeting therapy hard-outcome trials | `research_hub__search_papers` | FOURIER（evolocumab, NEJM 2017, DOI 10.1056/NEJMoa1615664）與 ODYSSEY OUTCOMES（alirocumab, NEJM 2018, DOI 10.1056/NEJMoa1801174）主要發表確認 |
| 9 | Inclisiran hard-outcome trial 現況 | `research_hub__search_papers` | **重要發現**：檢索到的僅為 VICTORION-2 Prevent 與 ORION-4 的**試驗設計/protocol 論文**（分別為 Am Heart J 2026 DOI 10.1016/j.ahj.2026.107493、ISRCTN registry 2018），**未找到任何已完成、已發表的 inclisiran hard-outcome 結果論文**——與 bempedoic acid／PCSK9i 已有完整發表的正向 hard-outcome 試驗形成明顯對比，此為 attack/defense 論述的重要不對稱點（見 evidence-map.md） |

## 未執行 / 刻意跳過

- 未使用 `mcp__research_hub__download_paper`（永久禁用）。
- 未嘗試破解 PMC proof-of-work challenge 或任何反機器人機制（一貫政策延續）。
- 未將 `inbox/2026-acc-aha-drive/` 任一檔案視為已驗證來源使用——該資料夾為 guideline-risk-intelligence
  owned，本角色僅在 00_RUN-MANIFEST.md 閱讀範圍內知悉其存在，未直接讀取或引用其內容。
