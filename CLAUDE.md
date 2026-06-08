# CLAUDE.md

Shopping Cart 專案。本檔供 Claude Code 自動載入；完整規格見 [prd.md](prd.md)。

## 專案概觀

開發前請先閱讀 [prd.md](prd.md)。重點摘要：

- **技術棧**：後端 Node.js 20 + Express + PostgreSQL（Docker 啟動）；前端 React + Vite。
- **核心實體**：Product（商品）、Cart（購物車）、CartItem（購物車明細）。
- **功能範圍**：瀏覽商品並加入購物車；加入相同商品自動合併數量；數量改為 0 則自動移除；結帳填收件資料後清空購物車。

## 關鍵規則

- **購物車合計一律由伺服器計算，不接受客戶端傳入金額。**

## 目前狀態

> ⚠️ 應用程式碼（後端 / 前端）尚未建立。目前 repo 僅有 PostgreSQL 18 的 Docker 設定。

## 資料庫

PostgreSQL 18 透過 Docker 運行（見 [docker-compose.yml](docker-compose.yml)）。

```bash
docker compose up -d        # 啟動
docker compose ps           # 狀態
docker compose down         # 停止
```

連線資訊（密碼可於 `.env` 覆寫，見 [.env.example](.env.example)）：

```
postgresql://postgres:postgres@localhost:5432/shoppingcart
```

| Host | Port | Database | User |
|------|------|----------|------|
| localhost | 5432 | shoppingcart | postgres |
