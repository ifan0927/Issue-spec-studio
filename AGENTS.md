# Agent Bootstrap

1. 先讀取 `START_HERE.md`，不要一開始遞迴讀取所有 `docs/`、`templates/` 或 target repository。
2. 依當前任務與 `START_HERE.md` 的 load trigger，只讀必要 reference。
3. 本 repository 的 durable 文件只保存已批准的現行決策；不要加入 brainstorm transcript、被淘汰方案或臨時工作狀態。
4. 要修改產品邊界、canonical information model、authority hierarchy 或 coding-ready gate 前，先取得 human approval。
5. 暫時工作內容放在 `work/`，並遵守 `docs/context-hygiene.md` 的壓縮與清理規則。
6. 尚未獲得實作授權時，不建立 CLI、service、database、TUI、renderer framework 或平台整合。
