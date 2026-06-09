# Shopping Cart 專案規範

## 技術棧
- 後端：Node.js 20 + Express + PostgreSQL
- 前端：React 18 + Vite + TypeScript
- 測試：Vitest + Supertest（後端）、Playwright（E2E）

## 命名規範
- API 路徑：小寫 kebab-case（/api/cart-items）
- 後端模組：檔名 kebab-case；函式與變數 camelCase
- React 元件：PascalCase；hooks：use 前綴

## 禁止行為
- 禁止在 Node.js 程式碼中 hardcode secret key 或直接信任客戶端傳入金額
- 禁止直接修改 spec.md，需先與人類確認

## 常用指令
- 啟動後端：`npm run server`
- 啟動前端：`cd frontend && npm run dev`
- 執行測試：`npm run test:server`

## 2. AI 行為準則 (Core Principles)
- **寫程式前先思考**：實作前務必釐清所有模糊地帶，不盲目猜測或替使用者做決定。若有更簡單的解法應主動提出。
- **保持精簡 (KISS)**：只用最少的程式碼解決當下問題，拒絕過度工程化或引入不必要的抽象層。
- **手術式修改**：只精準更動與需求直接相關的檔案，絕對不去「順手重構」或更改未損壞的程式碼及排版。
- **繁體中文溝通**：所有回答與程式碼註解（Explain Why）皆必須使用「繁體中文」。