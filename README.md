# DanielChou的部落格

這是我的個人部落格專案，使用 MkDocs 建置，並通過 GitHub Pages 發布。

## 專案結構

```
blog/
├── docs/                # 網站內容
│   ├── assets/         # 圖片等資源
│   ├── posts/          # 部落格文章
│   └── index.md        # 首頁
├── overrides/          # 主題客製化
├── .github/workflows/  # GitHub Actions
└── mkdocs.yml         # 配置文件
```

## 本地開發

1. 克隆專案：
```bash
git clone https://github.com/danielchou/blog.git
cd blog
```

2. 安裝依賴：
```bash
pip install mkdocs-material
```

3. 本地預覽：
```bash
mkdocs serve
```

4. 瀏覽 http://127.0.0.1:8000

## 部署

- 推送到 main 分支會自動觸發部署
- 網站會發布到 https://danielchou.github.io/blog

## 寫作指南

1. 在 `docs/posts/` 目錄下建立新的 .md 文件
2. 文件名格式：`YYYY-MM-DD-title.md`
3. 文件開頭加入 Front Matter：
```yaml
---
date: YYYY-MM-DD
categories:
  - 分類名稱
tags:
  - 標籤1
  - 標籤2
---
```

## 相關連結

- 部落格網址：https://danielchou.github.io/blog
- MkDocs 文檔：https://www.mkdocs.org/
- Material for MkDocs：https://squidfunk.github.io/mkdocs-material/
