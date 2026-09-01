# positioning-brief — Pitavastatin/Ezetimibe FDC 之可防禦臨床定位（Focus Area 4）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Owner: safety-pharmacology-intelligence（primary，focus area 4；trials-efficacy 負責 efficacy delta
部分）

## 標記規則（本輪新增，Focus Area 6）

每個論斷同時標示兩套標籤：
1. **Evidence Hierarchy**（`CLAUDE.md` §7）：DIRECT EVIDENCE | INDIRECT EVIDENCE | GUIDELINE/
   CONSENSUS | OBSERVATIONAL EVIDENCE | MECHANISTIC SUPPORT | INSTITUTIONAL PRACTICE | EXPERT
   INTERPRETATION | INSUFFICIENT EVIDENCE
2. **Claim-Safe Taxonomy**（本輪新增）：`SUPERIORITY` | `NONINFERIORITY` | `LDL-C SURROGATE
   EFFICACY` | `OBSERVATIONAL SIGNAL` | `SUBGROUP/HYPOTHESIS-GENERATING` | `GUIDELINE/CONSENSUS` |
   `EXPERT INFERENCE`

本文件建立在 `2026-08-31-v1/20_EVIDENCE/safety-pharmacology/{evidence-map.md, ddi-matrix.md}`
（已通過 Wave 4 獨立稽核，Final Gate PASS_WITH_MINOR_ISSUES）之上，**不重新推導**，僅：(a) 補上
claim-safe 標籤，(b) 標註本輪新查得之補充資料，(c) 組織成「vs. 三個比較對象」的定位論述結構。

---

## 1. Pitavastatin/Ezetimibe FDC vs. Pitavastatin 單方

### 1.1 Efficacy（LDL-C，主要屬 trials-efficacy 領域，此處僅作定位論述之必要背景）

Chou MT et al. 2022（1PC111，台灣/澳洲/紐西蘭）：pitavastatin 2mg/ezetimibe 10mg 於 wk12 LDL-C
降幅 −50.5% vs pitavastatin 2mg 單方 −36.11%（p<0.001）。
**Evidence Hierarchy: DIRECT EVIDENCE**（pitavastatin/ezetimibe FDC 專屬試驗）。
**Claim-Safe Taxonomy: `LDL-C SURROGATE EFFICACY`**（非硬指標優越性，是替代指標之統計顯著差異）。

K-924（Tsujita 2023，日本，**DOI 本輪新確認：10.5551/jat.64006**）：pitavastatin 2mg+eze10mg
（K-924 LD）LDL-C −51.4% vs pitavastatin **4mg 單方** −45.2%——**這是「加 ezetimibe 優於劑量加倍」
最直接的頭對頭數字**，惟為不同產品/族群（日本 Kowa 產品，非 Taiwan/Australia/NZ 之 1PC111）。
**Evidence Hierarchy: DIRECT EVIDENCE**（對 K-924 本身）/ **INDIRECT EVIDENCE**（對
pitavastatin/ezetimibe FDC 一般化定位而言）。**Claim-Safe Taxonomy: `LDL-C SURROGATE EFFICACY`**。

### 1.2 安全性/耐受性定位（本角色主責）

- **CKD 劑量調整**：pitavastatin 單方於中重度 CKD（eGFR 15–59）或洗腎病人之劑量上限為 FDA label
  明定的 1mg 起始/2mg 上限——**所有已列表 statin 中最低上限**（`2026-08-31-v1` Tramontano 2025
  review table 交叉比對 FDA label 確認）。此為單方劑量資料，FDC 本身之 CKD 專屬劑量調整**仍未有
  任何來源涵蓋**（`2026-08-31-v1/20_EVIDENCE/safety-pharmacology/unresolved-questions.md` 已記錄
  BLOCKED_FOR_SOURCE，本輪未發現新資料可解決此缺口，維持原狀）。
  **Evidence Hierarchy: DIRECT EVIDENCE**（label，僅涵蓋單方）。**Claim-Safe Taxonomy:
  `EXPERT INFERENCE`**（「FDC 應可比照單方 statin 成分之 CKD 劑量指引」為合理推論，非直接證實）。
