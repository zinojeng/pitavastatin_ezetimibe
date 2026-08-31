# 02 指引與風險分層定位（Guideline / Risk-Positioning）

PROJECT_ID: `pitavastatin-ezetimibe-evidence` · RUN_ID: `2026-08-31-v1`
Owner: Research Director · Wave 3 Synthesis · 2026-08-31 · 主要來源：guideline-risk-intelligence

## 從 intensity-based 到 goal-directed：典範轉移

2018 版 ACC/AHA 指引（#17/#18）以 statin intensity（≥50% / 30–49% / <30% LDL-C 降幅）為核心邏輯；
2026 版 ACC/AHA 指引（#28，`GUIDELINE/CONSENSUS`）改用 PREVENT-ASCVD 方程式估計 10 年風險，並納入
CAC、Lp(a)、ApoB 等 risk enhancer 精算個人化風險，直接訂出絕對 LDL-C/non-HDL-C 目標值。這個轉變的
臨床意義是：**先問「這個病人的目標是多少、baseline 多少、需要降幅多少」，再反推起始治療強度**，而非
「先給 high-intensity statin，再視情況調整」。

## 風險分層目標比較（四份指引、四套數字，`CLAUDE.md` §9 提醒不可混用）

| 指引 | 風險族群 | LDL-C 目標 | Citation | 全文狀態 |
|---|---|---|---|---|
| 2026 ACC/AHA | Very-high-risk 次級預防 | <55 mg/dL，≥50% 降幅 | #28 | `BLOCKED_FOR_SOURCE`（引用已驗證） |
| 2026 ACC/AHA | Not very-high-risk 次級預防 | <70 mg/dL，≥50% 降幅 | #28 | 同上 |
| 2023 TSC CCS | Extreme-risk | <50 mg/dL | #30 | 全文已取得 |
| 2023 TSC CCS | General CCS | <70 mg/dL | #30 | 全文已取得 |
| 2025 ADA | 次級預防合併糖尿病 | <55 mg/dL | #32 | 全文已取得（recommendation 10.22/10.28/10.33/10.34） |
| 台灣 2022（#29） | CAD/ACS、PAD、缺血性中風/TIA | 依基線 LDL-C 與臨床狀況，中至高強度 statin 或合併 ezetimibe（未列單一絕對數字） | #29 | 全文已取得 |
| 台灣 2022 初級預防（#35） | DM/CKD/LDL-C≥190 | <100 mg/dL | #35 | 全文已取得 |
| 台灣 2022 初級預防（#35） | ≥2 危險因子 | <115 mg/dL | #35 | 同上 |
| 台灣 2022 初級預防（#35） | 1 危險因子 | <130 mg/dL | #35 | 同上 |
| 台灣 2022 初級預防（#35） | 0 危險因子 | <160 mg/dL | #35 | 同上 |
| 2025 台灣血脂管理臨床路徑（#27） | 依風險分級（低/中/高/非常高/極高） | 130/115/100/70/55 mg/dL 分層 | #27 | **引用已驗證（DOI 已修正），但這組數字取自 `Tonvasca_2026.md` 自身轉載的流程圖，尚未獨立對照 #27 原文全文覆核**——與 #27 citation 本身的 bibliographic 驗證（作者/期刊/卷期）屬不同層級的驗證，不應混為一談 |

**關鍵提醒**：#28（<55, very-high-risk）與 #30（<50, extreme-risk）是兩份不同指引對「風險最高族群」
使用的兩個不同數字，其風險分層定義本身也不完全相同——任何綜整文字若寫成「指引建議 <55 mg/dL」而未
指名是哪一份指引、哪一個風險分層，即構成本輪 Challenge Round 標記的過度概括風險。

## Taiwan STS（Suboptimally Tolerable Statins）2026：本專案最重要但未驗證的框架概念

