# shoppingcart

PostgreSQL 18 資料庫的 Docker 設定，供購物車（shopping cart）專案使用。

## 需求

- [Docker](https://www.docker.com/) / Docker Desktop

## 快速開始

```bash
# 啟動資料庫
docker compose up -d

# 查看狀態
docker compose ps

# 進入 psql
docker exec -it shoppingcart-postgres psql -U postgres -d shoppingcart

# 停止
docker compose down
```

## 連線資訊

| 項目 | 值 |
|------|-----|
| Host | `localhost` |
| Port | `5432` |
| Database | `shoppingcart` |
| User | `postgres` |
| Password | `postgres`（預設，請於 `.env` 覆寫） |

連線字串：

```
postgresql://postgres:postgres@localhost:5432/shoppingcart
```

## 設定密碼

預設密碼僅供本機開發。請建立 `.env` 檔覆寫（`.env` 已被 `.gitignore` 忽略，不會進版控）：

```env
POSTGRES_PASSWORD=your-strong-password
```

## 備註

- PostgreSQL 18+ 變更了資料目錄掛載慣例，需掛載 `/var/lib/postgresql`（而非舊版的 `/var/lib/postgresql/data`），PostgreSQL 會自行在底下建立 major-version 子目錄，以支援 `pg_upgrade`。
- 資料持久化於 Docker named volume `shoppingcart_pgdata`。