- **K-924 12 週+52 週資料**顯示 pitavastatin 2mg+eze10mg（K-924 LD）之 CK/肝功能異常事件發生率
  與 pitavastatin 單方組相近或更低（見 `2026-08-31-v1` ddi-matrix.md 完整表格），**惟樣本數小
  （n=72/arm，12 週），且非 CKD/elderly 次族群分析**。**Evidence Hierarchy: DIRECT EVIDENCE**
  （K-924 本身）/ **INDIRECT EVIDENCE**（外推至 pitavastatin/ezetimibe FDC 一般結論）。
  **Claim-Safe Taxonomy: `OBSERVATIONAL SIGNAL`**（樣本數不足以做正式安全性優越性推論，僅為
  descriptive comparison，非統計檢定之結論）。
- **本輪新查得候選資料（UNVERIFIED，僅取得標題/DOI，未取得摘要內容）**：「Optimizing LDL-C
  Reduction: High-Dose Pitavastatin Vs. Combination Therapy With Ezetimibe In Type II Diabetes」
  （*African Journal of Biomedical Research*, DOI 10.53555/ajbr.v27i4s.7096, 2024）——標題顯示為
  T2DM 族群、pitavastatin 高劑量單方 vs +ezetimibe 之比較，若驗證屬實將直接補強本節（血糖+FDC
  positioning 雙重相關）。**本輪未能取得摘要內容**（來源網站回傳 403，doi.org 重導向後之出版社
  頁面無法存取）——**不得引用其中任何數字**，僅記錄為候選來源，交下一輪或 Director 決定是否值得
  進一步追蹤（期刊知名度較低，需額外查證其編輯/同儕審查品質後再決定投入程度）。
  **Evidence Hierarchy: INSUFFICIENT EVIDENCE**（尚無可查證內容）。

### 1.3 定位論述（本角色綜合，非單一來源）

> Pitavastatin/ezetimibe FDC 相較 pitavastatin 單方之核心論點，不在於「取代」單方治療，而在於：
> 對於 pitavastatin 2mg（甚至考慮加量至 4mg）仍未達 LDL-C 目標的病人，加 ezetimibe 10mg 之額外
> LDL-C 降幅（K-924 頭對頭數字：加 eze 優於劑量加倍），配合 pitavastatin 本身已知的
> low-CYP3A4-dependent interaction liability 與相對有利的血糖側寫（見第 3 節），構成一個在
> **efficacy、tolerability、與 polypharmacy 風險之間**取得平衡的加藥選項，而非單純「藥效更強」
> 的行銷主張。**Claim-Safe Taxonomy: `EXPERT INFERENCE`**（本段為本角色之綜合定位論述，非單一
> 研究之直接結論，寫作/簡報時應維持此層級之謹慎用語，不可包裝成「已證實」的結論）。

---

## 2. Pitavastatin/Ezetimibe FDC vs. 高劑量/高強度 Statin 單方

### 2.1 策略層級證據（RACING，trials-efficacy 主責，此處僅為安全/耐受性面向之延伸）

RACING（rosuvastatin 10mg+eze10mg vs 高強度 statin 單方）之 intolerance-related
discontinuation/dose reduction：4.8% vs 8.2%（overall）；DM 次族群 5.2% vs 8.7%——**此為 statin 類別
一般化的「中強度+eze 優於高強度單方」耐受性訊號，非 pitavastatin 專屬**，沿用
`2026-08-31-v1/CLAUDE.md` §7 對 RACING 之既定處理原則（INDIRECT EVIDENCE，不得當作
pitavastatin/ezetimibe 專屬證據引用）。**Evidence Hierarchy: INDIRECT EVIDENCE**。
**Claim-Safe Taxonomy: `NONINFERIORITY`**（RACING 原始設計即為 non-inferiority trial，MACE
9.1% vs 9.9%）。

### 2.2 Pitavastatin 專屬之耐受性論據（本角色主責，此為本節真正新增價值）

高強度 statin（atorvastatin/rosuvastatin 高劑量）之已知耐受性代價——肌肉相關 AE、NODM 風險
（相對 pitavastatin 較高，見第 3 節）——若病人本身已有 DM/prediabetes、CKD、或高齡多重用藥情境，
高劑量單方 statin 之邊際耐受性成本可能高於「中劑量 pitavastatin + ezetimibe」策略。此論點目前
**缺乏 pitavastatin/ezetimibe FDC 專屬之頭對頭高強度 statin 比較試驗**——本輪搜尋未發現此類直接
比較（僅有 RACING 之 rosuvastatin 版本，及 K-924 之 pitavastatin 內部劑量比較，皆非
「pitavastatin+eze vs. atorvastatin/rosuvastatin 高強度單方」之直接對照）。**此為本節定位論述
最大的直接證據缺口，應誠實揭露，不可用 RACING 或 K-924 間接填補成看似直接的比較**。
**Evidence Hierarchy: INSUFFICIENT EVIDENCE**（缺乏直接比較試驗）。**Claim-Safe Taxonomy:
`EXPERT INFERENCE`**（基於個別已知耐受性/血糖特性之合理推論，非試驗證實的定位）。

