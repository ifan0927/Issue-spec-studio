# Quality Measurement

## Objective

衡量的是規格是否降低執行期的不確定性與返工，而不是模板填滿率、文件長度或抽象品質分數。

## Measurement policy

採 exception-driven、低維護成本的方式。正常成功的 Issue 不額外建立詳細紀錄；只有規格造成下游異常時記錄一個標準化 quality event。

## Quality event triggers

- Coding agent 因需求歧義必須停止。
- 執行中發現 project rule conflict。
- Implementation Plan 在 repo 現況下不可行。
- Scope 漏項造成實質擴張或 replacement Issue。
- AC 無法判斷是否完成。
- Verification 無法執行或不能產生必要證據。
- Issue 過大導致拆分、取消或高額返工。
- Risk overlay 漏失造成 migration、compatibility、安全、部署或 rollback 問題。

## Minimal event information

- Affected Issue reference。
- Failure category。
- 發現階段。
- 是否阻塞 execution。
- 是否需要 clarification、replacement Issue 或 project policy update。
- 一句根因摘要。

事件可以記在 Linear Issue comment，並視需要加一個簡單 label。Core 只定義事件內容，不負責寫入 Linear。

## Useful measures

以完成的 standardized Issues 為 denominator，可觀察：

- Execution 開始後需要重大 clarification 的比例。
- 因 spec defect 停止或重開的比例。
- 因 Issue 過大而拆分或取消的比例。
- AC／Verification 不足事件比例。
- Project governance conflict 比例。
- 從討論到 approval 的人工作業負擔是否合理。

## Anti-metrics

不以以下項目代表品質：

- Section 數量。
- 字數。
- 模板完成百分比。
- LLM 自評分數。
- 問題數量。
- Roadmap Issue 數量。

## Improvement rule

只有重複出現、且可由 Studio authoring rule、template 或 deterministic check 預防的失敗，才改進系統。一次性 edge case 不自動增加流程與 schema。
