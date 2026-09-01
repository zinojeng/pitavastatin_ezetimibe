# attack-defense-contribution — safety-pharmacology 領域貢獻（Focus Area 5）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-09-01-v1`
Owner: safety-pharmacology-intelligence（貢獻本角色領域部分；Director 整合全部三角色貢獻至
Challenge Round 與最終 attack/defense 段落）

本文件是「誠實地攻擊自己立場」的練習——目的是讓最終簡報/文件經得起質疑，而非單方面替
pitavastatin/ezetimibe FDC 辯護。標記規則同 `positioning-brief.md`（Evidence Hierarchy +
Claim-Safe Taxonomy）。

---

## 1. 糖尿病/DDI 論述的誠實極限（Diabetes/DDI Claim Limits）

### 1.1 血糖側寫論述可能被過度延伸之處

- Singh 2024 SRMA 之 RR 0.86/0.77 是「相較其他 statin 的相對風險」，**不是**「pitavastatin 對血糖
  無影響」的證據——13 篇納入研究中仍有部分顯示 pitavastatin 並非完全血糖中性，只是相對優勢。若
  簡報將此簡化為「pitavastatin 血糖安全」而省略「相較於……」的比較對象，即構成過度延伸。
- CAPITAIN（pitavastatin 4mg 高劑量）本身仍觀察到 FPG 微升 +4%（p<0.05）——**高劑量下並非
  完全零血糖影響**，只是臨床意義輕微。攻防時若對方引用此點質疑「pitavastatin 也不是完全無害」，
  這是**站得住腳的反駁**，我方誠實的回應應是承認此點，而非否認。
- 目前**沒有一篇 pitavastatin 專屬的頭對頭 dose-ranging RCT**（1mg vs 2mg vs 4mg 同一試驗內比較
  血糖終點）——dose-response 論述是跨試驗拼接，方法學上弱於真正的 dose-ranging 設計，此限制應
  在簡報中明確揭露，而非隱藏。
- Li 2026（elderly, T2DM population NODM 0% vs 10.29%）樣本數僅 126 人、單中心、非隨機、劑量
  非對等（pitavastatin 4mg 為其最高劑量 vs atorvastatin 20mg 為中等劑量）——**不是可獨立支撐
  結論的證據，只能作為輔助訊號**。

**建議防禦語言**：「pitavastatin 相對其他常用高效能 statin，可能有較有利的血糖側寫」，並附上
比較對象與證據等級（觀察性/統合分析為主，非大型頭對頭 RCT）——**不可**寫成「pitavastatin 是
糖尿病病人的安全首選」或任何暗示已被 RCT 證實安全性優越的語言。

### 1.2 DDI 論述可能被過度延伸之處

- FDA label 之 DDI 數字（cyclosporine 4.6倍、erythromycin 2.8倍等）反映的是**已知、已測試**的
  交互作用——**不代表所有可能交互作用都已排除**。Clarithromycin 未見於 label 不等於「無交互
  作用」，只是「label 未特別處理」，本專案已多次強調此區隔，攻防時若對方以「你們自己都說有些
  藥物沒測過」質疑完整性，這是合理質疑，應誠實承認 label 覆蓋範圍有限，而非宣稱「已測試所有
  常見交互作用」。
- OATP1B1 為主要機轉、CYP3A4 為次要機轉——這使 pitavastatin 相對於 atorvastatin/simvastatin
  （CYP3A4 高度依賴）有優勢，但對於**同樣走 OATP1B1 路徑**的交互作用（如 cyclosporine、
  gemfibrozil），pitavastatin **並未**因為「低 CYP3A4 依賴」而豁免——這是「low CYP3A4-dependent
  liability」與「low DDI liability 全面」之間最容易被誤解、也最容易被對手抓住的落差。
  **這正是本專案語言校準規則存在的原因，須在簡報中明確區分機轉，而非籠統宣稱「DDI 少」。**

**建議防禦語言**：「pitavastatin 對 CYP3A4 依賴性低，降低與 CYP3A4 抑制劑（如某些鈣離子通道
阻斷劑、部分抗心律不整藥物）的交互作用風險；但透過 OATP1B1 之交互作用仍存在，尤其
cyclosporine（禁忌）與 gemfibrozil（避免併用），臨床仍須個別評估」。

---

## 2. 何時 Pitavastatin/Ezetimibe FDC *不是*較佳選擇——安全性/耐受性角度（非單純 efficacy 角度）

