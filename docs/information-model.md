# Canonical Information Model

## Model shape

Studio 不使用單一巨型 schema，也不維護兩份平行的 human／machine representation。它由少量具有清楚 ownership 的 Markdown artifacts 組成，透過 references 連接。

```text
Target repo governance
        ↓ indexed by
Approved Project Profile
        ↓ constrains
Bounded Roadmap
        ↓ decomposes into
Active Issue discussion
        ↓ produces
Approved Markdown Issue
        ↓ published to
Linear / GitHub / other consumer
```

箭頭代表 navigation 或 constraint，不代表複製內容。

## Artifact responsibilities

### Target repo governance

保存 coding、architecture、test、CI、security、migration、observability、deployment、PR 與 Definition of Done 規則。這是 project behavior 的最高權威。

### Project Profile

保存 project identity 與 topic-to-reference routing。它可以指出 commands 與 canonical sources，但不得改寫或複製完整治理規則。

### Roadmap

保存一個 bounded goal 的 Issue boundaries、dependencies、planning frontier 與仍影響後續工作的 decisions。不保存完整 Issue 或即時執行狀態。

### Active checkpoint

保存尚在討論中的最小可恢復狀態：有效決策、active assumptions、blocking questions、目前 decomposition 與 next focus。它是 working-only、可持續改寫且必須定期清理。

### Candidate Issue

保存正在接受 ready review 的單一 execution contract。它不再保存探索過程，但在 human approval 前仍可修訂。

### Approved Issue

保存 frozen Goal、Scope、Requirements、Implementation Plan、Agent discretion、AC、Verification 與必要 safeguards。這是 Studio 的最終輸出。

### Published Issue

由 Linear、GitHub 或其他 issue manager 擁有。Status、priority、assignee 與 downstream progress 不回寫成 Studio canonical state。

### Validation review

保存候選 Issue 的 blockers、advisories 與 ready 判斷，只向 human 顯示，不合併到 final Issue，也不作為長期 artifact 保存。

### Quality event

只有下游發生 spec-related failure 時才建立的輕量事件。通常附著於 published Issue，而不是形成 Studio telemetry database。

## Information categories

| Category | Meaning | Allowed durable destination |
|---|---|---|
| Project rule | 對同 project 多個 Issues 有效的治理準則 | Target repo governance |
| Project mapping | Topic、ref、purpose、load trigger、authority | Project Profile |
| Milestone decision | 影響 Issue boundaries 或依賴的已批准決策 | Roadmap |
| User requirement | 必須交付的外部行為或限制 | Approved Issue |
| Confirmed decision | Human 已批准且影響 scope／strategy 的結果 | Roadmap 或 Issue，依適用範圍 |
| Active assumption | 尚未證實但目前用於推理的前提 | Active checkpoint only |
| Implementation guidance | 已決定的策略、boundary 與順序 | Issue |
| Agent discretion | 不影響契約的低階選擇空間 | Issue |
| Open question | 會影響方案、尚待回答的問題 | Active checkpoint only |
| Execution state | Status、PR、CI、runtime progress | Linear／GitHub／ALC |

同一資訊只保留一個 canonical owner。其他 artifacts 只使用 reference 或任務必要的精簡衍生結果。

## Decision scope

決策放置位置由影響範圍決定：

- 影響整個 project：先更新 project governance。
- 影響目前 milestone 多個 Issues：放入 roadmap。
- 只影響單一 Issue：直接寫入 Issue。
- 尚未批准或仍可能改變：只放 active checkpoint。

Issue 不得把 project-level policy 降格為單一 Issue decision，也不得用 out-of-scope、constraint 或 implementation note 規避 project governance。

## Discussion ledger behavior

Discussion AI 可以在 active checkpoint 內維護目前有效決策，但不建立逐輪 decision log。

Ledger／decision view 預設不每輪展示，只在以下情況向 human 顯示：

- 既有決策被修改或取代。
- 需要 human approval。
- Human 主動要求查看。

顯示的是目前有效結果與變更影響，不是完整聊天歷史。

## Versioning

- Issue 使用低干擾 `spec_version` marker，以便日後辨識其 information model 版本。
- Rules、templates 與 Project Profile 的歷史由 Git 管理。
- 已批准或發布的 Issue 不因 template 更新而 migration。
- 新版本 template 只影響之後建立的新 Issue。
- 不在 MVP 建立 schema migration engine。

## Freshness and drift

Studio 不透過複製 repo 狀態防止 drift，而是在需要時重新查詢 authority source。

### Before ready review

- Targeted re-read 與 Issue 相關的 Project Profile refs。
- 驗證會影響 plan 的 repo assumptions。
- 確認 commands、boundaries 與 dependencies 仍成立。
- 若 project policy 已改變，重新 review candidate Issue。

### After publication

- Published Issue 不持續與 Studio draft 同步。
- Executor 若發現 Issue 與當前 repo state 或 governance 衝突，應停止並回報 evidence。
- 是否綁定 exact commit／HEAD 由 downstream execution system 決定，不放入 consumer-neutral core。

### Project growth

- Relevant governance change 觸發 Project Profile update proposal。
- Human approval 後落地，再做 affected-area re-scan。
- 不定期全量複製 repo context，也不建立背景同步 service。

## Traceability

Traceability 以最小必要關係表達：

- Project Profile ref 指向 canonical project rule。
- Roadmap item 指向 published Issue ID（發布後）。
- Requirement 與 AC 使用簡單文字對應或 identifiers。
- Verification 指向能證明 AC 的 test、command 或 observable result。

不要求大型 traceability matrix。當關係已能由短 Issue 清楚理解時，不增加額外標記。
