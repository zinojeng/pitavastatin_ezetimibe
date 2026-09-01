# 01 攻防章節（整合三角色貢獻）— Pitavastatin/Ezetimibe FDC

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Director 整合 guideline-risk（`focus-area-5-attack-defense.md`）、trials-efficacy（`evidence-map.md`
末段）、safety-pharmacology（`attack-defense-contribution.md`）三份原始貢獻，對應 PI 六大焦點第 5
項要求。**本文件刻意呈現最誠實版本的反方論證，非替 FDC 單方面辯護** —— 每項攻擊皆保留來源角色之
原始判斷；有防禦時列出防禦，**沒有站得住腳的防禦時，明確承認**（尤以 Attack 4 為代表）。

---

## A. Product-specific MACE limitation（PI 焦點 5-1）

**攻擊**：Pitavastatin+ezetimibe FDC 沒有自己專屬、達統計顯著的 hard-outcome 優越性證據。
HIJ-PROPER 整體 primary endpoint HR 0.89（95% CI 0.76–1.04, P=0.152）未達顯著——**這是唯一直接
檢驗此問題的 RCT**，本 run 確認至今無新試驗關閉此缺口。

**目前能提供的最強證據**：兩個次族群分析（TE-016 absorber-phenotype、TE-017 baseline-LDL-C 分層，
interaction P=0.012）皆為 `hypothesis-generating`，**不構成** superiority 論斷的替代。

**誠實結論（無法迴避）**：若對手要求「pitavastatin/ezetimibe FDC 專屬的 hard-outcome 優越性證據」，
本專案**目前無法提供**達到 superiority 等級的答案，只能提供：(1) Level 1 LDL-lowering 之強證據，
(2) Level 2 之 statin-class-general 併用策略證據（RACING，非 pitavastatin 專屬），(3) Level 3 之
hypothesis-generating 次族群訊號。**任何簡報都不應暗示這三者加總等於直接的 hard-outcome
superiority 證明**——這是加總不同層級證據強度所產生的邏輯謬誤，本專案自第一個 run 起即警示此點。

**Claim-Safe Taxonomy**：整體 HIJ-PROPER 結果 = 陳述「未達統計顯著」，不套用任何正面標籤；次族群
訊號 = `SUBGROUP/HYPOTHESIS-GENERATING`；RACING = `NONINFERIORITY`（但 `INDIRECT EVIDENCE`，
非 pitavastatin）。

---

## B. Indirect-evidence conflation risk（PI 焦點 5-2）

**攻擊**：本專案援引的多項證據，其研究對象**並非** pitavastatin/ezetimibe FDC 本身：

| 證據 | 實際研究對象 | 常見誤用方式 | 正確標籤 |
|---|---|---|---|
| RACING | Rosuvastatin 10mg + ezetimibe 10mg | 誤引為「pitavastatin+ezetimibe 之 CV outcome 證據」 | `INDIRECT EVIDENCE` |
| REPRIEVE | Pitavastatin 單方 vs 安慰劑，HIV 族群 | 誤引為「pitavastatin+ezetimibe FDC 之證據」 | `INDIRECT EVIDENCE`（pitavastatin 專屬但非 FDC） |
| REAL-CAD | Pitavastatin 劑量強度（4mg vs 1mg），無 ezetimibe | 誤引為 FDC 證據 | `INDIRECT EVIDENCE`（pitavastatin 專屬但非 FDC） |
| T-101（2026 ACC/AHA guideline） | Statin-agnostic，從未指名 pitavastatin | 誤引為「guideline 支持 pitavastatin FDC」 | `GUIDELINE/CONSENSUS`（statin-class 通用，非 FDC 專屬） |

**防禦**：這四者並非沒有價值——它們分別提供策略層級（RACING）、單方藥物層級（REPRIEVE/REAL-CAD）、
guideline 框架層級（T-101）的**間接**支持，共同構成一個合理的臨床論證鏈，但**鏈中沒有一環是 FDC
專屬的直接證據**，任何呈現都必須讓讀者清楚看到這個區別，而非以連續引用的方式製造「證據充分」的
錯覺。這是本專案自 2026-08-31-v1 起最高風險的過度延伸點，本 run 再次確認並延續此紀律。

---

## C. Maximize-statin-first 反方立場（PI 焦點 5-3）

**攻擊**：「先把 statin 劑量推到最大，而非急於加用 ezetimibe」是合理、且**有直接 pitavastatin
專屬證據支持**的立場——**這不是需要辯駁的過時觀點，而是目前證據等級上，其實比 FDC 本身更完整的
路徑**：

- **REAL-CAD**（前一 run TE-012）：pitavastatin 4mg vs 1mg，HR 0.81（95% CI 0.69–0.95, P=0.01），
  日本次級預防 CAD 族群，**達統計顯著**。這是 pitavastatin 單方劑量強化策略的正向 hard-outcome
  RCT，其證據完整度**優於** pitavastatin+ezetimibe FDC 目前僅達次族群層級的 Level 3 證據。
