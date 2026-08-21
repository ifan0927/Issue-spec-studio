# Roadmap and Issue Decomposition

## Roadmap purpose

Roadmap 幫助 human 與 discussion AI 在一個 bounded goal／milestone 內管理 Issue boundaries、依賴與學習順序。

Coding agent 原則上不依賴 roadmap。它從獲派的 coding Issue execution contract 取得所需內容。

## Roadmap boundary

Roadmap 只涵蓋目前目標以及到下一個 meaningful learning point 所需的工作，不試圖預先展開完整產品未來。

Roadmap 保存：

- Goal 與 success condition。
- 已確認的 scope boundary。
- Issue decomposition。
- Issues 之間的必要 dependency。
- 為何此切割可以獨立驗證。
- 下一個需要重新規劃的 learning frontier。
- 仍會影響未來 Issue 的有效 decisions。

Roadmap 不保存：

- 每個 Issue 的完整規格。
- Linear 即時 status、priority 或 assignee。
- PR、CI、ALC execution logs。
- 歷史 roadmap 版本或被否決方案。
- 固定且沒有證據支持的長期 Issue 數量。

## Decomposition rules

優先切出多個小 Issue，只要每個 Issue 都：

- 交付一個有意義 outcome。
- 可在明確 repo state 上開始。
- 可獨立 review。
- 有自己的 AC 與 verification evidence。
- 失敗時不會迫使整個大型變更一起回退。
- 不要求 coding agent 推測其他 Issue 的策略。

應拆分的常見信號：

- 包含多個不同使用者 outcome。
- 同時跨越 preparation、migration、cutover 與 cleanup。
- 需要先探索或驗證未知技術前提。
- 一個 PR 無法合理 review。
- Verification 必須分不同環境或時間完成。
- 任何部分失敗都會使整個 Issue 無法安全交付。
- 需求變動可能只影響部分工作。

## Planning frontier

Roadmap 只詳細規劃到下一個會產生新資訊的點，例如：

- 完成 architecture spike。
- 確認 migration 可行性。
- 建立第一個垂直切片。
- 驗證 integration contract。
- 取得 production behavior evidence。

越過 frontier 的內容只保留 outcome 與暫定方向；取得新證據後再更新 roadmap。如此避免需求反覆時不斷維護龐大的遠期計畫。

## Change handling

- 尚未發布的 Issue 可在 roadmap review 中重新切割。
- 已發布但未執行的 Issue 需求改變時，以新 Issue 取代，不要求 template migration。
- 已在執行的 Issue 出現罕見重大變更時，由 human 停止 ALC／executor，再重新產生 Issue。
- Roadmap 只更新仍然有效的現況，不保留 change log；必要歷史由 Git 或 Linear 提供。
