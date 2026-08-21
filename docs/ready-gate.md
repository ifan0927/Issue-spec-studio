# Coding-ready Gate

## Gate result

Discussion AI 在 human approval 前輸出以下其中一種結論：

- `BLOCKED`：存在必須先解決的缺漏或衝突。
- `READY WITH ADVISORIES`：可執行，但 human 應知悉非阻塞風險。
- `READY`：沒有已知阻塞問題。

這份 review 結果是批准前資訊，不放入最終 Issue。

## Blocking conditions

出現任一項即不得 coding-ready：

- Goal 仍可能代表不同 outcome。
- Scope 或 out of scope 會導致實作邊界不明。
- 存在尚未回答、會改變策略或驗收的問題。
- Issue 與 target repo governance 衝突。
- 依賴尚未完成或沒有明確處置方式。
- Coding agent 仍需選擇高階策略。
- Requirement 沒有可驗收 AC 或 verification。
- Verification 無法在預期環境執行或取得證據。
- Issue 同時包含多個無法以單一 PR／驗證單元交付的 outcomes。
- Migration、compatibility、安全、部署或 rollback 風險未處理。
- Issue 依賴未驗證且會影響可行性的 assumption。

## Ready checklist

### Intent and boundary

- [ ] Goal 描述單一、具體 outcome。
- [ ] Scope 明確列出需要改變的範圍。
- [ ] 必要時明示 out of scope。
- [ ] Issue 大小適合一次獨立實作、review 與 verification。

### Decisions and plan

- [ ] 所有高影響問題已解決。
- [ ] Confirmed decisions 已進入 Issue。
- [ ] Implementation Plan 指定策略、boundaries 與順序。
- [ ] Agent discretion 不會改變需求、安全或相容性。
- [ ] Coding agent 無需重新做產品或 architecture planning。

### Project consistency

- [ ] 已載入與任務相關的 Project Profile refs。
- [ ] Issue 沒有覆寫 project governance。
- [ ] Issue 沒有大量複製 repo 規則。
- [ ] Repo 現況足以支持計畫，或前置 Issue 已明確建立必要基礎。

### Acceptance and evidence

- [ ] 每項重要 requirement 均可驗收。
- [ ] AC 描述 observable outcome，不只是重述需求。
- [ ] Verification 說明如何取得證據。
- [ ] 必要的 test、lint、build 或人工檢查範圍清楚。
- [ ] Issue-specific DoD delta 已列出；沒有重複 project-wide DoD。

### Risk

- [ ] 已辨識適用的 risk overlays。
- [ ] 需要時包含 compatibility、migration、rollback、security、deployment 或 observability 證據。
- [ ] 高風險工作已拆分成可以安全停止與驗證的步驟。

### Final hygiene

- [ ] 沒有 open questions、TBD、TODO 或未處理 placeholder。
- [ ] 沒有 brainstorm transcript、被否決方案或 validation report。
- [ ] References 都與本 Issue 直接相關。
- [ ] Markdown 結構乾淨且可獨立閱讀。

## Approval and freeze

Human approval 代表同意 Goal、Scope、重要 decisions、Issue split、Implementation Plan、AC 與 Verification。

Approval 後的 Issue 應視為 frozen output。發布前若發現實質語意變更，必須重新取得 approval；發布後則建立新的或 superseding Issue，不在 Studio 靜默改寫。