- **T-101（2026 ACC/AHA guideline）本身即以「statin 優先、maximally tolerated 後才加藥」為其
  Class 1 建議結構**（見 `00_executive-synthesis.md` 第 3 節）——這不只是歷史慣性，而是現行、
  已驗證之最大型美國 guideline 的正式立場。

**誠實結論**：辯論的正確框架不是「guideline 已經走向 combination-first，maximize-statin-first 已
過時」——這個前提**不成立**，至少對美國現行最大型 guideline 而言。真正誠實、可防禦的問題是：「當
病人可耐受劑量提升、尚未達到高劑量上限時，pitavastatin/ezetimibe FDC 是否能在**不犧牲有意義 LDL-C
降幅**的前提下，讓病人更快、更舒適地從 statin 最大化過渡到合併治療」——FDC 的優勢主要在於 Level 1
（LDL-C 降幅更大）與耐受性/依從性（RACING 提供之間接 strategy-level 證據），**而非**「FDC 本身已
證實比最大化劑量更能降低 CV event」這個更強、目前無直接證據支持的論斷。

**Claim-Safe Taxonomy**：REAL-CAD = `SUPERIORITY`（達統計顯著，但範圍限定於 pitavastatin 單方劑量
強度問題，非 FDC 問題）；FDC vs 最大化劑量之直接比較 = `EXPERT INFERENCE`（無直接資料，簡報中必須
明確揭露此為專家推論）。

---

## D. Diabetes/DDI claim limits（PI 焦點 5-4）

### D.1 血糖側寫論述的誠實極限

- Singh 2024 SRMA 之 RR 0.86（vs atorvastatin）/0.77（vs rosuvastatin）是**相對風險**，不是
  「pitavastatin 對血糖無影響」的證據——若簡報省略「相較於……」的比較對象，即構成過度延伸。
- **CAPITAIN（pitavastatin 4mg 高劑量）本身仍觀察到 FPG 微升 +4%（p<0.05）**——高劑量下並非完全
  零血糖影響，臨床意義輕微但**不應否認**此點；對手質疑「pitavastatin 也不是完全無害」是站得住腳
  的反駁，誠實回應是承認，而非否認。
- 目前沒有一篇 pitavastatin 專屬的頭對頭 dose-ranging RCT（同一試驗內比較 1mg/2mg/4mg 血糖終點）
  ——dose-response 論述是跨試驗拼接，方法學上弱於真正的 dose-ranging 設計。

**校準語言（不變）**：「pitavastatin 相對其他常用高效能 statin，可能有較有利的血糖側寫」——**絕不**
寫成「does not cause diabetes」或「pitavastatin 是糖尿病病人的安全首選」。

### D.2 DDI 論述的誠實極限

- FDA label 之 DDI 數字反映**已知、已測試**的交互作用——**不代表所有可能交互作用皆已排除**。
  Clarithromycin 未見於 label 不等於「無交互作用」，只是「label 未特別處理」。
- **核心區隔（最容易被對手抓住的落差）**：OATP1B1 為 pitavastatin 之主要清除機轉，CYP3A4 為次要——
  這使 pitavastatin 相對於 atorvastatin/simvastatin（CYP3A4 高度依賴）有優勢，**但對同樣走
  OATP1B1 路徑的交互作用（cyclosporine、gemfibrozil），pitavastatin 並未因「低 CYP3A4 依賴」而
  豁免**——cyclosporine 禁忌併用、gemfibrozil 建議避免，此二者風險依然存在。

**校準語言（不變）**：「pitavastatin 對 CYP3A4 依賴性低，降低與 CYP3A4 抑制劑的交互作用風險；但
透過 OATP1B1 之交互作用仍存在，尤其 cyclosporine（禁忌）與 gemfibrozil（避免併用）」——**絕不**
簡化為「DDI 少」或「no DDI」。

---

## E. Cost/adherence-realistic counter-view（PI 焦點 5-5）

- FDC 之依從性優勢（Katzmann 2022、Samnaliev 2025、Wei 2023 SRMA）建立在「病人已經願意且能夠取得
  該 FDC 處方」的前提上——若健保/自費成本使病人無法穩定取得 FDC，此優勢可能被「病人負擔不起而中斷
  治療」的風險抵銷。**本 run 未查證台灣健保對 pitavastatin/ezetimibe FDC 之給付與自付額資訊**——
  這是尚待補充的在地化資訊缺口。
- **Katzmann 2022 本身沒有依從性的直接測量資料**——FDC 優於 SPC 的 LDL-C 降幅差異是透過「合理推測
  依從性改善為可能解釋」，而非直接證實的因果機轉。這是攻防時最直接可預期的反駁點，誠實回應應承認
  此為推論鏈，非直接證據。
- **Samnaliev 2025 之整體世代並未觀察到 persistence/adherence 與 MACE 之顯著關聯**（僅 R10/E10
  劑量次族群觀察到 HR 0.58）——此矛盾必須主動揭露，否則若對手發現整體結果與次族群結果不一致，會
  嚴重損害整體論述的可信度。

