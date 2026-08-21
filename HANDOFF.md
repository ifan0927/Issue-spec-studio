# Handoff

## Current state

本 repository 已建立 Issue Spec Studio 的 product design baseline v0.1。內容只包含目前已確認的決策與操作準則，沒有保存 brainstorm 過程或方案比較。

目前尚未進入 implementation。Repository 中沒有正式 CLI、service、database、renderer、Skill 或平台發布整合。

## 已確定的產品形態

- 單人使用、local-first 的文件型 Spec Studio。
- Discussion AI 是主要操作介面與語意推理者。
- Markdown 是 canonical human-readable artifact。
- Repo-level bootstrap instruction 只載入極小入口，再以 refs 按需取得其他 project context。
- Target repo 保存治理規則與 Project Profile；Studio 不複製完整治理內容。
- Linear 預期是主要 Issue 管理平台，但發布不屬於核心能力。
- ALC 只是 coding-ready Issue 的下游 consumer，不影響 Studio 核心模型。
- Studio 內部可在有重複錯誤證據後加入小型檢查 scripts，但不先建立產品級 CLI。

## 下一個建議工作階段

下一階段仍應是設計驗證，不是直接建立完整工具：

1. 依 `templates/` 建立 paper prototype。
2. 分別走查 compact 小修改、standard 功能、大需求拆分、高風險修改。
3. 記錄缺漏、過量 context、不可驗證 AC、過大 Issue 與清理失敗。
4. 修訂 rules 與 templates。
5. 通過 MVP acceptance 後才決定需要哪些最小實作。

## 接手限制

- 不要把目前文件改寫成討論日誌。
- 不要為尚未發生的 edge case 新增 framework。
- 不要把 ALC execution lifecycle 納入本產品。
- 不要建立與 Linear 或 target repo 重複的狀態來源。
- 不要讓 bootstrap 或 Project Profile 演變成完整知識庫。

## 尚未完成但已排定的設計驗證

- 使用真實 repo 驗證 Project Profile onboarding。
- 以真實需求測試 compact 與 standard Issue template。
- 驗證 roadmap 拆分能否維持 bounded planning frontier。
- 驗證長對話／新對話可否只靠乾淨 active checkpoint 恢復。
- 收集是否真的需要 deterministic check script 的證據。
