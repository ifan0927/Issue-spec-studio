# Operating Model

## Roles

### Human

- 決定產品目標與重要 trade-off。
- 回答真正會改變方案的 clarifying questions。
- 批准 Project Profile、project policy change、roadmap 與最終 Issue。
- 必要時停止下游執行並要求以新 Issue 取代。

### Discussion AI

- 載入必要 project context。
- 分析需求缺漏、歧義、衝突與風險。
- 維護 assumption register 與 confirmed decisions 的當前有效狀態。
- 判斷 compact 或 standard authoring depth。
- 拆分過大需求並維護 roadmap。
- 形成具體 implementation plan。
- 執行 semantic validation 與 coding-ready review。
- 產生標準 Markdown output。

### Coding agent

- 遵循 target repo 的治理規則與最終 Issue。
- 依 Issue 已決定的策略、邊界與順序實作。
- 在明確 agent discretion 內選擇低階實作細節。
- 發現計畫不可行、規格矛盾或需要高階決策時停止並回報 spec defect。

### Downstream consumer

Linear、GitHub、ALC 或其他系統接收最終 Issue。它們可以管理發布、執行與狀態，但不得成為 Studio canonical information model 的來源。

## Authoring stages

這些是 discussion AI 的工作階段，不是必須持久化的狀態機，也不要求每階段產生獨立 artifact。

### Analyze

- 重述真正要解決的 outcome。
- 比對 project context 與 repo 現況。
- 找出缺漏、矛盾、不可驗證敘述與風險。
- 判斷需求是否過大或需要先拆分。

### Clarify

- 只詢問會改變 scope、strategy、safety、verification 或 Issue split 的問題。
- 將回答轉成 confirmed decision。
- 不把已解決問題保留到最終 Issue。

### Decompose

- 將大型需求切成多個單一 outcome Issues。
- 確認每個 Issue 可獨立安全執行、review 與驗證。
- 將依賴與學習順序記入 bounded roadmap。

### Plan

- 決定實作方向、重要 boundaries、順序與必要 integration points。
- 明示 coding agent 可以自行決定的部分。
- 不指定沒有必要的低階程式細節。

### Review and approve

- 執行 semantic validation 與 ready gate。
- 對 human 顯示 blockers、advisories 與 ready 結論。
- Human approval 後凍結輸出。
- 最終 Issue 不包含內部 validation report。

## Lightweight lifecycle

概念上的 artifact 狀態為：

```text
working discussion → candidate issue → approved issue → published issue
```

不建立 workflow database 或正式狀態機。

- Working discussion 可持續壓縮與改寫。
- Candidate issue 尚可依 review 修訂。
- Approved issue 已凍結，等待發布。
- Published issue 由外部 issue manager 管理。

已批准或發布的 Issue 不進行模板 migration。需求改變時產生新的或 superseding Issue。若極少數情況下 Issue 已由 ALC 執行，human 手動停止執行後再重新產生，不要求 Studio 或 ALC 支援複雜 restart lifecycle。

## Approval points

- Existing repo 首次 Project Profile mapping。
- Project policy change。
- Roadmap 的 goal、Issue boundaries 與重要 dependency。
- 最終 coding-ready Issue。

Mapping maintenance 可以批次批准；真正改變規範的 policy change 必須先落地，再產生依賴新規則的 Issue。