Focus Area 5 明確要求：「when PCSK9-targeting therapy, bempedoic acid, or inclisiran is the more
defensible choice instead — on tolerability/DDI grounds specifically, not just efficacy grounds」。
本節專注於**安全性/耐受性理由**，效果量比較留給 trials-efficacy。

### 2.1 Statin 完全不耐受（Complete Statin Intolerance）

若病人已符合正式 statin intolerance 標準（NLA 2022 / EAS 2015 定義，見 `2026-08-31-v1` 之
evidence-map.md §4.3——CK 顯著升高、rechallenge 後症狀復發），則 pitavastatin/ezetimibe FDC
**仍含有 statin 成分**，理論上仍可能誘發相同機轉之肌肉副作用——即使 pitavastatin 之肌肉安全性
側寫相對較佳，也不能保證對已確立 statin intolerance 之病人安全。此時 **ezetimibe 單方 +
bempedoic acid（非 statin 機轉）或 PCSK9-targeting therapy** 在藥理機轉上是更誠實、更保守的
選擇——這與 Taiwan STS 2026 共識對 extremely-high-risk 病人「及早合併治療（ezetimibe +
bempedoic acid）」之演算法一致（見 guideline-risk 領域，此處僅從安全性角度呼應）。
**Evidence Hierarchy: MECHANISTIC SUPPORT**（機轉推論）。**Claim-Safe Taxonomy: `EXPERT
INFERENCE`**。

### 2.1b 更新（本輪新增）：T-101 guideline 文字部分佐證 PCSK9/inclisiran/bempedoic acid 之耐受性定位

guideline-risk 於本輪驗證 T-101（2026 ACC/AHA guideline, DOI 10.1161/CIR.0000000000001423）為
VERIFIED 來源後，本角色已獨立對照原始 `.md` 全文核對以下段落（第 2011–2022 行，Section 4.2.1.1
Statins Synopsis / 4.2.1.2 Nonstatin LDL-C–Lowering Medications）：

> "Ezetimibe lowers LDL-C levels by a mean of 18% (25% incremental reduction when added to statin
> therapy) and has a low incidence of side effects... PCSK9 monoclonal antibodies (mAbs) can lower
> LDL-C by 45% to 64%, are well tolerated and safe... Inclisiran, a small-interfering ribonucleic
> acid (RNA)-based PCSK9i, lowers LDL-C by 48% to 52%, and is well tolerated... Bempedoic acid, an
> adenosine triphosphate citrate lyase inhibitor, lowers LDL-C by 21% to 24% as monotherapy **in
> patients with statin-attributed side effects**, and by an additional 17% to 18% in combination
> [with ezetimibe]."

此段落**部分**上修了下方 §2.2/§2.3 原先標記為 `EXPERT INFERENCE` 的推論——guideline 原文明確將
bempedoic acid 定位於「statin-attributed side effects 病人」情境，且將 PCSK9 mAb/inclisiran
描述為「well tolerated and safe」，這是**guideline 層級對耐受性的直接陳述**，非本角色自行推論。
**Evidence Hierarchy: GUIDELINE/CONSENSUS**（升級，原為 MECHANISTIC SUPPORT/EXPERT
INFERENCE）。**Claim-Safe Taxonomy: `GUIDELINE/CONSENSUS`**。

**惟仍須誠實揭露之限制**：guideline 原文**未具體提及 DDI/OATP1B1/CYP3A4 機轉層面的比較**，僅是
一般耐受性/LDL-C 降幅陳述，**不能**直接當作「PCSK9/inclisiran 於 OATP1B1 相關多重用藥情境下
DDI 風險更低」之直接證據——下方 §2.2（OATP1B1 相關多重用藥）與 §2.3（ESRD/HD）之 DDI 機轉論述
**仍維持 `EXPERT INFERENCE`**，本次更新僅上修「耐受性/statin-side-effect 適應症定位」部分，
兩者不可混淆。

### 2.2 已知 OATP1B1 相關高風險多重用藥（非 CYP3A4）

若病人正在使用 cyclosporine（器官移植後）或需要 gemfibrozil（嚴重高三酸甘油酯血症合併用藥）——
即使 pitavastatin 之 CYP3A4 依賴性低，**OATP1B1 途徑之交互作用風險依然存在且顯著**（cyclosporine
禁忌併用、gemfibrozil 建議避免）。此類病人若仍需要 statin 類藥物之外的降 LDL-C 選項，**PCSK9單株
抗體或 inclisiran（非肝臟 transporter/CYP 依賴之作用機轉）在 DDI 風險上明確更具優勢**——這是
「DDI grounds specifically」最直接的例子，不涉及療效比較，純粹是交互作用機轉的差異。
**Evidence Hierarchy: MECHANISTIC SUPPORT**（基於已知 PCSK9 單株抗體/siRNA 藥物之非肝臟代謝
機轉——**本輪未獨立查證 PCSK9 製劑/inclisiran 之 DDI 資料原始文獻**，此為 EXPERT INFERENCE 層級
之機轉推論，非直接引用查證後的 PCSK9/inclisiran DDI 研究，如需正式寫入 manuscript 應請 Director
指派或本角色下一輪補查）。**Claim-Safe Taxonomy: `EXPERT INFERENCE`**。

