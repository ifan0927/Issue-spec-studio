# Context Hygiene Contract

## Principle

Context 採 pull-based progressive disclosure：bootstrap 只負責導航，Project Profile 只負責 mapping，discussion AI 只在任務需要時載入必要 canonical sources。

不得把「有 reference」理解成「必須遞迴讀取所有 reference」。

## Context layers

### L0 — Bootstrap

固定載入，但只包含目的、基本循環、authority rule 與 reference routing。

### L1 — Project Profile

選定 target project 後載入。Profile 告訴 AI 哪些 topic 對應哪些 canonical source，以及何時需要讀取。

### L2 — Task-relevant governance

依 task trigger 載入，例如 authentication、API compatibility、migration、testing 或 deployment 規範。

### L3 — Repository evidence

只有需要確認現況、驗證 assumption 或形成 implementation plan 時才讀實際 source、tests、configuration 或 CI。

Existing project 首次 onboarding 可以完整掃描；日常 authoring 不可無目的重掃完整 repository。

## Reference contract

每個重要 ref 必須能辨識：

- `Ref`：可定位的文件或 source。
- `Purpose`：它提供什麼決策資訊。
- `Load when`：什麼任務條件才需要載入。
- `Authority`：canonical、supporting evidence 或 working-only。

Ref 應指向最接近原始權威的來源，不複製其完整內容。Leaf document 應單一責任、乾淨、可直接理解。

## Prohibited reference patterns

- Bootstrap 直接載入所有 rules 和 examples。
- Project Profile 複製完整 coding guide。
- Roadmap 複製完整 Issues。
- Issue 複製 project-wide DoD 或一般 test commands。
- Local file 複製 Linear 即時 status。
- A 引用 B 後自動展開 B 的全部 references。
- 以多層 redirect 保留已失效文件路徑。
- 最終 Issue 引用 `active.md`、scratch notes 或 validation report。

## Active checkpoint

`active.md` 只保存恢復當前 discussion 所需的最小有效狀態：

- Current objective
- Confirmed decisions
- Active assumptions
- Blocking questions
- Current decomposition
- Next discussion focus

它不是 transcript、timeline、完整 brainstorm、已否決方案集合或永久 decision archive。

## Compaction rules

### Clarification 完成

- 移除已回答 questions。
- 將有效答案提升為 confirmed decisions。
- 刪除被否決方案。
- 移除已失效 assumptions。

### Decomposition 完成

- 將穩定 Issue boundaries 移至 roadmap。
- Active 只留下目前正在細化的 Issue。
- 不複製其他 Issues 的完整內容。

### Candidate issue 完成

- 已進入 draft 的內容不在 active 重複。
- Active 只保留未解 blocker、待批准 decision 與 draft ref。

### Approval／publication 完成

- 清空該 active work。
- Roadmap 只保留仍影響後續規劃的結構性資訊。
- 不預設建立 active archive。

Git history、published Issue 與 authority systems 已提供必要歷史，不在 Studio 再建立一份鏡像。

## Roadmap hygiene

Roadmap 只保存目前 bounded goal、Issue boundaries、dependencies、learning frontier 與仍有效 decisions。Linear status、PR、CI、ALC logs 與過期計畫不進入 roadmap。

## Maintenance checks

未來若實際使用證明有需要，可加入 Studio 內部 scripts 檢查：

- Broken local references。
- 缺少 purpose／load trigger 的 refs。
- Bootstrap 直接引用過多內容。
- Final Issue 引用 working-only artifact。
- Active 出現 transcript/history sections。
- Profile 大量複製 governance text。

Scripts 只做 deterministic checks，不決定該載入哪些語意 context。