---

## 3. Pitavastatin/Ezetimibe FDC vs. 其他 Non-statin Add-on（bempedoic acid、PCSK9-targeting、
inclisiran）

此節為 Focus Area 5（attack/defense）之核心貢獻部分，獨立成 `attack-defense-contribution.md`，
本文件僅列出與定位直接相關之摘要交叉引用：見該檔案第 2 節「何時 pitavastatin/ezetimibe FDC
*不是*較佳選擇」。

---

## 4. 三大安全/藥理定位支柱（本角色核心 Evidence Base，carry-forward + 本輪確認無新變化）

### 4.1 血糖側寫（Glycemic Profile）

沿用 `2026-08-31-v1` 完整證據（Singh 2024 SRMA：RR 0.86 vs atorvastatin, RR 0.77 vs rosuvastatin；
Seo 2022 real-world cohort HR 0.72；PAPAGO-T 台灣 RCT；CAPITAIN 高劑量資料等，完整列表見該 run 的
`evidence-map.md` §1）。**本輪未發現任何新的、更新的、或矛盾的血糖相關文獻**（僅 1 天時間差，
且本輪工具連線限制下之輕量搜尋未觸及新文獻；不排除仍有遺漏，非窮盡式搜尋）。

**校準語言強制規則（不變）**：「pitavastatin may have a more favorable glycemic profile than some
other potent statins」——**絕不**寫成「does not cause diabetes」。
**Claim-Safe Taxonomy（新增標籤，套用至既有證據）**：Singh 2024 SRMA 結果 = `OBSERVATIONAL
SIGNAL`（pooled RCT+observational，非純 RCT superiority claim）；Seo 2022 = `OBSERVATIONAL
SIGNAL`；PAPAGO-T HbA1c 次族群顯著性 = `SUBGROUP/HYPOTHESIS-GENERATING`（DM 次族群 n=125，非
主要設計終點）；CAPITAIN 高劑量中性結果 = `OBSERVATIONAL SIGNAL`（非對照組優越性宣稱）。

### 4.2 低 CYP3A4-dependent Interaction Liability

沿用 `2026-08-31-v1` 完整 DDI matrix（FDA label 直接引用：cyclosporine 禁忌、erythromycin/
rifampin 劑量上限、gemfibrozil 避免併用、fenofibrate 無限制；OATP1B1 為主要機轉；clarithromycin
confirmed absent from label）。**本輪未發現新的 pitavastatin DDI 資料**。

**校準語言強制規則（不變）**：「low CYP3A4-dependent interaction liability」——**絕不**寫成
「no DDI」。**Claim-Safe Taxonomy**：FDA label 之定量交互作用數字 = `GUIDELINE/CONSENSUS`
（regulatory institutional practice，非臨床試驗優越性宣稱，但屬最高權威層級的機構性資料）；
Hong 2025 PBPK 模擬 BCRP-adjacent 數字 = `EXPERT INFERENCE`（模擬預測，非臨床實測）。

**臨床情境應用（老年+HTN+DM+CAD+CCB+抗血小板/抗凝血）**：見
`2026-08-31-v1/20_EVIDENCE/safety-pharmacology/ddi-matrix.md` 完整段落，本輪無新增。

### 4.3 老年/亞洲/台灣族群 + CKD

**本輪新增，來自 T-101（2026 ACC/AHA/…多學會 dyslipidemia guideline, *Circulation*.
2026;153:e1154–e1276, DOI 10.1161/CIR.0000000000001423，guideline-risk 已 VERIFIED）——本角色已
獨立對照原始 `.md` 全文逐字核對，非僅採信 guideline-risk 之轉述**：

> "Certain populations (especially East Asian ancestry) may be more prone to side effects due to
> inherited drug metabolism effects; thus, initial treatment should be with lower doses."
> — Section 4.2.1.1 Statins Synopsis（本角色直接於原始 `.md` 第 2015–2018 行核對，逐字相符）。