**建議防禦語言**：「FDC 之依從性優勢在多篇觀察性研究中一致觀察到，但直接量測依從性的資料有限，
因果機轉仍是合理推論而非直接證實；成本/給付因素可能影響此優勢在真實世界的實現程度」。

---

## F. 何時 PCSK9-targeting therapy、bempedoic acid、或 inclisiran 更適當（PI 焦點 5-6）

### F.1 Hard-outcome 證據狀態總表（trials-efficacy 驗證）

| 藥物類別 | 主要 hard-outcome trial | 證據狀態 | Claim-Safe Tag |
|---|---|---|---|
| Bempedoic acid | CLEAR-Outcomes（Nissen 2023, NEJM, DOI 10.1056/NEJMoa2215024） | 已完成、已發表之正向 CV outcome RCT（statin-intolerant 高風險族群） | `SUPERIORITY`（於其設計族群內） |
| PCSK9i（evolocumab） | FOURIER（NEJM 2017, DOI 10.1056/NEJMoa1615664） | 已完成、已發表之正向 CV outcome RCT | `SUPERIORITY` |
| PCSK9i（alirocumab） | ODYSSEY OUTCOMES（NEJM 2018, DOI 10.1056/NEJMoa1801174） | 已完成、已發表之正向 CV outcome RCT（post-ACS） | `SUPERIORITY` |
| **Inclisiran** | VICTORION-2 Prevent、ORION-4（皆僅設計/protocol 論文） | **⚠ 本 run 檢索範圍內未找到任何已完成、已發表的 hard-outcome 結果論文** | `LDL-C SURROGATE EFFICACY`（僅此）；hard-outcome 層級 = `INSUFFICIENT EVIDENCE` |

**重要不對稱性（誠實呈現，不可忽略）**：「與其用 pitavastatin+ezetimibe FDC（Level 3 證據薄弱），
不如直接用 hard-outcome-proven 的新藥」這個論點，對 bempedoic acid 與 PCSK9-targeting therapy
**站得住腳**（兩者證據等級優於 FDC 目前僅達次族群層級的 Level 3 證據）；但對 **inclisiran
目前站不住腳**——inclisiran 本身也還沒有已發表的 hard-outcome 證據。任何「hard-outcome-proven
替代方案」框架若涵蓋 inclisiran 而未加註限制，即犯下與本專案核心紀律相同性質的過度延伸錯誤。

### F.2 何時安全性/耐受性理由（非純效果理由）更支持替代方案（safety-pharmacology 貢獻）

1. **完全確立之 statin intolerance**（NLA 2022/EAS 2015 標準）：pitavastatin/ezetimibe FDC 仍含
   statin 成分，理論上仍可能誘發相同機轉之肌肉副作用。此時 ezetimibe 單方+bempedoic acid（非
   statin 機轉）或 PCSK9-targeting therapy 在藥理機轉上是更保守的選擇。`MECHANISTIC SUPPORT` /
   `EXPERT INFERENCE`。**T-101 guideline 層級部分佐證**（safety-pharmacology 已獨立逐字核對第
   2011–2022 行）：PCSK9 mAb/inclisiran 被描述為「well tolerated and safe」，bempedoic acid
   明確定位於「statin-attributed side effects」病人——此為 `GUIDELINE/CONSENSUS` 層級對**耐受性/
   適應症定位**之直接陳述，但 guideline 原文**未涉及 DDI/OATP1B1/CYP3A4 機轉層級比較**，該部分
   仍為 `EXPERT INFERENCE`，兩者不可混淆。
2. **已知 OATP1B1 相關高風險多重用藥**（cyclosporine 器官移植後、gemfibrozil 合併用藥）：即使
   pitavastatin CYP3A4 依賴性低，OATP1B1 路徑風險依然存在——PCSK9 mAb/inclisiran（非肝臟
   transporter/CYP 依賴機轉）在 DDI 風險上更具優勢。`MECHANISTIC SUPPORT` / `EXPERT INFERENCE`
   （本 run 未獨立查證 PCSK9/inclisiran 之 DDI 原始文獻，需標示為推論層級）。
3. **進行中透析之 ESRD/HD 病人**：pitavastatin 單方 ESRD/HD 劑量指引明確（1mg/2mg 上限），但
   **FDC 於此族群之專屬安全性資料完全缺乏**。PCSK9-targeting therapy（蛋白質分解代謝路徑，非腎臟/
   OATP 依賴）在「未知風險」角度上可能是更保守選項——**惟此為 `EXPERT INFERENCE`，非直接比較試驗
   證實**，簡報應標示為「資料缺口下的保守選項」而非「已證實更安全」。

---

## G. 章節間交叉檢核（Director Wave 3 內部一致性確認）

- A、B、C、F.1 四節之 evidence-hierarchy/claim-safe 標籤已交叉核對，無矛盾。
- D、F.2 之「校準語言」與 `00_executive-synthesis.md` 第 8 節完全一致，未在不同文件間出現不同
  措辭版本。
- Attack B 的表格與 `00_executive-synthesis.md` 第 0 節「兩個必須貫穿全文的紀律」互為呼應，非
  重複但獨立撰寫的兩套規則——避免未來編修時兩處各自漂移。
