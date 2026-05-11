# OrderManagement 專案規範

## 語言
- 所有回覆一律使用繁體中文

## 專案概述
簡易電商訂單系統，作為 Side Project 學習用途，展示 DDD + Clean Architecture 實踐能力。

## 技術棧
- .NET 10.0 Web API
- Clean Architecture 四層：Api → Application → Domain ← Infrastructure
- xUnit 測試專案（Domain.Tests、Application.Tests）
- 依賴方向：Api → Application → Domain，Api → Infrastructure → Domain

## 開發方法論

### 需求階段（AI 模擬 PM 流程）
1. 使用者先自己思考需求（不能跳過）
2. AI 模擬 PM，使用者模擬終端用戶，進行需求整理和邊界確認
3. 定義 Ubiquitous Language 並文件化保存
4. 基於需求文件 + UL 定義才開始架構設計
5. 完成標準：每個 Domain 都能透過文字清楚定義

### 測試策略（漸進式 TDD）
- 階段 1（前 1-2 個功能）：test-after，先學會 xUnit + Mock 語法
- 階段 2（第 3-4 個功能）：先列測試案例，再寫 code，最後補測試
- 階段 3（核心 Domain Logic）：完整 TDD（Red → Green → Refactor）
- 底線規則：每個功能 PR 必須包含測試，沒測試不能 merge
- 邊界條件：使用者自己先想一輪，再用 AI 討論補充

### ADR（架構決策紀錄）
- 位置：`docs/decisions/`
- 記錄重要架構選擇，包含 AI 建議了什麼、自己如何判斷
- 每週 1-2 則，不記錄 API 查詢等瑣事

## AI 角色定位
- 核心業務邏輯（訂單狀態機、庫存扣減等）引導使用者自己思考，不直接寫
- Boilerplate（Controller 接線、DTO mapping）可大量使用 AI
- 測試前幾個自己寫，之後可用 AI 輔助加速

## 設計原則
詳見上層目錄 `docs/避坑清單與設計原則.md`（5 條原則來自 DDD + PM 失敗覆盤）
