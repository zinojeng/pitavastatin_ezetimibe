---
marp: true
paginate: true
---

# Pitavastatin + Ezetimibe FDC
## 臨床定位與誠實攻防

**Treat the target, not the dose.**

PROJECT: pitavastatin-ezetimibe-evidence · RUN 2026-09-01-v1
Final Gate: **PASS_WITH_MINOR_ISSUES**（獨立稽核已完成）

<!-- 講者註：本簡報所有數字皆可溯源至專案 20_EVIDENCE/40_SYNTHESIS，Q&A 時可直接引用出處。本簡報刻意保留誠實限制與攻防段落，不為求流暢而省略。 -->

---

## 核心問題重新框架

**"Should we treat the statin dose, or treat the LDL target?"**

- 2026 ACC/AHA guideline（DOI `10.1161/CIR.0000000000001423`，本 run 已獨立驗證）以**絕對 LDL-C/non-HDL-C 目標**建構治療框架
- 依風險分層區分四種目標：<100 / <70 / <55 mg/dL，各附對應 non-HDL-C 共同目標
- 不是「相對降幅百分比」，而是「達標與否」
- **驗證方法之誠實限制**：`ahajournals.org` 對本專案工具為 Cloudflare 阻擋，故 T-101 之驗證為
  **獨立佐證式驗證**（DOI 解析 302 重導向、Crossref metadata 比對、123 頁內部一致性系統性檢查三項
  外部可查證方式），**非**逐位元組出版社重新下載比對——此限制須誠實揭露，不可陳述為與出版社原始檔案
  逐字比對相符

<!-- 講者註：GUIDELINE/CONSENSUS。逐字溯源見 40_SYNTHESIS/00_executive-synthesis.md §2.1、§3；Decision 2026-09-01-04。若被問「你們真的看過原文全文嗎」，誠實說明三項獨立佐證方法與 Cloudflare 限制，不誇大為逐字比對。 -->

---

## Severe Hypercholesterolemia（LDL-C≥190 mg/dL）：三層絕對目標

T-101 對此族群設定**三層**結構（非單一目標），已由三套獨立萃取工具交叉驗證：

| 層級 | LDL-C 目標 | non-HDL-C 目標 | COR/LOE |
|---|---|---|---|
| Tier 1：無 ASCVD/HeFH/subclinical atherosclerosis/其他風險因子 | <100 mg/dL (2.6 mmol/L) | <130 mg/dL (3.4 mmol/L) | 1, B-NR |
| Tier 2：合併 HeFH/subclinical atherosclerosis/其他風險因子，無 clinical ASCVD | <70 mg/dL (1.8 mmol/L) | <100 mg/dL（**2.6 mmol/L**，見下注） | 1, B-R |
| Tier 3：合併 clinical ASCVD | <55 mg/dL (1.4 mmol/L) | <85 mg/dL (2.2 mmol/L) | 1, B-R |

**Tier 2 non-HDL-C 誠實註記（不可省略）**：guideline 權威條列段落（頁 e1199，編號建議 #4）印為
**2.6 mmol/L**——與 100 mg/dL 之標準換算、及文件其餘所有「<100 mg/dL」出現處一致，本表以此為準。
但同一份 guideline 自己的「Table 1. 2018 vs 2026」摘要比較表（頁 e1159）**確實、完整、無斷裂地**
印著同一條建議之 non-HDL-C 目標為 **2.4 mmol/L**——這是來源出版品**自身內部**的印刷不一致
（most plausibly 摘要表本身之 typo），**不是**本專案任何萃取工具的假影，故不予捨棄，僅標註為
來源異常值。LDL-C 目標本身（<70 mg/dL）兩處相符，不受影響。

<!-- 講者註：GUIDELINE/CONSENSUS。此為本 run 歷經三輪修正才定案之發現（Decision 2026-09-01-08→10→14），過程本身即為 Numeric Integrity Rule 的實際示範，Q&A 時可誠實引用此修正過程本身作為方法論嚴謹度的證明。 -->

---

## Level 1 證據：LDL-lowering efficacy（強）

- Pitavastatin/ezetimibe FDC 已跨國複現：Taiwan/Australia/NZ（Chou 2022, Clin Ther）、Japan（K-924, Tsujita 2023）
- K-924 matched-dose LS-difference（已獨立核實）：
  - combo 2/10 vs pitava 2mg：**−11.9%**（95% CI −15.2 to −8.7）
  - combo 4/10 vs pitava 4mg：**−12.7%**（95% CI −15.9 to −9.4）
