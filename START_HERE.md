# Start Here

本文件是 Issue Spec Studio 的最小 bootstrap。它只負責導航，不承載完整產品知識。

## 基本工作循環

1. 確認正在處理的 target project 與本輪目標。
2. 讀取該 project 已批准的 Project Profile。
3. 依 Profile 的 load trigger 讀取必要治理與 repo reference。
4. 在對話中執行 analyze、clarify、decompose、plan。
5. 維護最小 active checkpoint；每個階段完成後立即壓縮。
6. 形成候選 Markdown Issue，執行 coding-ready review。
7. 取得 human approval 後輸出；發布由使用者或當前對話 AI 處理。

## Reference routing

只在符合 trigger 時讀取下列文件；不得因為存在連結就全部展開。

| 當前任務 | 必要 reference |
|---|---|
| 理解產品邊界、責任與非目標 | `docs/product-boundary.md` |
| 理解 artifacts、ownership、版本與 freshness | `docs/information-model.md` |
| 理解端到端工作方式與 artifact lifecycle | `docs/operating-model.md` |
| 設計或檢查 canonical Issue | `docs/issue-model.md`、`docs/ready-gate.md` |
| 拆分需求或維護 milestone roadmap | `docs/roadmap-and-decomposition.md` |
| 新專案或既有 repo onboarding | `docs/project-onboarding.md` |
| 載入 context、維護 reference 或清理 active work | `docs/context-hygiene.md` |
| 發布、consumer、ALC 或未來 adapter 邊界 | `docs/consumer-boundaries.md` |
| 規格品質、失敗事件或衡量方式 | `docs/quality-measurement.md` |
| 決定 MVP 與後續工作 | `docs/mvp.md`、`HANDOFF.md` |

## Authority rule

Target repo 的已批准治理規則高於 roadmap 與 Issue。發現衝突時停止 ready 判定，先提出 project-level change；不得在 Issue 中例外覆寫。

## Output rule

最終輸出是單一、乾淨、可獨立閱讀的 Markdown Issue。不得包含 unresolved questions、討論紀錄、validation report 或已否決方案。
