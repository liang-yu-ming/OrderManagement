# OrderManagement — 簡易電商訂單系統

練習用 Side Project，以 DDD + Clean Architecture 實作電商訂單管理系統。

## 技術棧

- ASP.NET Core 10.0 Web API
- Entity Framework Core + SQL Server
- xUnit + Moq

## 專案結構

```
src/
├── OrderManagement.Api              # Web API 進入點、Controller、DI 設定
├── OrderManagement.Application      # 用例層：Service、DTO、介面定義
├── OrderManagement.Domain           # 核心層：Entity、Value Object、Domain Event
└── OrderManagement.Infrastructure   # 基礎設施：EF Core、外部服務實作

tests/
├── OrderManagement.Domain.Tests
└── OrderManagement.Application.Tests

docs/
└── decisions/                       # Architecture Decision Records (ADR)
```

## 依賴方向

```
Api → Application → Domain
Api → Infrastructure → Domain
```

## 預計功能

- [ ] 使用者註冊 / 認證（JWT）
- [ ] 商品管理 CRUD
- [ ] 訂單建立（含庫存檢查、價格計算、併發安全的庫存扣減）
- [ ] 訂單狀態流轉（State Pattern）
- [ ] 簡易事件機制（Domain Events）
