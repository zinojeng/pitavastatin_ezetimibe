# fulltext-manifest — safety-pharmacology-intelligence

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

依 CLAUDE.md §11：全文 PDF/解析全文屬 local-only 工作素材，僅 committed metadata/擷取表/引用清單/
synthesis。本輪**未下載任何全文 PDF**，亦**未使用 llamaparse** — 所有本輪取得之資訊皆為
abstract/label/摘要層級，透過 PubMed metadata、Crossref metadata、DailyMed 官方仿單網頁內文、或
WebSearch 摘要片段取得，故 gitignored 的 `20_EVIDENCE/safety-pharmacology/fulltext/` 目錄目前為空
（已建立，供未來使用）。

## 已知曾嘗試但被 paywall/403 阻擋、未取得全文之來源

| 來源 | 嘗試方式 | 結果 | 後續建議 |
|---|---|---|---|
| Chou MT et al., Clin Ther 2022;44(10):1272-1281（1PC111 trial 安全性表格） | ScienceDirect 直接存取 | 403/付費牆 | 待 `research_hub` metadata-only 工具或機構訂閱管道；**禁止使用 `mcp__research_hub__download_paper`（見下方限制）** |
| Rai GS/Rozario CJ 2023, Anaesth Intensive Care Med | Elsevier 直接存取 | 付費牆 | 低優先（僅背景綜述，非本專案核心數字來源） |
| Taiwan STS 2026 consensus (Wu YJ et al., J Formos Med Assoc) | ScienceDirect 直接存取 | 403/付費牆 | 建議改試台灣脂肪與動脈硬化學會（TAS）官網是否有公開 PDF |
| NLA 2022 statin intolerance 定義原文 (lipidjournal.com) | 直接存取 | 403 | 次要，目前以二手摘要引用並標記 MODERATE 信心 |
| EAS 2015 Consensus Panel 原文 (Eur Heart J / atherosclerosis-journal.com) | 直接存取 | 未直接擷取 | 同上 |
| "Journal of Clinical Lipidology — A clinician's guide to statin drug-drug interactions" (2014) | 直接存取 | 403，僅搜尋片段 | 注意：此即 `02_SOURCE-INVENTORY.md` #6 Kellick KA 2014，已由 citation-verify subagent 透過 PubMed/Crossref metadata 獨立確認書目資訊，不受此全文缺口影響 |

## 重要限制更新（2026-08-31，Director 轉知，Decision 2026-08-31-08）

`mcp__research_hub__download_paper` 之內部搜尋邏輯已確認包含 Sci-Hub 且**無法選擇退出**（由
guideline-risk-intelligence 發現並回報）。**本角色即日起禁止呼叫此工具**，即使 `research_hub`
在本 session 可連線。`research_hub` 的 metadata-only 工具（如 `search_papers`）仍可使用。本輪
（Wave 1）**未曾呼叫**此受限工具，亦未取得任何來源全文，故無需回溯處理。往後全文取得改用：
paper-search 各資料庫專屬 download 工具、直接出版商/PMC/Unpaywall 開放取用連結，或對合法取得之
檔案使用 `llamaparse` 解析。

## Gitignored 目錄狀態

`20_EVIDENCE/safety-pharmacology/fulltext/` 已建立（空目錄，`.gitkeep` 待補），符合
`.gitignore` 的 `**/20_EVIDENCE/**/fulltext/` 規則，未來若取得合法全文將存放於此，不會進入
git 版本控制，除非個別檔案之授權經 `02_SOURCE-INVENTORY.md` 明確記錄
`verified: true, license: <name>, redistribution_ok: true`（由 Director 依 CLAUDE.md §11 登錄）。
