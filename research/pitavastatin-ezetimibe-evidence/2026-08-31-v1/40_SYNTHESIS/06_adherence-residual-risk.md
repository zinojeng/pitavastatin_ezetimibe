# 06 服藥遵從性與殘餘風險（Adherence / Residual Risk）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Wave 3 Synthesis · 2026-08-31

> 依 Research Charter，本節（含 residual risk / Lp(a) 子項）維持整體輸出篇幅的 ≤10–15%，不搶主軸。

## FDC 對服藥遵從性的間接證據

Fixed-dose combination（FDC）相較分開服用（separate/free-equivalent combination），在服藥遵從性上
有中等強度、方向一致的間接證據支持：

- T-022（Wei et al. 2023，跨疾病領域、61 篇研究 meta-analysis）：FDC 相較分開服用，遵從機率 RR
  1.29（95% CI 1.23–1.35, p<0.00001）。`INDIRECT EVIDENCE`——跨疾病領域一般性結論，非
  statin+ezetimibe 專屬。
- T-012（Katzmann et al. 2022，德國真實世界世代）：FDC 相較分開服用，額外 LDL-C 降幅 28.4% vs
  19.4%（p<0.0001），LDL<70 達標率 31.5% vs 21.0%。**引用 n 時務必使用 n=1,639（FDC）/ n=796
  （分開服用）這一對數字**——`Tonvasca_2026.md` 另印有一組 n=6,429/533，經 Wave 3 全文比對確認為
  同一研究中不同子集（GP 2018 年處方普及率快照），非同一結果的錯誤數字（詳見
  `03_DECISION-LOG.md` Decision 2026-08-31-11 最終更新）。
- T-025（Samnaliev et al. 2025，rosuvastatin/ezetimibe FDC 世代，THIN 資料庫）：持續服藥 HR 0.54
  （95% CI 0.51–0.58），遵從 OR 3.00（95% CI 2.70–3.30）。**其 R10/E10 劑量次族群顯示正向 MACE
  訊號（HR 0.58, p=0.030），但此訊號未在該研究自身的整體世代分析中重現**——不得單獨引用此次族群
  數字作為「FDC 降低心血管事件」的證據。

**三項來源皆非 pitavastatin 專屬（T-012、T-025 為其他 statin；T-022 為跨疾病領域），且全數為回溯性/
觀察性設計，存在 healthy-adherer bias（服藥遵從性較高的病人，往往在未測量的健康行為與社經條件上
也較佳，此混淆因子無法被觀察性設計完全排除）**。「FDC → 遵從性提升 → 結果改善」這條因果鏈目前僅有
關聯性證據支持，本專案任何綜整文字若要呈現此邏輯鏈，必須使用關聯性語言（例如「與較佳結果相關」），
不得使用因果語言（例如「FDC 可改善結果」），除非未來取得隨機分派 FDC vs 分開服用的頭對頭試驗。

## Residual Risk：LDL 達標之後，為什麼還會發生第二次事件？

臨床銜接語句：「病人 LDL-C 已達 55 mg/dL 的目標，為什麼還會發生第二次心肌梗塞？」——答案是並非所有
殘餘風險都能單靠 statin 類藥物解決。Lipoprotein(a)［Lp(a)］是目前最受關注的殘餘風險標記之一：

- 2026 ACC/AHA（#28）建議成人至少終身檢測一次 Lp(a)，≥50 mg/dL 或 ≥125 nmol/L 列為 risk enhancer。
  **精確溯源（Wave 4 稽核發現並修正）**：mg/dL 數字（≥50 mg/dL）追溯至 `Tonvasca_2026.md`（L-002）
  第1361行的 risk enhancer 表格，明確引用 #28；nmol/L 換算數字（≥125 nmol/L）僅見於
  `pitavastatin topic.md`（L-001，PI 論點筆記）第149行，未見於 L-002 或任何已取得的文獻全文。
  **兩者皆未經獨立對照 #28 原文全文覆核**（#28 全文仍 `BLOCKED_FOR_SOURCE`）——與下方 ESC 2025 數字
  屬同一驗證層級（見 `02_SOURCE-INVENTORY.md` #28 列與 Decision 2026-08-31-33）。
- ESC 2025（同樣以 Lp(a) 為 risk modifier）閾值約 >50 mg/dL，惟 nmol/L 閾值使用 >105 nmol/L
  （與 ACC/AHA 的 125 nmol/L 不同，屬指引間差異，不可混用）。**此 ESC 2025 數字與 STS 2026 的情況
  相同——T-007 全文 `BLOCKED_FOR_SOURCE`，目前唯一依據是 `pitavastatin topic.md` 的轉述，並非獨立
  驗證的原文**；本輪 Challenge Round 在 Wave 3 覆核時發現此數字先前未獲得與 T-005/STS 2026 claim
  同等的「未驗證」標註，已於此補正——引用時應一併註明來源限制。
- 台灣 2026 年正式發表 Lp(a) 專屬共識（T-006）——**全文 `BLOCKED_FOR_SOURCE`**（無 PMC 收錄，
  tas.org.tw 鏡像嘗試亦未成功，guideline-risk 已停止進一步猜測 URL 型態），其具體內容目前無法
  獨立驗證。

Lp(a) 之外，ApoB、triglyceride-rich remnant cholesterol、發炎指標（如 hsCRP）也是 PREVENT-ASCVD
risk enhancer 清單的一部分（#28）。這些標記共同指向：**LDL-C 達標只是心血管風險管理的必要條件，非
充分條件**，為未來 non-statin/non-ezetimibe 標的治療（如 Lp(a)-lowering therapy）鋪陳臨床脈絡。

**篇幅提醒**：本節依 Research Charter 刻意維持精簡，residual risk 相關的完整文獻回顧（尤其 Lp(a)
專屬治療進展）超出本 RUN 的 Search Protocol 範疇，僅作脈絡性收尾之用。