- **「−51.4% vs −45.2%」已撤回** — 非該試驗 prespecified 統計比較，不可再引用

<!-- 講者註：DIRECT EVIDENCE / LDL-C SURROGATE EFFICACY。若被問及舊版跨組並列數字，誠實說明已撤回，改引上述數字。 -->

---

## Level 2 證據：策略層級 CV outcome（非 pitavastatin 專屬）

- RACING：rosuvastatin 10mg + ezetimibe 10mg vs 高強度單方
- 3-yr MACE **9.1% vs 9.9%**（non-inferior）
- **明確揭露：這是 rosuvastatin 的證據，不是 pitavastatin 的證據**
- 屬策略層級間接支持，非 FDC 專屬直接證據

<!-- 講者註：INDIRECT EVIDENCE / NONINFERIORITY。「這不是你們的藥」是合理質疑，誠實承認即可，這正是本專案刻意標示的區隔。 -->

---

## Level 3 證據：Pitavastatin/Ezetimibe 專屬 hard-outcome（誠實：尚未證實）

- HIJ-PROPER 整體 primary endpoint：32.8% vs 36.9%，**HR 0.89（95% CI 0.76–1.04, P=0.152）** — 未達統計優越性
- 兩個 hypothesis-generating 次族群訊號（**不可合併陳述**）：
  - Sitosterol/absorber-phenotype：**HR 0.71**（信心度 MODERATE）
  - Baseline LDL-C 分層（高 LDL-C 組）：**HR 0.72**，interaction **P=0.012**
- 本專案至今找不到 FDC 專屬、已證實的 hard-outcome 優越性證據

<!-- 講者註：這是誠實簡報的核心限制，應主動說明，不應迴避。兩個次族群切分變數不同，各自獨立呈現。 -->

---

## Guideline 支持：範圍與限制（POST-FINAL-GATE 已修正）

**極高風險（VHR）二級預防**（T-101 頁 e1208）：
- Ezetimibe **and/or** PCSK9 mAb：**COR 1, LOE A**（兩者之間無偏好）
- Bempedoic acid：獨立、較低的 **COR 2a, LOE B-R**
- Inclisiran：**COR 2a, LOE B-R**，且限定無法耐受/取得 PCSK9 mAb 或明確偏好低頻給藥者

**非極高風險**：ezetimibe / PCSK9 mAb / bempedoic acid **三者確實同等**（COR 2a, LOE B-R）

<!-- 講者註：GUIDELINE/CONSENSUS，statin-agnostic，不可轉引為 pitavastatin 專屬證據。VHR 層級 ezetimibe 相對 PCSK9 mAb 無偏好，這是任何「ezetimibe 優先」論述必須揭露的限制；但 ezetimibe/PCSK9 mAb 相對 bempedoic acid/inclisiran 確有形式偏好（COR 1 vs 2a）。 -->

---

## 台灣/亞洲族群定位

- T-101 自身陳述：東亞族群「may be more prone to side effects due to inherited drug metabolism effects; thus, initial treatment should be with lower doses」
  - 此為 statin **類別**一般性陳述，**非** pitavastatin 專屬
- Li 2026（中國回溯性世代，pitavastatin 4mg vs atorvastatin 20mg，≥60 歲）：NODM **0% vs 10.29%**（OR 0.212）
  - 單中心觀察性、非隨機，樣本數小

<!-- 講者註：guideline 段落為 GUIDELINE/CONSENSUS；Li 2026 為 OBSERVATIONAL SIGNAL，不可獨立支撐結論。 -->

---

## 安全性三支柱：血糖 / DDI / CKD

- **血糖**：pitavastatin 相對其他常用高效能 statin，**可能有較有利的血糖側寫** — 不寫「不致糖尿病」
- **DDI**：**低 CYP3A4 依賴** — 不寫「無交互作用」；OATP1B1 路徑（cyclosporine 禁忌、gemfibrozil 避免併用）風險依然存在
- **CKD**：Pitavastatin 單方為所有 statin 中劑量最保守（1mg 起始/2mg 上限）；**FDC 本身 CKD 專屬資料仍缺乏**

<!-- 講者註：務必保留「相較於……」「可能」等校準用語，此為本專案自 2026-08-31-v1 起之強制語言規則。 -->

---

## 依從性與真實世界證據

- FDC vs 分開處方：LDL-C 降幅差 **−28.4% vs −19.4%**（p<0.0001，Katzmann 2022）
  - **該研究無依從性直接測量** — 「FDC 提升依從性」是推論鏈，非直接證實
