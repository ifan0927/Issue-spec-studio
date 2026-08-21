<!-- issue-spec: v1 -->

# 新增管理端停權使用者 API

## Goal

讓具備管理權限的操作者能停權使用者，並確保被停權帳號的既有登入 session 失效且操作留下 audit record。

## Context

系統目前可以停用新登入，但沒有單一管理端操作同時更新使用者狀態、撤銷既有 session 並記錄操作者。此 Issue 只建立 backend 行為；管理介面不在本次範圍。

## Scope

- 新增符合現有 admin API conventions 的停權 endpoint。
- 將目標使用者狀態改為 suspended。
- 使目標使用者既有 sessions 失效。
- 記錄 actor、target、timestamp 與 action result。
- 補足 authorization、domain、API 與 session invalidation 測試。

## Out of scope

- 管理端 UI。
- 自動通知被停權使用者。
- 刪除或匿名化使用者資料。
- 建立新的全域 session infrastructure。

## Requirements

- 只有符合現有 admin authorization policy 的操作者可以執行。
- 對不存在或已停權的使用者，回應必須符合現有 API error／idempotency conventions。
- 成功回應前，使用者狀態更新與 session invalidation 必須達到專案既有一致性要求。
- 無論成功或拒絕，敏感操作都必須依現有 audit policy 留下必要紀錄。

## Applicable project references

- `<project-profile: admin-api>`：admin endpoint 與 authorization conventions。
- `<project-profile: error-handling>`：公開錯誤 mapping。
- `<project-profile: session-management>`：session revocation 方法。
- `<project-profile: audit>`：敏感操作紀錄要求。
- `<project-profile: verification>`：backend test commands。

## Implementation Plan

1. 在既有 admin API boundary 增加停權操作，沿用現有 authorization middleware。
2. 透過既有 user domain/service boundary 驗證狀態轉換並保存 suspended 狀態。
3. 使用既有 session revocation abstraction 撤銷目標使用者的 active sessions；不要建立平行機制。
4. 依 audit policy 記錄 actor、target、result 與必要 request context。
5. 透過既有 public error mapping 回傳不存在、未授權及無效狀態結果。
6. 補足 domain、authorization、endpoint、session revocation 與 audit coverage。

## Agent discretion

- 可依現有 module conventions 決定 handler、service method 與 test fixture 的局部命名。
- 可在不改變既有 public contract 的前提下選擇測試資料建立方式。

## Acceptance Criteria

- [ ] 合法 admin request 會將 active 使用者改為 suspended。
- [ ] 停權完成後，該使用者既有 active sessions 無法再通過 authentication。
- [ ] 非管理者無法執行停權，且使用者狀態與 sessions 不變。
- [ ] 不存在與已停權使用者的結果符合現有 error／idempotency conventions。
- [ ] 操作依 audit policy 記錄 actor、target、timestamp 與 result。
- [ ] 停權不會刪除使用者 domain data。

## Verification

- 執行 Project Profile 指定的 backend test 與 lint commands。
- Domain test：允許及拒絕的狀態轉換。
- Authorization test：admin 與 non-admin caller。
- Integration test：成功停權後既有 session 被拒絕。
- Audit test：成功與拒絕路徑產生符合 policy 的紀錄。

## Risks and safeguards

- Session invalidation 與狀態保存若無法符合 project consistency rule，不得退化成 eventual best effort；停止並回報需要的 architecture decision。
- Audit log 不得包含 credential、token 或其他 policy 禁止的敏感資料。

## Issue-specific Definition of Done

- 停權 endpoint、session invalidation 與 audit evidence 必須在同一組 verification results 中可追溯。

## Execution fallback

若現有 session abstraction 不支援 user-level revocation，停止並提供 repo evidence，回報需要前置 Issue；不要在本 Issue 自行建立新的 session architecture。