### 2.3 進行中透析之終末期腎病（ESRD/HD）病人

FDA label 雖對 pitavastatin 於 ESRD/HD 病人給出明確劑量（1mg/2mg 上限），但**該劑量指引僅涵蓋
pitavastatin 單方，FDC（pitavastatin+ezetimibe）於此族群之專屬安全性資料完全缺乏**（見
`positioning-brief.md` §1.2 及 `2026-08-31-v1` 之 unresolved-questions.md，此缺口本輪仍未解決）。
在缺乏 FDC 專屬 ESRD 資料的情況下，若臨床上有其他機轉更不依賴腎臟/肝臟 transporter 之選項可用
（如 PCSK9-targeting therapy，其代謝機轉主要為蛋白質分解代謝路徑，非腎臟/OATP 依賴），
**在「未知風險」角度上可能是更保守、更能說明的選擇**——惟此為 EXPERT INFERENCE，非直接比較
試驗證實，簡報時應誠實標示為「在資料缺口下的保守選項」而非「已證實更安全」。**Evidence
Hierarchy: INSUFFICIENT EVIDENCE**（FDC 於 ESRD 之直接資料缺口）+ **MECHANISTIC SUPPORT**
（PCSK9 替代機轉之理論優勢）。**Claim-Safe Taxonomy: `EXPERT INFERENCE`**。

---

## 3. 成本/依從性務實觀點（Cost/Adherence-Realistic Counter-View）

- FDC 之依從性優勢（Katzmann 2022、Samnaliev 2025、Wei 2023 SRMA）**建立在病人已經願意且能夠
  取得該 FDC 處方的前提上**——若健保/自費成本使病人無法穩定取得 FDC（相對於個別學名藥 statin
  + ezetimibe 分開處方，通常更便宜），則「FDC 提升依從性」的優勢在現實中可能被「病人負擔不起
  FDC 而中斷治療」的風險抵銷。**本輪未查證台灣健保對 pitavastatin/ezetimibe FDC 之給付與自付
  額資訊**——這是 guideline-risk 或 Director 層級之台灣在地化資訊缺口，非本角色可從國際文獻
  文獻搜尋補足，建議列入 `04_OPEN-QUESTIONS.md`。
- Katzmann 2022 本身之研究限制（原文明確指出）：**該研究沒有服藥遵從性的直接測量資料**，FDC
  優於 SPC 的 LDL-C 降幅差異是透過「合理推測依從性改善為可能解釋」而非直接證實的因果機轉——
  這是攻防時最直接可預期的反駁點：「你們用 LDL-C 降幅差異去推論依從性改善，但你們自己的來源
  承認沒有量測依從性」。誠實回應應承認此為推論鏈，非直接證據。
- Samnaliev 2025 之整體世代並未觀察到 persistence/adherence 與 MACE 之顯著關聯（僅 R10/E10
  劑量次族群觀察到），此矛盾**必須主動揭露**，否則若對手發現整體結果與次族群結果不一致，會
  嚴重損害整體論述的可信度。

**建議防禦語言**：「FDC 之依從性優勢在多篇觀察性研究中一致觀察到（處方數減少、LDL-C 降幅增加），
但直接量測依從性的資料有限，因果機轉（依從性改善 → LDL-C 降幅增加）仍是合理推論而非直接證實；
成本/給付因素可能影響此優勢在真實世界的實現程度，此為台灣在地化定位待補充之資訊」。

---

## 4. 本節與 Director Challenge Round 的銜接

本文件之三大攻擊點（1. 血糖/DDI 論述極限、2. 何時 FDC 非最佳選擇、3. 成本/依從性務實觀點）
建議由 Director 於 Wave 3 Challenge Round 中與 guideline-risk（STS/guideline 角度）、
trials-efficacy（efficacy/療效角度之攻擊點，如 REPRIEVE/REAL-CAD 之產品混淆風險、HIJ-PROPER
非優越性主要終點）整合，形成完整的 attack/defense 段落。本角色不擅自撰寫整合版本，僅提供領域
內容。
