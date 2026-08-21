# Canonical Issue Model

## Representation

Canonical artifact 是單一、標準 Markdown Issue。

- 人類可直接閱讀與編輯。
- Coding agent 可依穩定 headings 理解內容。
- 使用低干擾版本標記，例如 HTML comment，避免額外 YAML／JSON 成為第二份語意來源。
- MVP 不維護 human-readable 與 machine-readable 雙層 artifact。
- 核心是穩定 information model 加可組合 sections，不要求所有任務填滿同一份大型模板。

## Semantic categories

### User requirement

描述必須達成的外部行為、能力或限制。不得混入未確認推測。

### Confirmed decision

Human 已確認、會約束 scope 或 implementation strategy 的決定。最終 Issue 直接表達有效結果，不保存決策歷史。

### Assumption

暫時依賴但尚未完全證實的前提。會影響可行性或驗收的 assumption 必須在 ready 前驗證或轉成明確 requirement；最終 Issue 不得留下阻塞性 assumption。

### Implementation guidance

已決定的策略、architecture boundary、sequence 與 integration approach。Coding agent 應遵循，但它不是逐行程式設計。

### Agent discretion

不影響外部行為、project rules、strategy、safety 或 verification 的低階實作選擇。Issue 應明示重要自由裁量邊界，不要求列出所有微小自由。

## Required core

所有 coding Issue 至少包含：

- Goal
- Scope
- Implementation Plan
- Acceptance Criteria
- Verification

## Composable sections

依任務需要加入：

- Context／Problem
- Out of scope
- Requirements
- Applicable project references
- Constraints
- Agent discretion
- Dependencies
- Risks and safeguards
- Migration／compatibility／rollback
- Observability／deployment
- Issue-specific Definition of Done delta

Project-wide DoD、coding style、test commands 與一般治理規則應由 repo／Project Profile 提供，不在每個 Issue 重複。Issue 只記載本任務的 delta 或真正需要 coding agent 注意的 reference。

## Authoring depth

### Compact

適用於範圍局部、行為明確、風險低、沒有跨 boundary 影響，而且可用直接 verification 驗收的任務，例如文案、小 bug、單一設定或局部重構。

最低仍保留 Goal、Scope、Implementation Plan、AC 與 Verification，但內容可以非常短。

Discussion AI 依當前需求判斷 compact path；human 不需先選模式，也不建立固定 classifier 或分數模型。

若釐清過程發現跨模組、compatibility、migration、安全、部署、rollback、不明依賴或無法直接驗證，應自然提升到 standard 深度。

### Standard

適用於一般功能、重要 bug fix、跨 boundary 變更或需要多個明確決策的工作。

Standard 應完整描述 context、requirements、out of scope、implementation strategy、agent discretion、AC、verification、dependencies 與相關風險。

### Risk overlays

High-risk 不是第三套模板。當任務涉及下列領域時，在 compact 或 standard 核心上增加必要 sections 與 evidence：

- Data migration
- API／schema／behavior compatibility
- Authentication／authorization／security
- Deployment sequencing
- Rollback／recovery
- Multi-repo／cross-system integration
- Observability 或 production data correctness

Overlay 可以促使任務拆成準備、變更、切換、驗證與清理等多個 Issues。

## Issue size

一個 Issue 對應一個 outcome、一個實作計畫、一個 PR 邊界及一組 verification evidence。

偏好多個小而明確的 Issues，不接受將高度不確定、跨多階段的工作包成單一大型 Issue。Issue 必須能在不依賴 coding agent 做高階策略判斷的前提下安全執行。

## Requirements and acceptance criteria

- Requirement 描述必須成立的行為或限制。
- AC 描述如何觀察該行為已成立，不只是重述 requirement。
- 每個重要 requirement 必須至少有一項 AC 或明確 verification evidence。
- AC 應可由測試、命令、可觀察狀態、API behavior 或人工檢查驗收。
- 不要求複雜 traceability matrix；簡單 identifiers 或文字對應即可。

## Implementation plan

Plan 必須讓 coding agent 不需要決定：

- 核心策略。
- architecture boundary。
- 重要修改順序。
- integration approach。
- safety 與 compatibility 方法。

Plan 不應規定：

- 不影響結果的函式拆分。
- 局部命名。
- 一般語言慣用寫法。
- 已由 repo 規則完整治理的內容。

若 coding agent 發現計畫不可行，Issue 應要求停止、提供證據並回報 spec defect，而不是自行改變高階策略。
