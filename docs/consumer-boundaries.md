# Consumer Boundaries

## Core output boundary

Studio 的責任終點是產生一份經 human approval 的標準 Markdown Issue。

將內容發布到 Linear、GitHub 或其他平台，可以由當前 discussion AI 使用平台工具完成，也可以由 human 手動完成；發布能力不進入 core。

## Linear

Linear 預期是主要 Issue 管理平台與 Issue ID 來源。

- Studio 不預先配置 Issue ID。
- 發布後由 Linear 產生 ID。
- Status、priority、assignee 與 execution progress 以 Linear 為準。
- Studio 不建立自動雙向同步。

## GitHub

GitHub 保存 target repo、governance、code、PR、CI 與 review evidence。Studio 只在需要 project context 或 repo evidence 時讀取。

Issue 發布到 GitHub 時仍使用同一份標準 Markdown，不需要改變 canonical semantics。

## Coding agents

Coding agent 應讀取：

- 最終 coding Issue。
- Target repo 的 agent instructions 與適用治理文件。
- Issue 明確引用的 task-specific context。

Coding agent 不依賴 discussion roadmap 或 working ledger。需要理解背景時，以 execution contract 與其必要 references 為入口。

## ALC

ALC 是眾多 downstream consumers 之一。

- Studio 不依賴 ALC code、database、state machine 或 TUI。
- ALC 的需求不是 canonical domain model。
- Studio 不管理 Codex execution、verification、review、PR、merge 或 cleanup。
- Issue 中可以加入「計畫不可行時停止並回報 spec defect」的防禦性提示；實際 enforcement 是 ALC／executor 責任。
- 若執行中的需求罕見地重大改變，由 human 手動停止 ALC，再建立 replacement Issue。

## Renderer and adapter

MVP 不建立 renderer framework。標準 Markdown 本身就是 portable output。

未來若 consumer 確實需要特殊格式，可以建立 thin adapter，但必須遵守：

- 不改變 Goal、Scope、Requirements、Plan、AC 或 Verification 的語意。
- 不補造 canonical artifact 缺少的需求。
- 不把 consumer-specific runtime state 回寫成 core schema。
- 轉換後仍須保持 coding-ready。
- 可刪減的只能是對該 consumer 非必要且不影響執行契約的 presentation metadata。

## Skill

MVP 先以 local Studio project 運作，不要求 Skill。

未來若需要從其他 repo 或 ChatGPT context 快速啟動，可以建立單一、薄的 user-facing Skill。Skill 只負責找到 Studio、載入 bootstrap 與引導工作流程，不保存 canonical state，也不拆成 analyze／clarify／plan 等多個 Skills。
