# DanielChou的部落格

這是我的個人部落格專案，使用 MkDocs 建置，並通過 GitHub Pages 發布。

## 專案結構

```
.
├── docs/
│   ├── index.md           # 首頁
│   ├── blog/
│   │   ├── index.md       # 文章列表頁面
│   │   ├── categories.md  # 分類頁面 (已移動到此處)
│   │   └── posts/         # 部落格文章
│   │       └── ....md
│   ├── tags.md            # 標籤頁面
│   ├── authors.md         # 作者資訊
│   └── ...                # 其他頁面或資源
├── overrides/             # Material 主題自定義
├── assets/                # 靜態資源 (圖片、CSS等)
├── mkdocs.yml             # MkDocs 配置文件
├── requirements.txt       # Python 依賴
└── README.md              # 本文件
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

## 最近更新

### 2025-03-30
- 擴充 Material for MkDocs 功能展示文章：
  - 新增多種 Grid 布局範例，包含：
    - 基本卡片展示
    - 產品功能展示
    - 團隊成員展示
    - 服務項目展示

### 2025-03-28
- 新增兩篇技術比較文章：
  - 前端開發中的條件渲染比較
  - 不同程式語言的迴圈實現方式
- 新增程式碼展示功能，支援多種程式語言（JS、CSS、HTML、偽代碼）的 Tab 切換展示

## 相關連結

- 部落格網址：https://danielchou.github.io/blog
- MkDocs 文檔：https://www.mkdocs.org/
- Material for MkDocs：https://squidfunk.github.io/mkdocs-material/
