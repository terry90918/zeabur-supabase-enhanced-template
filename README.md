# Zeabur Supabase Enhanced Template

專為企業級部署設計的 Supabase 模板，提供完整的中文化支援和最佳實踐配置。

## ✨ 特色功能

- **完整的 Supabase 堆疊**: 包含 8 個核心服務
- **企業級安全**: 動態 JWT 金鑰生成，移除硬編碼憑證
- **最新版本**: 所有服務均已更新至 2025 年最新穩定版本
- **中文本地化**: 完整的繁體中文介面和文檔
- **一鍵部署**: 簡化的部署流程

## 🏗️ 服務架構

### 核心服務
- **Database**: PostgreSQL 15.8.1 (主要資料庫)
- **Kong**: API Gateway 2.8.1 (統一入口)
- **Studio**: Supabase 管理介面 (2025.06.30)
- **Auth**: GoTrue 身份驗證 (v2.176.1)
- **REST**: PostgREST API (v12.2.12)
- **Storage**: 檔案儲存服務 (v1.24.7)
- **Realtime**: 即時訂閱服務 (v2.34.47)
- **MinIO**: 物件儲存後端 (2025.01.01)

## 🔧 必要變數

部署時需要提供以下變數：
- `SUPABASE_DOMAIN`: Supabase Studio 的網域
- `ADMIN_USERNAME`: 管理員用戶名
- `ADMIN_PASSWORD`: 管理員密碼
- `ANON_KEY`: 匿名存取 JWT 金鑰
- `SERVICE_ROLE_KEY`: 服務角色 JWT 金鑰

## 🚀 快速開始

### 1. 認證登入
```bash
# 檢查登入狀態
npx zeabur auth status

# 登入 Zeabur 帳號
npx zeabur auth login
```

### 2. 部署模板
```bash
# 部署到新專案
npx zeabur template deploy -f supabase-enhanced.yaml

# 部署到指定專案
npx zeabur template deploy -f supabase-enhanced.yaml --project-id PROJECT_ID
```

### 3. 上架模板
```bash
# 上架新模板
npx zeabur template create -f supabase-enhanced.yaml

# 更新現有模板 (需要模板代碼)
npx zeabur template update -c CODE -f supabase-enhanced.yaml
```

## 📋 模板管理指令

```bash
# 查看模板詳情
npx zeabur template get -c CODE

# 列出所有模板
npx zeabur template list

# 刪除模板
npx zeabur template delete -c CODE

# 查看認證指令說明
npx zeabur auth --help
```

## 🔒 安全性改進

此版本包含重要的安全性改進：
- ✅ 移除硬編碼的 JWT Secret
- ✅ 動態生成 JWT 金鑰
- ✅ 使用變數管理敏感資訊
- ✅ 更新至最新安全版本

## 📝 更新紀錄

### v1.1.0 (2025.07.12)
- 更新所有服務至最新穩定版本
- 改進 JWT 金鑰安全性
- 統一中文本地化內容
- 新增動態 JWT Token 配置

### v1.0.0
- 初始版本發布
- 基本 Supabase 堆疊部署

## 📦 部署平台
[![Deploy on Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/templates/LXL5G9?referralCode=terry90918)