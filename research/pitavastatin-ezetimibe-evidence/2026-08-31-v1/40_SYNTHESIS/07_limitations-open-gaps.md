# 07 限制與未解缺口（Limitations / Open Gaps）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Wave 3 Synthesis · 2026-08-31

本節彙整 `30_METHODS/shared/wave2-challenge-round.md`（Director 於 Gate 2 執行的四角度對抗性審查）
與 Wave 3 新增發現，依優先順序排列。詳細出處請見 `04_OPEN-QUESTIONS.md`。

## 六份指引/試驗全文，`NEEDS_PI`/`BLOCKED_FOR_SOURCE`（PI 已明確指示維持此狀態）

| Citation | 內容 | 阻擋方式 | 已嘗試的合法管道 |
|---|---|---|---|
| T-005 | 台灣 STS 2026 共識 | Cloudflare bot-challenge；精確 NCBI elink 二次確認為真陰性 | curl/WebFetch 直接嘗試、Europe PMC PMCID 查詢、Wave 3 未再嘗試（PI 指示不再重試） |
| T-006 | 台灣 Lp(a) 2026 共識 | 無 PMC 收錄 | WebSearch、tas.org.tw 鏡像 PII 猜測（均失敗，未繼續猜測） |
| #34 | 2019 base ESC/EAS 指引 | 無 PMC 收錄；無台灣學會式鏡像可用（歐洲文件） | elink 確認 |
| #28 | 2026 ACC/AHA 指引 | Cloudflare bot-challenge，PI 提供之官方 URL 亦被擋 | curl/WebFetch、Europe PMC 交叉確認 |
| T-007 | ESC 2025 Focused Update | Cloudflare bot-challenge | curl/WebFetch、Europe PMC 交叉確認；二手轉述（T-021）部分佐證但非原文 |
| #33 | Chou MT 2022 安全性表格 | Unpaywall 無 OA；Springer/直接 PDF 連結均為存取限制頁 | Unpaywall、直接 HTTP 檢查、Europe PMC PMCID 查詢（Wave 3 仍失敗） |

**PI 明確指示（本輪）**：上述六份文件維持記錄為 `NEEDS_PI`/`BLOCKED_FOR_SOURCE`，**不假設 PI 可以或
將會提供**，任一角色皆不應在無新指示下再次嘗試取得。

## Challenge Round 四項優先發現（詳見 `wave2-challenge-round.md`）

1. **台灣 STS 2026「ezetimibe 為第一線 add-on」的具體論述，從未經原文驗證**——本專案對
   pitavastatin/ezetimibe FDC 最具說服力的框架性論述，目前唯一依據是 `pitavastatin topic.md` 自身的
   轉述。這是本輪標記的最高優先未驗證論述。
2. **REPRIEVE（T-015）/REAL-CAD（T-016）與 FDC 混淆風險**——兩者皆為正向的 pitavastatin 單方
   hard-outcome RCT，是本專案證據庫中最容易被誤讀為「已墊高 Level 3 缺口」的高風險內容，任何未來
   輸出都必須明確標註「pitavastatin 單方，非 FDC」。
3. **FDC 專屬 CKD 劑量缺口**——本專案最高風險的安全性缺口：僅有 pitavastatin 單方 CKD 劑量（T-018）
   已確認，FDC 複方本身無任何文獻直接處理。
4. **Singh 2024（T-003）RCT/observational 混合，尚未拆解**——與 Sydhom 2024（#26）已解決過的同類
   問題平行，但 T-003 全文兩輪皆確認 `BLOCKED_FOR_SOURCE`，無法比照 #26 的方式拆解驗證。

## Wave 3 新增的缺口與待辦

- **T-024（Abbas 2026）**：可能是第一篇 pitavastatin/ezetimibe FDC 專屬 meta-analysis，經三次合法
  管道嘗試（Unpaywall、Taylor & Francis figshare — 遇 AWS WAF bot-challenge、ResearchGate 鏡像）
  皆未取得全文。若未來取得，可能對 Level 1/2 框架帶來實質更新——列為下一輪最高優先目標。
- **T-028（Jeong 2022，韓國）全文**：目前僅有摘要層級數字（Yonsei 大學典藏連結遇 JS anti-bot
  challenge，未解），AE/CK/肝功能細節待補。
- **BCRP 孤立抑制劑定量交互作用數據**：不存在於本專案已檢索文獻中，僅有機轉性 PBPK 模擬
  （T-019、T-020、T-026、T-027）作為間接佐證，非臨床測量數據。
- **T-009 第 3 項（van Driel/Cochrane）的替代來源說明**：safety-pharmacology 因無法直接取得
  Cochrane 摘要本身，改用同團隊之期刊發表版本（Deichmann et al., PMID 27660570）——此替代來源之
  數字未經獨立確認與 Cochrane 記錄本身完全一致，引用精確數字時應註明此限制。
- **T-006 作者列表的重複姓名**（"Wang CY" 出現兩次）：依 Numeric Integrity Rule 原樣保留，未經
  獨立確認是轉錄重複或兩位不同的同名共同作者。
- **`Tonvasca_2026.md` 自身的兩處內部不一致**（第 2796 行上標/引用不匹配；citation #33 於文件內
  以兩種不同格式引用）：屬 legacy 來源本身問題，本專案不修改原始文件，僅供記錄。

## 未於本 Wave 執行的工作（範疇界定）

- **`50_MANUSCRIPT/` 手稿/投影片撰寫——本 Wave 未獲 PI 授權**，即使 Gate 3 通過亦不自動開放，需
  另行 PI 指示。
- **Wave 4 獨立稽核**——尚未啟動，將於 Gate 3 通過後由獨立稽核角色（sonnet，唯讀，僅可寫入
  `99_FINAL-QA.md`）執行。
- **safety-pharmacology 的 git commit 權限問題**（其任務指示明訂「不執行 commit/push」）——PI 於
  Wave 2 授權時未明確處理此項，目前該角色的工作成果透過 Codex 整合流程間接可見，非阻塞性問題，
  但仍為待 PI 決定的未結事項。
