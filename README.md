# Zeabur Supabase Enhanced Template

## 基本認證指令

```bash
# 檢查登入狀態
npx zeabur auth status

# 登入 Zeabur 帳號
npx zeabur auth login

# 登出 Zeabur 帳號
npx zeabur auth logout

# 查看認證指令說明
npx zeabur auth --help
```

## 模板上架指令

```bash
# 上架模板
npx zeabur template create -f supabase-enhanced.yaml

# 部署模板
npx zeabur template deploy -f supabase-enhanced.yaml
```

## 模板部署指令

```bash
# 部署模板到指定專案
npx zeabur template deploy -f supabase-enhanced.yaml --project-id PROJECT_ID
```

## 模板管理指令

```bash
# 查看模板
npx zeabur template get -c CODE

# 更新模板
npx zeabur template update -c CODE -f supabase-enhanced.yaml

# 列出模板
npx zeabur template list

# 刪除模板
npx zeabur template delete -c CODE
```

## 快速開始

1. 確保已登入 Zeabur
```bash
npx zeabur auth login
```

2. 部署模板到專案
```bash
npx zeabur template deploy -f supabase-enhanced.yaml --project-id PROJECT_ID
```

3. 上架模板
```bash
npx zeabur template create -f supabase-enhanced.yaml
```