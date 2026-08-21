# Project Onboarding

## Purpose

Project onboarding 建立一份已批准、可供 discussion AI 導航的 Project Profile。Profile 是 project governance 的索引，不是另一份 constitution。

## Minimum governed project context

依專案實際需要，至少能定位：

- Project goal 與 domain。
- Repository structure 與主要 modules。
- Agent instructions，例如 `AGENTS.md`。
- Coding style 與 architecture boundaries。
- Build、test、lint 與 verification commands。
- Branch、PR 與 review conventions。
- Project-wide Definition of Done。
- 適用的 security、migration、observability、deployment 與 rollback 規則。

不是每個專案都必須建立所有類別文件；不存在或不適用時保持簡單，不建立空洞規範。

## New project path

對從零建立的 project：

1. 確認 project goal、domain 與預期 boundaries。
2. 建立最低必要 governance，包括 agent instructions、commands、coding conventions 與 DoD。
3. 對有實際風險的領域建立 security、migration、observability 或 deployment 規則。
4. 產生只含 references 與 load triggers 的 Project Profile。
5. Human review and approval。
6. Profile 與治理文件落地後，才用它們產生 coding Issues。

## Existing project path

對已有 code 與規範的 project：

1. Discussion AI 做一次完整 repository discovery。
2. 找出明示與隱含的規則來源，包括 agent instructions、README、CI、build configuration、tests、architecture docs 與慣例。
3. 建立 mapping proposal，指出 canonical source、load trigger、重複、缺漏與衝突。
4. Human review and approval。
5. 將必要治理補充及 Project Profile 落地到 target repo。
6. 從此 discussion AI 以 Profile 導航，不在每個 Issue 重新完整掃描。

首次 discovery 的掃描結果在批准前只是 proposal，不自動成為規範。批准落地後才開始治理後續 Issues。

## Zero、low and full configuration

### Zero configuration

適用於簡單或實驗性 project。AI 讀取現有 repo evidence，以一般軟體工程準則形成 Issue，但不得假裝存在未定義的 project policy。

### Low configuration

建議的預設路徑。建立一份精簡 Project Profile，指向既有 `AGENTS.md`、README、commands、CI 與少量 architecture docs。

### Full configuration

適用於長期治理或高風險 project。補齊明確 architecture boundaries、security、migration、observability、deployment、rollback 與 project-wide DoD references。

Configuration 深度由實際 project 風險驅動，不以模板完整度為目標。

## Profile update

Project 成長時採輕量更新循環：

```text
偵測 relevant change → mapping/policy proposal → human approval → land in repo → targeted re-scan
```

- 單純 path、command 或 mapping 維護可以批次批准。
- 改變行為準則、architecture boundary、DoD 或 safety policy 必須明確批准。
- 依賴新 policy 的 Issue 必須等 policy 先落地。
- 更新後只重掃受影響領域，不重新掃描整個 repo。

## Conflict precedence

優先順序為：

1. Target repo 已批准的 project governance。
2. 已批准 Project Profile 所指向的 canonical sources。
3. 已批准 roadmap decisions。
4. Issue-level requirements and plan。
5. Working assumptions and suggestions。

若 Issue 與 project governance 衝突，Issue 不得覆寫。Discussion AI 應將其標為 blocker，提出獨立的 project-level change，待批准落地後再產生 Issue。
