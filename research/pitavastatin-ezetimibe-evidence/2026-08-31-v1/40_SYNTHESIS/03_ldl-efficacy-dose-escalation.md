# 03 LDL 降脂效果與劑量遞增（LDL Efficacy / Dose-Escalation）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Wave 3 Synthesis · 2026-08-31 · 主要來源：trials-efficacy-intelligence

## 三國獨立 Phase III RCT：Level 1 證據的核心

Pitavastatin/ezetimibe FDC 的 LDL 降脂效果，目前有三個獨立國家的 Phase III RCT 直接支持，彼此互相
複製，構成本專案 `DIRECT EVIDENCE` 中最堅實的一塊：

| 試驗 | 國家/地區 | Citation | FDC 降幅 | Pitavastatin 單方降幅 | 全文狀態 |
|---|---|---|---|---|---|
| Chou MT et al. Clin Ther 2022 | 台灣/澳洲/紐西蘭 | #33 | −51.04%（第4週）/ −50.5%（第12週） | −34.99%（第4週）/ −36.11%（第12週） | LDL 效果數字已驗證；安全性表格 `BLOCKED_FOR_SOURCE` |
| Tsujita K et al. J Atheroscler Thromb 2023 | 日本 | T-004a | −51.4%（K-924 LD, 2mg+eze10, 12週） | −45.2%（4mg 單方，12週） | 全文已取得，LlamaParse 解析成功 |
| Jeong HS et al. Clin Ther 2022 | 韓國 | T-028 | −52.8%（合併） | −37.1%（單方） | 摘要已驗證；全文 `BLOCKED_FOR_SOURCE` |

三個試驗一致顯示：pitavastatin/ezetimibe FDC 相較 pitavastatin 單方，LDL-C 降幅皆超過 50%，且皆顯著
優於各自的單方對照組（P<0.001）。Ezetimibe 單方對照組（如 #33 的 −19.85% ~ −20.01%）降幅明顯較小，
符合機轉預期（intestinal absorption inhibition 單獨效果弱於 hepatic synthesis inhibition + absorption
inhibition 的合併效果）。這是本專案 `pitavastatin topic.md` §6 所稱「Level 1 LDL-lowering efficacy」
的具體實證基礎，且**跨三個獨立國家/族群重現，強化其外部效度**。

## 2mg vs 4mg，以及「加 ezetimibe」vs「劑量加倍」

T-004a（Tsujita 2023）是本專案唯一直接回答「2mg vs 4mg」劑量遞增問題的 4-arm RCT（pitavastatin
2mg／4mg／K-924 LD＝2mg+eze10／K-924 HD＝4mg+eze10，隨機分派 293 人，288 人納入療效/安全性分析組，
每組 72 人）。Wave 3 全文解析確認其統計設計為**成對 MMRM（pairwise），非整體 pooled 檢定**：

- **K-924 HD vs K-924 LD（FDC 內部劑量遞增）**：正式檢定，達統計顯著，差異 −6.4%（95% CI −9.6 至
  −3.2, p≤0.001）。
- **K-924 LD vs pitavastatin 4mg 單方（即「加 ezetimibe」vs「劑量加倍」，`pitavastatin topic.md`
  提出的臨床決策標題問題）**：**從未被正式檢定**，僅有描述性點估計（−51.4% vs −45.2%），無對應的
  p 值或信賴區間。

**這是本輪 Challenge Round 的重要防線**：`pitavastatin topic.md` 原始構想中「Add ezetimibe or double
the statin?」這張決策投影片，其吸引力來自於「加 ezetimibe 效果比劑量加倍更好」的直覺印象，但**目前
唯一可直接回答此問題的試驗，並未針對這個具體比較做正式統計檢定**。任何未來簡報或手稿若要呈現這張
決策投影片，必須明確標註該點估計差異為描述性資料，不具統計顯著性結論。

## 安全性資料：AE 與 ADR 的區分，以及族群/產品交叉引用的界線

T-004b（Ako 2024，T-004a 的 52 週開放性延伸研究）全文解析發現，其摘要「a single adverse drug
reaction」的敘述若單獨引用會低估實際安全性圖像：整體 AE 發生率 59.6%（65/109 人），其中 12 例
severe AE（11.0%），但全研究僅 1 例經判定為藥物相關 ADR（CK 上升），且無任何 severe AE 被判定為
藥物相關。「well-tolerated」的結論本身仍然成立，但**引用時必須同時呈現整體 AE 發生率與 ADR 判定結果
兩個數字，不可僅引用 ADR 數字造成安全性圖像過於樂觀**。

**族群/產品交叉引用警示**：T-004a/T-004b 為日本族群，與 #33（台灣/澳洲/紐西蘭）為不同的法規申請/
族群基礎，即使是相同藥物組合。#33 自身的 AE/CK/肝功能詳細表格 `BLOCKED_FOR_SOURCE`（Unpaywall 無 OA
連結，Wave 2/3 兩輪未解），因此 Wave 2 曾以 T-004a/T-004b 的日本安全性資料作為替代參考——**此替代
必須明確標註為 `INDIRECT EVIDENCE`，不可呈現為台灣族群本身的安全性數據**。

## 真實世界資料：與 RCT 證據互補，但等級不同

T-023（Lu et al. 2026，台灣 PCI 後真實世界回溯性世代，N=120，pitavastatin 4mg+ezetimibe 10mg）全文
取得後顯示更豐富的資料：依先前 statin 暴露史分層的 LDL-C 反應（statin-naïve −38.47% vs
ex-statin+eze −16.03% vs ex-statin-alone −13.17%）、調整後 GEE 模型（LDL-C −36.11 mg/dL，95% CI
−46.52 至 −25.69，p<0.0001）。其摘要原先呈現的「zero AE」在全文 Limitations 段落中被**該研究自己
承認**極可能是回溯性病歷回顧的低估（under-ascertainment），而非真正的零不良事件——這與 trials-efficacy
在 Wave 2 僅憑摘要就提出的謹慎判斷完全吻合，屬於 `OBSERVATIONAL EVIDENCE`，不可與 T-004a 等 RCT 的
正式 AE 通報等量齊觀。

## 尚待完成的最高優先缺口：T-024

T-024（Abbas MS et al. 2026, Future Cardiol）的收案條件（pitavastatin 2/4mg+eze10 vs pitavastatin
2mg alone）與本專案已納入的 FDC 試驗高度吻合，**可能是第一篇 pitavastatin/ezetimibe FDC 專屬的正式
系統性回顧/meta-analysis**。若其確實 pool 了 #33、T-004a、T-028 等試驗，將可能把 Level 1 證據從「三個
獨立 RCT 的敘事性複製」提升為「正式統合分析的定量證據」——但截至 Wave 3，經過三次合法管道嘗試
（Unpaywall、Taylor & Francis figshare 補充材料連結、ResearchGate 鏡像）皆未取得全文，其實際 pooled
結果完全未知，不得猜測或引用。此為本專案下一輪（若授權 Wave 4 之後的追蹤，或未來 run）的最高優先
證據取得目標。
