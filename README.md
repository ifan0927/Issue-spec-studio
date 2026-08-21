# Issue Spec Studio

Issue Spec Studio 是一個 local-first、consumer-neutral 的規格工作區，用來把自然語言需求討論轉換成穩定、標準化、可執行的 coding-ready Issue。

本 repository 目前保存已確認的產品與流程設計基線，供後續本地 Codex 接手。它不是 ALC 的子系統，也尚未進入程式實作階段。

## 核心輸出

- 經人工批准的 Project Profile
- 有邊界的 milestone roadmap
- 單一、標準 Markdown coding Issue

## 核心原則

- 專案治理高於 Issue；Issue 不得覆寫 repo 規則。
- Discussion AI 負責需求分析、釐清、拆分、規劃與語意檢查。
- Coding agent 不承擔高階策略決策，只在明確授權範圍內決定實作細節。
- Context 依 reference 按需載入，不預先展開整個 project。
- Linear、GitHub、repo 與下游系統各自保有其權威資料，不在 Studio 建立鏡像狀態。
- 小任務走低摩擦 compact path；高風險要求以 overlay 增加必要證據。

## 從哪裡開始

Agent 與維護者都先閱讀 [START_HERE.md](START_HERE.md)。該文件是最小 bootstrap，會依任務引導至必要 reference。

目前設計成熟度與下一步見 [HANDOFF.md](HANDOFF.md)。

