# Product Boundary

## Product statement

Issue Spec Studio 將自然語言對話、已批准的 project context 與 repo 現況，轉換為可交給 coding agent 或人工開發者執行的標準 Markdown Issue。

它負責 Issue coding-ready 之前的需求工作，不負責 Issue 被接單之後的執行控制。

## Primary user

主要使用者是單人開發者：透過 ChatGPT、Codex 或其他 discussion AI 討論需求，再將結果交給 coding agent、Linear、GitHub 或人工流程。

設計不為尚未證實的多人協作、企業治理或大規模平台需求增加複雜度。

## In scope

- 從自然語言形成結構化需求。
- 發現缺漏、歧義、衝突與不可驗證描述。
- 產生少量高資訊價值的 clarifying questions。
- 區分 confirmed decisions、assumptions、implementation guidance 與 agent discretion。
- 依任務規模採 compact 或 standard authoring depth。
- 依 migration、compatibility、安全、部署等風險增加必要 overlay。
- 將大型需求拆成可獨立安全執行與驗證的 Issues。
- 維護 bounded milestone roadmap。
- 建立及更新 Project Profile。
- 在輸出前執行 semantic review、ready gate 與 human approval。
- 輸出 consumer-neutral 的標準 Markdown Issue。

## Out of scope

- 接單、排程、執行 coding agent。
- 管理 worktree、branch、commit、PR、CI、merge 或清理。
- 追蹤 ALC runtime state。
- 自動同步 Linear、GitHub 或其他 issue manager。
- 成為另一個 project management system。
- 維護完整聊天紀錄或永久 discussion ledger。
- 在 MVP 建立 database、service、TUI、workflow engine 或 renderer framework。
- 要求 Issue 重複 project governance。
- 讓 Issue 覆寫 project-level rules。
- 對所有任務套用大型 PRD 儀式。

## Independence

核心模型不依賴 ChatGPT、Codex、Linear、GitHub、ALC 或 spec-kit。任何平台能力都是外部入口或 consumer。

即使完全不使用 ALC，Studio 仍能服務一般 coding agent、人工開發、GitHub Issue 或 Linear Issue。

## Success conditions

- 相似需求能產生結構與品質一致的 Issue。
- Coding agent 不需要補做高階產品或實作策略決策。
- Issue 足以驗收，且不過度鎖死低階實作細節。
- 小修改的規格成本維持低於實作成本。
- 高風險修改會要求額外分析、拆分與證據。
- 新對話或 context compaction 後可從乾淨 checkpoint 恢復。
- Project onboarding 後能依 references 按需取得規範，而非重複掃描或全文載入。
- 已發布 Issue 與執行狀態只由其權威系統管理。
