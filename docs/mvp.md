# MVP Baseline

## MVP product

MVP 是一個 documentation-first、local-first 的 Issue Spec Studio：

- Repo-level bootstrap instructions。
- 極小 `START_HERE.md`。
- Versioned product rules 與 templates。
- Project Profile onboarding 方法。
- Roadmap 與 Issue decomposition 方法。
- Active checkpoint 與 context hygiene。
- Compact／standard authoring depth。
- Risk overlays。
- Coding-ready gate 與 human approval。
- 標準 Markdown output。

## MVP does not include

- Product CLI。
- Database 或 service。
- TUI／web UI。
- Workflow state machine。
- Linear／GitHub 自動發布。
- ALC integration。
- Renderer framework。
- JSON／YAML canonical schema。
- Template migration engine。
- Quality score。
- Automatic compact classifier。
- 多個 workflow Skills。
- 永久 transcript／ledger storage。

## Internal scripts

`scripts/` 是保留擴充點，不是 MVP 前提。

只有 paper prototype 與真實使用持續出現相同 deterministic errors 時才加入，例如：

- 必要 headings 缺漏。
- Spec marker 格式錯誤。
- Broken refs。
- Placeholder 未清除。
- Requirement／AC identifier 重複或懸空。
- Final Issue 引用 working-only file。

Scripts 不做 semantic decisions、不連接平台、不保存狀態，也不發展成 workflow CLI。

## MVP validation scenarios

### Compact change

確認小型文案、bug、設定或局部 refactor 可以低摩擦完成，而且不載入不相關 context。

### Standard feature

確認一般功能可由 Profile 精準載入規範，並產生足以直接實作的 plan、AC 與 verification。

### Roadmap decomposition

確認大型目標能拆成多個可獨立交付 Issues，且 roadmap 不複製即時執行狀態。

### High-risk change

確認 migration、compatibility、安全、部署或跨系統工作會啟用必要 overlays、證據與 Issue split。

## MVP acceptance

- Bootstrap 維持短小，只提供 routing。
- 一般任務只載入少量 relevant refs。
- Project Profile 不複製完整 governance。
- Compact task 的規格成本不高於實作成本。
- Standard Issue 不要求 coding agent 補高階策略。
- 高風險工作會補足 safeguards 或被拆分。
- 新對話可從乾淨 active checkpoint 恢復。
- 最終 Issue 為乾淨、可獨立閱讀的 Markdown。
- Studio 不成為 Linear、GitHub、repo 或 ALC 的第二份狀態來源。

## Deferred evolution

有真實證據後才考慮：

- 單一薄 Skill 作為跨環境入口。
- Studio 內部 deterministic check scripts。
- CI lint。
- Consumer-specific thin adapters。
- 更正式的 schema versioning。

Spec-kit 的 clarify、constitution、plan、analyze 等概念可以作為設計參考，但 MVP 不採用或 fork 其完整多 artifact workflow。