- Pitavastatin+ezetimibe FDC 專屬 RWE：**目前僅 TE-013 一篇**（Taiwan post-PCI，N=120，單臂兩中心）
  - 證據基礎仍薄弱

<!-- 講者註：LDL-C SURROGATE EFFICACY / OBSERVATIONAL SIGNAL。若被問「RWE 充分嗎」，誠實回答目前僅一篇。 -->

---

## 攻防：何時不選 Pitavastatin/Ezetimibe FDC

| 情境 | 更適當之替代方案 |
|---|---|
| 完全確立之 statin intolerance | Ezetimibe 單方 + bempedoic acid，或 PCSK9-targeting therapy |
| 已知 OATP1B1 高風險多重用藥（cyclosporine、gemfibrozil） | PCSK9-targeting therapy 或 inclisiran |
| 進行中透析（ESRD/HD） | PCSK9-targeting therapy（保守選項，非已證實更安全） |
| 追求 hard-outcome-proven 替代方案 | Bempedoic acid（CLEAR-Outcomes）、PCSK9i（FOURIER/ODYSSEY OUTCOMES） |

**例外**：Inclisiran **沒有**已發表 hard-outcome trial，不應與 bempedoic acid/PCSK9i 並列為「已證實」替代方案

<!-- 講者註：此頁為刻意保留的誠實攻防頁，Q&A 時應主動引用，而非等對手提出才承認。 -->

---

## 攻防：「先最大化 statin 劑量」是否已過時？

**不是** — 這是有直接 pitavastatin 專屬證據支持的合理立場：

- REAL-CAD（pitavastatin 4mg vs 1mg）：**HR 0.81**（95% CI 0.69–0.95, P=0.01）— 達統計顯著
- 2026 ACC/AHA guideline 本身仍以「statin 優先」為 Class 1 建議結構（逐步式，非 upfront combination）
- **誠實限制**：本專案未找到 pitavastatin/ezetimibe FDC 與高強度 statin 單方之直接頭對頭試驗——
  RACING 為 rosuvastatin 版本、K-924 為 pitavastatin 內部劑量比較，兩者皆非此比較的直接證據
- 真正的問題不是「combination 已取代劑量最大化」，而是：病人可耐受劑量提升時，FDC 能否讓過渡更快、更舒適

<!-- 講者註：REAL-CAD = SUPERIORITY，但限 pitavastatin 單方劑量問題，非 FDC。FDC vs 最大化劑量之直接比較 = EXPERT INFERENCE，無直接資料（04_OPEN-QUESTIONS.md Q6）。 -->

---

## 最大的未驗證支撐性主張：Taiwan STS 2026

- Taiwan STS（Suboptimally Tolerable Statins）2026 共識 —「重新定位 ezetimibe 為高/極高風險首選加藥」— 是本專案整體論述框架的核心組織概念
- **本 run 再次確認：其具體內容主張至今仍 `BLOCKED_FOR_SOURCE`**（Cloudflare 阻擋，與 OA 授權狀態無關 — 已確認為真正 Gold OA/CC BY，但仍無法擷取全文）
- **本專案自我評估：這是單一最大的未獨立驗證但具支撐性主張** — 比任何個別試驗證據缺口都更關鍵

<!-- 講者註：此頁必須保留於任何正式簡報中，不可為求論述流暢而省略。若被問及 Taiwan STS 具體建議內容，誠實回答：書目資訊已驗證存在，具體內容本專案尚未取得可獨立查證之全文。 -->

---

## 結論：可防禦的定位聲明

**可以說的：**
- Pitavastatin/ezetimibe FDC 有強健、已跨國複現的 LDL-C 降幅證據（Level 1）
- 2026 ACC/AHA guideline 支持 statin+ezetimibe 併用策略為極高風險族群 COR 1, LOE A 建議（statin-agnostic）
- Pitavastatin 之低 CYP3A4 依賴、相對有利之血糖側寫，於特定多重用藥/東亞情境有合理藥理學定位

**不可以說的：**
- 「FDC 已證實降低心血管事件」（Level 3 尚未達成）
- 「Guideline 建議 ezetimibe 作為首選加藥」（guideline 並列選項，非偏好 ezetimibe）
- 「Pitavastatin 不致糖尿病」「無藥物交互作用」
- 「與 Taiwan STS 2026 一致」用於任何尚未獨立驗證之具體內容主張

<!-- 講者註：本頁為全案總結，任何刪減版簡報皆須保留「不可以說的」四點。 -->