台灣血脂及動脈硬化學會 2026 年提出 STS 概念，刻意與傳統「statin intolerance」區分：許多真實世界病人
並非正式符合完全不耐受，而是「high-dose 後肌肉痠痛、CK 上升但不嚴重、病人害怕副作用、DM/prediabetes
擔心血糖、高齡多重用藥」等，導致無法長期維持足以達標的 statin intensity。臨床問題因此從「這個病人是否
statin intolerant」轉變為「這個病人能否長期維持足以達標的 statin intensity」。

`pitavastatin topic.md`（PI 論點筆記）指出 STS 2026 共識將 ezetimibe 定位為 high/very-high-risk 病人
的**第一線 add-on**，extremely-high-risk 病人**及早合併治療**，優先於 bempedoic acid 或 PCSK9-targeting
therapy。**這是 `GUIDELINE/CONSENSUS` 層級的框架性論斷，但截至 Wave 3，其具體措辭從未經 T-005 原文
獨立驗證**——T-005 全文在 Wave 2、Wave 3 兩輪皆確認 `BLOCKED_FOR_SOURCE`（Cloudflare bot-challenge，
以精確的 NCBI elink 方法二次確認為真陰性，非單純推測）。目前唯一的依據是 PI 自己的論點筆記轉述，
**不構成獨立驗證**。此為 Challenge Round 標記的專案最高優先未驗證論述（見
`30_METHODS/shared/wave2-challenge-round.md` 與 `07_limitations-open-gaps.md`）。

## ESC 2025 Focused Update：住院期間即完成降脂強化

ESC 2025 Focused Update（T-007）明確建議 ACS 病人於住院期間即完成 lipid-lowering intensification；
若 treatment-naïve 病人預期單靠 high-intensity statin 無法達標，可於 index hospitalization 即考慮
high-intensity statin + ezetimibe 起始治療。**T-007 原文全文亦 `BLOCKED_FOR_SOURCE`**（與 T-005 同一
Cloudflare 阻擋模式，Europe PMC metadata 交叉確認為真陰性）。Wave 2 透過二手來源
T-021（Katzmann & Laufs 2026 review）取得部分佐證性轉述，但需特別注意：**T-021 本身在比較「美國指引
是否建議 upfront combination」時，引用的是舊版 2018 AHA/ACC 指引，而非 2026 新版**——這是二手文獻常見
的時效性陷阱，任何引用 T-021 的段落都必須明確標示其為「對 ESC 2025 建議的轉述」，而非 ESC 2025 或
2026 ACC/AHA 的原文。

## 2023 TSC 慢性冠心症（CCS）指引：Upfront Combination 的明確立場

台灣心臟學會 2023 年 CCS 指引（#30，全文已取得）第 9.1.4 節明確主張：近期使用非 statin
降脂藥物（ezetimibe 及/或 PCSK9 inhibitors）的 RCT、meta-analysis 及 Mendelian randomization 資料
支持「the earlier the better」「the lower the better」「the longer the better」。雖然多數國際指引仍
建議先用 high-intensity statin monotherapy 再視情況合併治療，但依「越早越好」原則，**upfront
combination therapy 應成為高風險病人達標的新標準**——此為 `GUIDELINE/CONSENSUS`，COR/LOE 分級文字
已由 guideline-risk 於 Wave 3 直接自原文萃取確認。2021 EAS 指引（#31）持相同立場。

## 小結：指引定位對 pitavastatin/ezetimibe FDC 的意涵

四份不同管轄權的指引（美國 ACC/AHA、歐洲 ESC/EAS、台灣 TSC/STS、美國 ADA）在 2023–2026 年間一致朝向
「及早合併治療」的方向靠攏，但**各自的絕對 LDL-C 目標數字、風險分層定義並不相同**，且**台灣特有的
STS 概念——本專案對 pitavastatin/ezetimibe FDC 最具說服力的臨床定位論述——其原始文本目前仍未能獨立
驗證**。任何未來的臨床綜整或簡報，在引用「指引建議及早合併治療」時，都應同時標明是哪一份指引、哪一個
風險分層、目標值是多少，並在涉及 STS 2026 的具體措辭時明確註記「依 PI 論點筆記轉述，原文未驗證」。
