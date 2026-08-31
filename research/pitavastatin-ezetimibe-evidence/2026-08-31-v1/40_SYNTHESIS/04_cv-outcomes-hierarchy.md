# 04 心血管結果證據層級（CV-Outcomes Hierarchy）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Wave 3 Synthesis · 2026-08-31

本節是本專案科學誠信最重要的一節——`pitavastatin topic.md` §6 建立的三層框架，經 Wave 1–3 完整驗證，
且新增了兩個容易與其混淆的旁支證據（REPRIEVE、REAL-CAD）。**維持這四類證據彼此不被混淆，是本輪
Challenge Round 標記的專案最高風險事項。**

## 四類心血管結果證據，不可互相替代

| 證據類型 | Citation | 藥物組合 | 族群 | 結論 | Evidence Hierarchy |
|---|---|---|---|---|---|
| **Level 3 直接證據** | T-001 HIJ-PROPER | Pitavastatin + ezetimibe vs pitavastatin alone | ACS | 整體 primary outcome **未達統計顯著**：32.8% vs 36.9%, HR 0.89 (95% CI 0.76–1.04, P=0.152) | `DIRECT EVIDENCE`（試驗本身），但結論為 non-superiority |
| Level 3 次族群訊號 | T-001 absorber-phenotype 次族群 | 同上 | 高 baseline sitosterol 次族群 | HR 0.71，訊號較佳 | `INSUFFICIENT EVIDENCE`（hypothesis-generating，非確證策略） |
| **Level 2 策略證據（間接）** | T-002 RACING | **Rosuvastatin** + ezetimibe vs high-intensity statin monotherapy | 一般族群含 DM 次族群 | Non-inferiority 達成；MACE 9.1% vs 9.9%（3年） | `INDIRECT EVIDENCE`（非 pitavastatin） |
| Pitavastatin 單方硬終點證據（非 FDC） | T-015 REPRIEVE | Pitavastatin 4mg **單方** vs 安慰劑 | HIV 感染者 | MACE HR 0.65 (95% CI 0.48–0.90, P=0.002)，提早終止試驗因效果顯著 | `DIRECT EVIDENCE`（pitavastatin 單方本身），**非 FDC 證據** |
| Pitavastatin 劑量比較硬終點證據（非 FDC） | T-016 REAL-CAD | Pitavastatin 4mg vs 1mg | 日本穩定冠心病 | HR 0.81 (95% CI 0.69–0.95, P=0.01) | `DIRECT EVIDENCE`（pitavastatin 劑量本身），**非 FDC 證據** |

## 為什麼 REPRIEVE 與 REAL-CAD 不能墊高 Level 3

REPRIEVE 與 REAL-CAD 都是設計嚴謹、族群龐大（N=7,769 與 N=13,054）、結果正向的 pitavastatin RCT，
證明 pitavastatin **本身**具有心血管硬終點效益的直接證據。這個事實本身完全正確、值得在任何綜整中
呈現。**但這兩個試驗都不含 ezetimibe**——REPRIEVE 是 pitavastatin 單方 vs 安慰劑，REAL-CAD 是
pitavastatin 兩個劑量的比較，皆與「pitavastatin/ezetimibe FDC 是否有其專屬的心血管硬終點證據」這個
Level 3 問題無關。

本輪 Challenge Round（`30_METHODS/shared/wave2-challenge-round.md`）將此列為專案**最高風險的
overclaim 情境**：一句看似合理的句子——「pitavastatin 已證實具有心血管結果效益」——若未清楚區分
「pitavastatin 單方」與「pitavastatin/ezetimibe FDC」，讀者很容易推論成「因此 pitavastatin/ezetimibe
FDC 也已證實具有心血管結果效益」，而這正是 HIJ-PROPER 尚未證實、仍是 Level 3 缺口的部分。任何簡報或
手稿在引用 REPRIEVE/REAL-CAD 時，都必須明確加註「pitavastatin 單方，非 FDC」的限定語。

## 三層框架的最終定位（Wave 3 收尾狀態）

1. **Level 1（LDL-lowering efficacy）**：強，且經三國獨立複製（#33 台灣、T-004a 日本、T-028 韓國），
   `DIRECT EVIDENCE`。
2. **Level 2（combination-strategy 心血管結果證據）**：強，但非 pitavastatin 專屬（T-002 RACING 為
   rosuvastatin），`INDIRECT EVIDENCE`。
3. **Level 3（pitavastatin/ezetimibe 專屬硬終點證據）**：**尚未直接、充分證明**——HIJ-PROPER 整體
   未達顯著，次族群訊號僅為 hypothesis-generating。這不是本專案的缺點，而是誠實的證據現況：LDL
   降脂效果證據很強 → combination strategy 的結果證據很強（但非 pitavastatin 專屬）→ pitavastatin/
   ezetimibe 專屬的硬終點優越性尚未被直接充分證明。

**唯一可能改變此結論的路徑**是 T-024（若其為 pitavastatin/ezetimibe FDC 專屬的正式 meta-analysis 且
納入了心血管結果數據）——但其全文目前完全無法取得，其存在本身不構成任何新增證據，僅是一個尚待驗證的
可能性（見 `03_ldl-efficacy-dose-escalation.md` 末段、`07_limitations-open-gaps.md`）。
