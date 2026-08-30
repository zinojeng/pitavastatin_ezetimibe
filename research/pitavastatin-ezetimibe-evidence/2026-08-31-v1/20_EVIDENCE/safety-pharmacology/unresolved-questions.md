# unresolved-questions — safety-pharmacology-intelligence

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`

角色專屬追蹤清單（與共用的 `04_OPEN-QUESTIONS.md` 不同 — 本角色無該檔案寫入權；下方項目已於
`90_CROSS-SESSION-LOG/safety-pharmacology-log.md` 回報 Director，供其決定是否併入共用檔案）。
分類沿用 CLAUDE.md §13 分類：`NEEDS_SOURCE` | `NEEDS_ANALYST` | `NEEDS_METHODS` | `NEEDS_PI`。

## NEEDS_ANALYST

1. Chou MT et al. 2022（1PC111, Taiwan/Australia/NZ）AE/CK/liver 安全性表格逐字數據 — 本輪僅取得
   一組低信心、來源為 AI 搜尋摘要（非逐字引用原文）的 ADR 數字（8.6%/6.1%/7.0%），**不得**進入
   `40_SYNTHESIS/` 或任何 manuscript。需 `research_hub`（僅限 metadata-only 工具）、機構訂閱、或
   直接 PDF 存取後重新逐字核對。
2. `Tonvasca_2026.md` line 2796 上標角「13」但內容應對應 ref 12（Sydhom）而非 ref 13
   （Katzmann）——疑似編號誤植，`SOURCE_VALUE = "13"`, `FLAG = POSSIBLE_ERROR`，未逕行更正。
3. `02_SOURCE-INVENTORY.md` #23（Chien SC 2019）目前主題標註為「Statin discontinuation
   outcomes」，經核實其實際主題為「2019 台灣脂肪與動脈硬化學會 statin intolerance 專家共識」——
   建議更正該列 topic 描述（本角色無該檔案寫入權，已回報 Director）。
4. `02_SOURCE-INVENTORY.md` T-005（Taiwan STS 2026 consensus）目前狀態標「Not yet located」——
   本輪已透過 Crossref 確認存在且取得完整書目資訊（DOI 10.1016/j.jfma.2026.04.111），建議更正
   狀態並補上引用（已回報 Director）。

## NEEDS_SOURCE

5. Pitavastatin 與 OATP1B1 之定量 PK 交互作用原始研究（現況僅有綜述引用之「約 90% 肝臟清除」數字，
   未鎖定可逐字核對之原始文獻）。
6. Pitavastatin 與 BCRP inhibitor 之具體交互作用 fold-change 數字（目前僅有「pitavastatin 為
   BCRP 受質」之機轉敘述，無定量交互作用數據）。
7. Pitavastatin 與 clarithromycin 之獨立交互作用數字（FDA label 本輪擷取段落僅含 erythromycin
   作為 macrolide 代表，clarithromycin 未見於擷取範圍 —— 需確認是否為 label 本身未列，或僅為本輪
   擷取遺漏）。
8. Itraconazole/pitavastatin PK 研究（PMID 27121674）完整摘要與數字（本輪僅取得標題）——為驗證
   「低 CYP3A4-dependence」最直接的機轉證據之一，優先度高。
9. Pitavastatin/ezetimibe FDC（無論 Chou MT 2022 或 K-924）之 CKD 特異性、elderly 特異性安全性
   次族群數據 — 兩篇已核對之劑量比較試驗均未報告此類次族群分析。**BLOCKED_FOR_SOURCE 候選**，
   若下一輪仍查無，建議正式登記為 BLOCKED_FOR_SOURCE 而非留白。
10. Pitavastatin 專屬（非 statin 類別一般化）與 CCB/warfarin 之定量交互作用數字（fold-change 或
    等效統計量）——現有引用（Fravel/Ernst、Ehelepola、Engell 等）皆為 statin 類別一般性證據或其他
    statin（atorvastatin）之證據，非 pitavastatin 專屬定量數據。
11. Taiwan STS 2026 共識（Wu YJ et al.）與 2019 台灣 statin intolerance 共識（Chien SC et al.）
    之全文逐字內容 — 兩篇本輪皆僅取得摘要/摘要層級 synopsis，未逐字核對全文，`CONFIDENCE:
    MODERATE`。建議優先嘗試台灣脂肪與動脈硬化學會（TAS）官網公開 PDF 管道。
12. CAMPUS（NCT03532620）與 LESS-DM（pitavastatin dose-comparison 糖尿病結果試驗）之最終結果
    論文 — 本輪僅找到 protocol，需查 ClinicalTrials.gov 完成狀態確認是否已發表。
13. "J-PREDICT" 命名之 pitavastatin 糖尿病預防試驗 — 查無此名稱之 PubMed 收錄研究。若此名稱曾見於
    任何 legacy 材料或未來 PI 提供之資料，應視為 unverified，需 PI 提供具體引用後才可使用
    （`NEEDS_PI` 候選，惟目前本專案任何既有文件皆未出現此名稱，暫列 NEEDS_SOURCE 而非升級）。

## NEEDS_METHODS

14. Pitavastatin 血糖/NODM 之 dose-response 論述目前須跨試驗拼接（1mg=Nakagomi 2015；2mg=
    PAPAGO-T/Sasaki/Mita；4mg=CAPITAIN/Devi），並非單一試驗內之 head-to-head dose-ranging 設計 —
    若 40_SYNTHESIS/manuscript 欲呈現「劑量-反應」曲線或聲明，須明確揭露此方法學限制，避免給人
    「已有正式 dose-ranging RCT」的錯誤印象。

## 待 Director 裁示之範疇問題

15. Search Protocol item 10（Lp(a)/ApoB/remnant 之殘餘風險藥理學）屬本角色領域，惟本輪任務指派未
    涵蓋，依其自身 ≤10–15% 權重定位延後處理，已於 90_CROSS-SESSION-LOG 向 Director 確認並取得
    「暫緩、不需提前處理」之回覆（2026-08-31）。列此僅作追蹤，非待辦阻塞項。

## Wave 2 更新（2026-08-31）

**新解決**：
- 項目 7（clarithromycin）：已直接重新查證 DailyMed，**確認 label 全文未提及**，由「本輪未查獲」
  升級為「確認缺席」（CONFIRMED_ABSENT_FROM_LABEL）——已記入 `ddi-matrix.md`，惟仍不等於「無交互
  作用」，維持 EXPERT INTERPRETATION 層級的謹慎用語。
- T-013（Corsini A 2011）：已透過 Crossref 完成書目層級 VERIFIED_MATCH。

**新缺口**：
16. Li H, Li J 2026（*Br J Hosp Med*, PMID 42528438）與 Singh H et al. 2024（PMID 39587804）皆經
    Europe PMC 查證為非開放取用、無 PMCID —— **正式登記為 BLOCKED_FOR_SOURCE**（已用盡本輪可用
    之合法免費全文取得管道：Unpaywall 查無記錄、Europe PMC 標示非開放取用、`download_paper`
    工具已被禁用不得使用）。若需全文，僅能透過機構訂閱或直接聯繫作者，已超出本專案目前工具範圍。
17. Fenofibrate 交互作用數字（AUC+18%/Cmax+11%）之精確 section 定位已確認為 Section 12.3 Table
    3，而非 Section 7 DDI 表本身 — 撰寫時若需引用 section 編號應以此為準。
18. 新增查得之 fibrates 類別整體/niacin/colchicine 交互作用提示（見 `ddi-matrix.md`）皆為風險/
    效益權衡用語，無具體 fold-change 數字 — 若 manuscript 需要量化數據，此三項仍屬 INSUFFICIENT
    EVIDENCE（量化層面）。
19. BCRP 缺口部分收斂：找到兩篇 open-access 佐證（Schmith 2026 PMC12868915、Stäuble 2026
    PMC12929307）支持 OATP1B1 為 pitavastatin 主要機轉之定位，但**仍未找到 pitavastatin 與具體
    BCRP inhibitor 之定量 fold-change 數字** — 維持 OPEN GAP，NEEDS_SOURCE。
20. **CKD 缺口已大部分解決**：已下載並解析 Tramontano D et al. 2025（*Drugs*, PMID 40106181,
    PMC12098426）全文，其 Table 1 提供 pitavastatin 於 CKD G3a–G5 之劑量上限（2mg），並已直接
    對照 FDA LIVALO label 官方原文確認一致（moderate/severe renal impairment 及 ESRD 洗腎病人：
    起始 1mg，上限 2mg；mild renal impairment 免調整）。**仍未解決**：pitavastatin/ezetimibe
    FDC 併用於 CKD 病人之專屬劑量調整建議（label 未特別處理 FDC 情境）——此子項維持
    BLOCKED_FOR_SOURCE。

## Resolved（本輪內部已解決，僅供追蹤）

- Sydhom P 2024 vs Singh H 2024「2024 systematic review」指認混淆問題 — 已於 `evidence-map.md`
  §1.1–1.2 明確區分，不再視為待解問題。