此為**現行美國 ACC/AHA guideline 自身**對東亞族群統計藥理遺傳學風險的明確陳述，直接支持本專案
「pitavastatin 於亞洲/台灣族群之定位」論述的上位 guideline 背景——惟需注意：此段落是 statin
類別的**一般性**陳述（"statins"，非 pitavastatin 專屬），且未具體點名 pitavastatin。
**Evidence Hierarchy: GUIDELINE/CONSENSUS**。**Claim-Safe Taxonomy: `GUIDELINE/CONSENSUS`**。
**不可**將此段落改寫成「guideline 建議東亞病人優先使用 pitavastatin」——guideline 原文僅建議
「較低劑量起始治療」，未指定特定 statin 品項；本專案既有之「pitavastatin 相對低劑量即可達
治療效果、且血糖/DDI 側寫相對有利」等既有證據，可作為**與此 guideline 一般性建議相容、但獨立**
的補充論點，兩者不可混為一談。

- **老年族群新證據**：Li H, Li J 2026（*Br J Hosp Med*）——中國回溯性世代，pitavastatin 4mg vs
  atorvastatin 20mg，≥60 歲 ASCVD 病人，NODM 0% vs 10.29%（OR 0.212, p=0.018）。**Evidence
  Hierarchy: OBSERVATIONAL EVIDENCE**（單中心回溯性，非隨機、劑量非對等）。**Claim-Safe
  Taxonomy: `OBSERVATIONAL SIGNAL`**。
- **台灣族群**：PAPAGO-T（唯一台灣 RCT，pitavastatin 2mg vs atorvastatin 10mg）；Huang CH 2016
  長庚回溯性研究；Lin YW 2024（台灣「三高」病人服藥遵從性先驅研究，25.8% 不遵從）。
- **CKD**：見上方第 1.2 節（pitavastatin 單方 CKD 劑量調整為所有 statin 中最保守，1mg/2mg 上限）。

### 4.4 耐受性與 FDC Adherence 優勢

沿用 `2026-08-31-v1` 完整證據：Katzmann 2022（FDC LDL-C 降幅 −28.4% vs SPC −19.4%, p<0.0001，
n=1,639/796）；Wei 2023 SRMA（跨疾病 FDC vs FEC adherence RR 1.29）；Samnaliev 2025
（rosuvastatin/ezetimibe FDC，persistence HR 0.54, adherence OR 3.00；R10/E10 次族群 MACE HR
0.58，惟與 overall cohort 之無顯著關聯結果不一致，撰寫時須揭露此矛盾）；Su M 2025（statin
adherence 與全因死亡率 aHR 0.68）。**本輪未發現新資料，亦未發現與既有結論矛盾之新證據。**
**Claim-Safe Taxonomy**：Katzmann 2022 LDL-C 差異 = `LDL-C SURROGATE EFFICACY`（p<0.0001 為
統計顯著，非硬指標）；Samnaliev persistence/adherence HR/OR = `OBSERVATIONAL SIGNAL`；Samnaliev
R10/E10 次族群 MACE HR 0.58 = `SUBGROUP/HYPOTHESIS-GENERATING`（與 overall cohort 結果不一致，
不可視為確認結論）。

---

## 5. 本輪與上輪差異總結（供 Director 整合用）

| 項目 | 上輪狀態 | 本輪新增/變化 |
|---|---|---|
| K-924 DOI | 未記錄 DOI（僅 PMID/PMCID） | **新增**：DOI 10.5551/jat.64006 確認 |
| 高劑量 pitavastatin vs +eze in T2DM | 未知此文獻存在 | **新發現候選來源**（AJBR 2024），**內容未驗證**，不得引用其數字 |
| Claim-Safe Taxonomy 標籤 | 不適用（上輪無此分類） | **本輪新增**，已套用至所有既有 Evidence Hierarchy 標籤之上 |
| 血糖/DDI/CKD/adherence 核心證據 | 已通過 Wave 4 獨立稽核 | **無變化**，本輪輕量搜尋未發現新文獻或矛盾證據 |
| Pitavastatin/eze FDC vs 高強度 statin 單方之直接比較 | 已知缺口（RACING 為間接證據） | **本輪確認此缺口依然存在**，無新試驗填補 |
