# 01 論斷—證據對照表（Claim-Evidence Matrix）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Wave 3 Synthesis · 2026-08-31

Evidence Hierarchy 標籤定義見 `CLAUDE.md` §7：`DIRECT EVIDENCE` | `INDIRECT EVIDENCE` |
`GUIDELINE/CONSENSUS` | `OBSERVATIONAL EVIDENCE` | `MECHANISTIC SUPPORT` | `INSTITUTIONAL PRACTICE` |
`EXPERT INTERPRETATION` | `INSUFFICIENT EVIDENCE`。每一列僅陳述已驗證論斷；未驗證或
`BLOCKED_FOR_SOURCE` 之來源不得單獨作為 claim 依據，須於 notes 欄註明限制。

| # | 論斷（Claim） | Citation ID(s) | Evidence Hierarchy | 備註 |
|---|---|---|---|---|
| C1 | Pitavastatin/ezetimibe FDC 相較 pitavastatin 單方，LDL-C 降幅 >50%，於台灣/澳洲/紐西蘭、日本、韓國三個獨立 Phase III RCT 中一致重現 | #33, T-004a, T-028 | `DIRECT EVIDENCE`（三國獨立複製） | T-028 全文 `BLOCKED_FOR_SOURCE`，僅摘要數字已驗證；#33 安全性表格 `BLOCKED_FOR_SOURCE` |
| C2 | Pitavastatin/ezetimibe FDC（2mg+eze10 vs 4mg+eze10）劑量間 LDL-C 降幅差異達統計顯著 | T-004a | `DIRECT EVIDENCE` | −6.4%（95% CI −9.6 至 −3.2, p≤0.001）；pairwise MMRM，非 pooled |
| C3 | 「加 ezetimibe」相較「statin 劑量加倍」（pitavastatin 2mg+eze10 vs 4mg alone）孰優孰劣 | T-004a | `INSUFFICIENT EVIDENCE` | **此比較從未被正式檢定**，僅有描述性點估計（−51.4% vs −45.2%），無 p 值/CI；不得呈現為顯著結果（Decision 2026-08-31-16） |
| C4 | Moderate-intensity statin + ezetimibe（非 pitavastatin 專屬）作為策略，達成與 high-intensity statin monotherapy 相當的心血管結果（non-inferiority），且達標率更高、不耐受更少 | T-002 (RACING) | `INDIRECT EVIDENCE` | Rosuvastatin，非 pitavastatin——不可作為 pitavastatin/ezetimibe FDC 的心血管結果證據引用 |
| C5 | Pitavastatin+ezetimibe（vs pitavastatin alone）於 ACS 病人整體未達成 hard-outcome 統計顯著優越性 | T-001 (HIJ-PROPER) | `DIRECT EVIDENCE`（trial 本身）／結論為 non-superiority | 32.8% vs 36.9%, HR 0.89, 95% CI 0.76–1.04, P=0.152 |
| C6 | 高 baseline sitosterol（cholesterol-absorber phenotype）病人使用 pitavastatin+ezetimibe 效果可能較佳 | T-001 次族群分析 | `INSUFFICIENT EVIDENCE`（hypothesis-generating） | HR 0.71，次族群訊號，非已證實策略；不得表述為「已證實可用 phenotype 篩選病人」 |
| C7 | Pitavastatin 單方對心血管硬終點有效（HIV 族群、安慰劑對照） | T-015 (REPRIEVE) | `DIRECT EVIDENCE`（pitavastatin 單方，非 FDC） | MACE HR 0.65 (95% CI 0.48–0.90, P=0.002)；**不可用以墊高或替代 C5/Level 3 缺口** |
| C8 | Pitavastatin 4mg 相較 1mg 於穩定冠心病病人降低心血管硬終點 | T-016 (REAL-CAD) | `DIRECT EVIDENCE`（pitavastatin 劑量比較，非 FDC） | HR 0.81 (95% CI 0.69–0.95, P=0.01)；**同樣不可替代 Level 3 缺口** |
| C9 | Low/moderate-intensity statin + ezetimibe 相較 high-intensity statin monotherapy，觀察性資料顯示臨床結果較佳，RCT 資料顯示無顯著差異 | citation #26 (Sydhom 2024) | `OBSERVATIONAL EVIDENCE`（僅限 observational-pooled 部分）；RCT-pooled 部分 `INSUFFICIENT EVIDENCE`（未達顯著） | **PI 明訂用語（Decision 2026-08-31-06）**：僅陳述 observational-pooled 效益；RCT-pooled 臨床終點未達統計顯著。MACE/CV死亡/全因死亡/中風 HR（0.76/0.80/0.84/0.81）不得呈現為 RCT-grade 證據 |
| C10 | Pitavastatin 相較 atorvastatin/rosuvastatin，new-onset diabetes（NODM）風險較低 | T-003 (Singh 2024) | `INDIRECT EVIDENCE`（RCT+observational 混合，未拆解） | RR 0.86 vs atorvastatin, RR 0.77 vs rosuvastatin；**全文 `BLOCKED_FOR_SOURCE`，無法確認 RCT-only 子集是否一致**——與 C9 同類風險，尚未解決（Challenge Round 發現 #4） |
| C11 | Pitavastatin「可能有較有利的血糖 profile」 | T-003, T-017（部分佐證） | `INDIRECT EVIDENCE` / `OBSERVATIONAL EVIDENCE` | **禁止表述為「does not cause diabetes」**（`CLAUDE.md` §5）；T-017 為 n=126 abstract-only 小型研究，效應量顯著（0% vs 10.29%）需全文驗證後方可強調 |
| C12 | Pitavastatin 具有「low CYP3A4-dependent interaction liability」 | T-010 (FDA label) | `INSTITUTIONAL PRACTICE`（法規標籤層級） | 標籤代謝敘述完全未提及 CYP3A4；**禁止表述為「no DDI」**。Cyclosporine 禁忌（AUC 4.6倍）、erythromycin/rifampin 劑量上限、gemfibrozil 避免併用 |
| C13 | Pitavastatin 單方於腎功能不全病人（eGFR 15–59 或洗腎）建議劑量為 1mg 起始/2mg 上限，為七種 statin 中劑量上限最低者 | T-018 | `OBSERVATIONAL EVIDENCE`/文獻回顧交叉驗證 FDA 標籤 | 僅限 pitavastatin **單方**；FDC 複方 CKD 劑量無任何文獻直接處理（見 C18 開放缺口） |
| C14 | Pitavastatin 與 BCRP 抑制劑併用可能有臨床相關交互作用 | T-019, T-020, T-026, T-027 | `MECHANISTIC SUPPORT`（機轉/PBPK 模擬） | 皆非孤立 BCRP 抑制劑的臨床定量數據；T-026 的 AUC ratio 2.24 來自多重機轉的合併干擾物（elexacaftor-tezacaftor-ivacaftor），不可作為 pitavastatin 專屬 BCRP fold-change 引用 |
| C15 | Fixed-dose combination（FDC）相較分開服用（free/separate pill combination），adherence 較佳 | T-012, T-022, T-025 | `INDIRECT EVIDENCE`（全數觀察性設計，非 pitavastatin 專屬或跨疾病領域） | T-012/T-025 為其他 statin（非 pitavastatin）；T-022 為跨疾病領域一般性 meta-analysis；**因果推論需謹慎（healthy-adherer bias）**，不可直接寫成因果語句 |
| C16 | FDC 相較分開服用可降低心血管事件風險 | T-025 次族群 | `INSUFFICIENT EVIDENCE`（次族群訊號，未經整體分析複製） | R10/E10 次族群 MACE HR 0.58（p=0.030）**未在該研究整體世代分析中重現**——不得單獨引用此次族群數字 |
| C17 | 台灣 STS 2026 共識將 ezetimibe 定位為 high/very-high-risk 病人第一線 add-on，extremely-high-risk 病人及早合併治療 | T-005 | `GUIDELINE/CONSENSUS`（框架層級）——**具體措辭尚未經原文驗證** | T-005 全文 `BLOCKED_FOR_SOURCE`；此論斷目前僅追溯至 `pitavastatin topic.md` 之轉述，非獨立驗證之原文——Challenge Round 最高優先未驗證論述 |
| C18 | FDC 複方於 CKD 病人之劑量調整 | *(無)* | *(無可用證據)* | **開放缺口**——本專案未發現任何文獻直接處理 pitavastatin+ezetimibe FDC 於 CKD 病人的劑量問題；僅 EXPERT INTERPRETATION 層級的合理推論（FDC 可能沿用其 statin 成分的單方 CKD 劑量指引），非文獻結論 |
| C19 | 2026 ACC/AHA 與台灣 2023 TSC CCS 對極高風險族群的 LDL-C 目標 | #28（<55 mg/dL）, #30（<50 mg/dL） | `GUIDELINE/CONSENSUS` — **#28 之兩數字（<55、<70）皆僅追溯至 `Tonvasca_2026.md` 轉載表格，未經獨立對照原文（Wave 4 稽核 Finding 1，已修正）** | **兩個指引、兩個不同數字、不同風險分層定義，不可互換或混合引用** |
| C20 | ESC 2025 Focused Update 建議 ACS 病人於住院期間即完成降脂強化 | T-007（全文 blocked）; T-021（二手轉述，帶「舊版 2018 指引」警示） | `GUIDELINE/CONSENSUS`——**原文措辭未驗證** | T-021 為 review 轉述，非指引原文；其「美國指引未建議 upfront combination」之比較段落引用的是**舊版 2018 AHA/ACC**，非 2026 新版——不可誤植為對 2026 版本的陳述 |
