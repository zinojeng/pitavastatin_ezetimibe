# 05 血糖／安全性／藥物交互作用／腎功能（Glycemic / Safety / DDI / CKD）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Wave 3 Synthesis · 2026-08-31 · 主要來源：safety-pharmacology-intelligence

> 本節全程遵守 `CLAUDE.md` §5 的校準語言規則：血糖敘述禁用「does not cause diabetes」；DDI 敘述禁用
> 「no DDI」。

## 血糖安全性：訊號一致，但證據等級需要拆解

Pitavastatin 相較 atorvastatin/rosuvastatin 的 new-onset diabetes（NODM）風險訊號一致偏低：

- T-003（Singh et al. 2024，Expert Rev Clin Pharmacol，13 篇 RCT+observational 混合分析）：
  RR 0.86（95% CI 0.79–0.93，p=0.0002）vs atorvastatin；RR 0.77（95% CI 0.71–0.84，p<0.00001）
  vs rosuvastatin。
- T-017（Li H, Li J et al. 2026，老年族群 pitavastatin vs atorvastatin，n=126，摘要層級）：
  NODM 0% vs 10.29%。

**兩項限制必須同時陳述**：第一，T-003 全文 `BLOCKED_FOR_SOURCE`（Wave 2、Wave 3 兩輪確認，Europe
PMC 顯示無 OA、無 PMCID），**無法確認其 RR 是否在 RCT-only 與 observational-only 子集中一致**——這與
citation #26（Sydhom 2024）已發生過的 RCT/observational 混淆問題屬同一類型風險，本輪 Challenge Round
標記為尚未解決的平行風險，需在未來取得全文後重新檢視。第二，T-017 效應量（0% vs 10.29%）在僅有
n=126 的摘要層級資料中顯得偏大，本輪 Challenge Round 建議在全文驗證前不宜作為headline 論述。

**正確表述**：「pitavastatin 可能有較有利的血糖 profile」。**禁止表述**：「pitavastatin does not
cause diabetes」。

## 藥物交互作用（DDI）：低 CYP3A4 依賴性，而非「無交互作用」

FDA 藥品標籤（LIVALO/pitavastatin calcium，T-010，經 safety-pharmacology 兩輪直接比對 DailyMed 原文
確認）代謝敘述原文：「only minimal metabolism by the cytochrome P450 system... marginally
metabolized by CYP2C9 and to a lesser extent by CYP2C8」——**全文完全未提及 CYP3A4**，這是支持
「low CYP3A4-dependent interaction liability」表述的直接法規文件依據。

**已確認的臨床相關交互作用**（皆為 `INSTITUTIONAL PRACTICE` 層級，法規標籤數據）：

| 併用藥物 | 建議 | AUC 變化 | Cmax 變化 |
|---|---|---|---|
| Cyclosporine | **禁忌** | 4.6 倍↑ | 6.6 倍↑ |
| Erythromycin | 劑量上限 1mg/日 | 2.8 倍↑ | 3.6 倍↑ |
| Rifampin* | 劑量上限 2mg/日 | +29% | 2.0 倍↑ |
| Gemfibrozil | 避免併用 | +45% | +31% |
| Fenofibrate | 無特別限制 | +18% | +11% |
| Clarithromycin | 標籤中**確認未列出**（非「已確認無交互作用」） | — | — |

\* Rifampin 數據反映單次併用劑量，非慢性 CYP 誘導狀態下的劑量方案——標籤本身未涵蓋長期併用情境。

此外，標籤另收錄 fibrate 類（一般性）、niacin、colchicine 的注意事項（Wave 2 補充萃取）。機轉層級的
補充證據（T-019、T-020：一般性支持 OATP1B1 為主要轉運機轉；T-026：pitavastatin 與多重機轉合併干擾物
elexacaftor-tezacaftor-ivacaftor 併用時 AUC ratio 2.24，但此為多重機轉合併干擾物，非孤立 BCRP
抑制劑，不可作為 pitavastatin 專屬 BCRP fold-change 引用）皆為 PBPK 模擬或機轉性文獻，標記
`MECHANISTIC SUPPORT`，不等同臨床測量 DDI 數據。**Pitavastatin 專屬的孤立 BCRP 抑制劑定量
fold-change 數據，目前不存在於本專案已檢索之文獻中——此為真正的證據缺口，非檢索失敗。**

**正確表述**：「low CYP3A4-dependent interaction liability」。**禁止表述**：「no DDI」。應搭配實際
病例情境使用（如高齡 + 高血壓 + 糖尿病 + 冠心病 + CCB + 抗血小板/抗凝血藥物的多重用藥情境）。

## 腎功能不全（CKD）劑量：單方已明確，FDC 複方仍是缺口

T-018（Tramontano et al. 2025，Drugs 期刊回顧，全文取得並與 FDA 標籤交叉驗證）確認：pitavastatin
**單方**於 eGFR 15–59 或洗腎病人，建議劑量為 1mg 起始、2mg 上限；eGFR ≥60（輕度腎功能不全）無需
調整劑量。依該回顧自身的比較表，**pitavastatin 在七種 statin 中 CKD 劑量上限最低**——這是一項有利於
CKD 病人使用 pitavastatin 的正面訊號。

**但本專案在所有檢索範圍內，未發現任何文獻直接處理 pitavastatin+ezetimibe FDC 複方本身於 CKD 病人的
劑量調整問題**。safety-pharmacology 提出的合理推論——FDC 可能單純沿用其 statin 成分的單方 CKD 劑量
指引——已明確標記為 `EXPERT INTERPRETATION`，非文獻結論。機轉性文獻（T-027：ESRD 使肝臟 OATP1B1/3
表現量下降約 75%，PBPK 模擬）提供了「為何 CKD 需要劑量上限」的機轉合理性，但同樣不是新的實證數字。

**本輪 Challenge Round 標記此為專案最高風險的安全性缺口**：任何未來臨床導向的輸出（簡報、手稿），
若暗示 FDC 複方的 CKD 劑量等同其單方成分而未明確標註這是推論、非文獻證實，即構成有病人安全疑慮的
過度延伸。

## 多重用藥情境的實務應用

本專案 Search Protocol 明確要求將 DDI 討論應用於實際病例情境（`CLAUDE.md` §5 item 4）：高齡 +
高血壓 + 糖尿病 + 冠心病 + CCB + 抗血小板/抗凝血藥物。基於 T-010 的標籤數據，此類病人使用
pitavastatin 時，主要臨床關注點應聚焦於：（1）是否併用 cyclosporine（禁忌）；（2）是否需要
erythromycin 等巨環內酯類抗生素（劑量調整）；（3）fibrate 類降脂藥物的選擇（gemfibrozil 避免，
fenofibrate 相對安全）；（4）CKD 病人的基礎劑量調整（單方已明確，FDC 複方待進一步證據）。這比單純
呈現 pharmacokinetic table 更具臨床決策價值，但仍須以「low CYP3A4-dependent interaction liability」
的校準語言呈現，避免「pitavastatin 沒有交互作用」的誤導性簡化。
