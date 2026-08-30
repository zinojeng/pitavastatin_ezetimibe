# fulltext-manifest — safety-pharmacology-intelligence

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

依 CLAUDE.md §11：全文 PDF/解析全文屬 local-only 工作素材，僅 committed metadata/擷取表/引用清單/
synthesis。本輪**未下載任何全文 PDF**，亦**未使用 llamaparse** — 所有本輪取得之資訊皆為
abstract/label/摘要層級，透過 PubMed metadata、Crossref metadata、DailyMed 官方仿單網頁內文、或
WebSearch 摘要片段取得，故 gitignored 的 `20_EVIDENCE/safety-pharmacology/fulltext/` 目錄目前為空
（已建立，供未來使用）。

## Wave 2 — 合法取得之全文（新增）

| 檔案 | 來源 | URL | 授權 | 下載時間 (UTC) | SHA-256 | 解析狀態 |
|---|---|---|---|---|---|---|
| `fulltext/Katzmann2022_PMC8873069.pdf` | Europe PMC open access（Katzmann JL et al., Clin Res Cardiol 2022;111(3):243-252, DOI 10.1007/s00392-020-01740-8, PMID 32949286, PMCID PMC8873069） | https://europepmc.org/articles/PMC8873069?pdf=render | **CC BY 4.0**（逐字確認："This article is licensed under a Creative Commons Attribution 4.0 International License"） | 2026-08-30T21:00:36Z | `0e981a55ac9be188cbede2bce045ffd4847ffef0336cae350d0f502137e0a111` | 已用 LlamaParse 成功解析，輸出 `fulltext/Katzmann2022_PMC8873069.md`（21 頁 PDF） |
| `fulltext/Tramontano2025_PMC12098426.pdf` | Europe PMC open access（Tramontano D et al., "Renal Safety Assessment of Lipid-Lowering Drugs: Between Old Certainties and New Questions." Drugs. 2025, PMID 40106181, PMCID PMC12098426） | https://europepmc.org/articles/PMC12098426?pdf=render | **CC BY-NC 4.0**（逐字確認："Creative Commons Attribution-NonCommercial 4.0 International License"；非商業性學術研究使用符合此授權） | 2026-08-30T21:06:59Z | `f8bb6f623bd1025893f15719b11c1e78cdc42c60f5ceb206b770c94eeeb6c7e9` | 已用 LlamaParse 解析（輸出過大超過單次工具回傳上限，改以 grep 針對性擷取），輸出
`fulltext/Tramontano2025_PMC12098426.md`（21 頁 PDF）；**內含 Table 1「Statin metabolism and
recommended doses in adults with CKD」，解決本角色 Wave 1 標記之 pitavastatin CKD 劑量缺口的
重要部分**，並已交叉比對 FDA LIVALO label 官方原文確認一致，詳見 `ddi-matrix.md` |

**Director 委託查證（2026-08-31，Decision 2026-08-31-11 numeric-integrity flag 的後續）**：
`Tonvasca_2026.md` 引用此篇時出現兩組不同 n 值（6,429/533 vs 1,639/796），經直接查閱本篇全文
（`fulltext/Katzmann2022_PMC8873069.md`），**兩組數字皆為本篇論文內真實存在、逐字可查的數字，
非任一組是錯誤**——只是量測對象不同，非同一分析：
- **n=6,429 (FDC) / n=533 (SPC)**：來自 **Table 1「Baseline characteristics for patients treated
  by general practitioners in 2018」**（僅 GP 執業別、2018 單一年度之處方盛行率計數，GP 全體
  n=136,494 中的子分類）。（對照：Table 2 為 cardiologist 執業別之對應數字，FDC n=682, SPC n=51，
  Tonvasca 兩組數字皆非此表。）
- **n=1,639 (FDC) / n=796 (SPC)**：來自論文 **Graphic Abstract 及 Figure 6**，是「LDL-C reduction
  after ezetimibe initiation」分析所用之**合併（GP+cardiologist）、具完整用藥前後 LDL-C 配對數據
  之子族群**——這正是論文標題性結論（FDC −28.4%/−40.0mg/dL vs SPC −19.4%/−27.5mg/dL, p<0.0001）
  所依據的樣本數。
- **結論給 Director/trials-efficacy 判斷**：若 `Tonvasca_2026.md` 該處所引用的主張是
  「LDL-C 降幅 FDC 優於 SPC」這個具體療效比較，正確對應樣本數應為 **n=1,639 (FDC) / n=796
  (SPC)**；若該處主張的是「處方盛行率」（例如「多數病人使用 FDC」），則 6,429/533（僅 GP、
  僅 2018 年）才是正確對應數字，但須註明其為 GP-only 子集，不可直接當作全體研究人口
  （n=311,242）的處方分布。本角色僅完成原始數字之逐字查證與定位，**決定 Tonvasca 該處具體
  主張應對應哪一組數字**、以及如何更新 `03_DECISION-LOG.md`/Tonvasca 引用建議，留給
  trials-efficacy-intelligence 與 Director（此為該角色 T-012 owned citation）。

**授權建議（供 Director 登錄 `02_SOURCE-INVENTORY.md`）**：因授權為 CC BY 4.0，`verified: true,
license: "CC BY 4.0", redistribution_ok: true` 應可成立 — 惟此為 T-012，屬 trials-efficacy 領域，
本角色僅完成合法取得，登錄動作與後續分析留給該角色與 Director。PDF/parsed markdown 本身依
`.gitignore` 規則（`**/20_EVIDENCE/**/fulltext/`）不會進入版本控制，僅本 manifest 之 metadata
會被 commit。

**未合法取得全文（本輪已查證確認，非未嘗試）**：
- Singh H et al. 2024（PMID 39587804, DOI 10.1080/17512433.2024.2433603）— Europe PMC 明確標示
  `is_open_access: false`，無 PMCID。**BLOCKED_FOR_SOURCE**（已取得完整結構化摘要，資訊已足夠
  當前需求）。
- Li H, Li J 2026（PMID 42528438, DOI 10.31083/bjhm56151, *Br J Hosp Med*）— 同樣
  `is_open_access: false`，無 PMCID。**BLOCKED_FOR_SOURCE**。

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
