# DanielChou的部落格

### 文章存放路徑
- 所有文章請放在 `docs/posts/` 目錄下，並以 Markdown 檔案儲存。
- `mkdocs.yml` 的 `post_dir` 請設為 `posts`。
- 本專案使用 `mkdocs-blogging-plugin` 作為部落格自動化插件。
- 重要頁面：
  - `docs/blog/index.md`：部落格首頁，自動列出所有文章
  - `docs/categories.md`：自動產生分類清單
  - `docs/archive.md`：自動產生歸檔清單

## Front Matter 標準格式
每篇文章必須有 YAML front matter，範例如下：

```yaml
---
title: 文章標題
date: 2025-04-21
categories:
  - 技術
  - 前端
tags:
  - js
  - markdown
---
```

- `date` 必填，格式建議為 `YYYY-MM-DD`
- `categories`、`tags` 用 YAML 陣列

## blog/index.md 用法

```markdown
---
title: 文章列表
---

# 文章列表

歡迎來到部落格文章索引，以下自動列出所有文章：

{{ blog_content }}
```

## 自動分類/歸檔/標籤
- `docs/categories.md` 內容：
  ```markdown
  ---
  title: 文章分類
  ---
  [Categories]
  ```
- `docs/archive.md` 內容：
  ```markdown
  ---
  title: 文章歸檔
  ---
  [Archive]
  ```

## mkdocs.yml nav 配置建議

```yaml
nav:
  - 首頁: index.md
  - 文章: blog/index.md
  - 歸檔: archive.md
  - 分類: categories.md
  - 標籤: tags.md
  - 作者: authors.md
```

## 注意事項
- 只需將文章放到 `docs/posts/`，不需手動加入 nav
- 每篇文章都需有 `date` 欄位，否則 blog plugin 會報錯
- 分類、標籤、歸檔、作者頁面皆自動產生

---

本專案採用 MkDocs 1.6+ 與 [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) 佈景主題打造，並採用 MkDocs 內建 blog 功能。

## 專案結構

```
.
├── docs/
│   ├── index.md           # 首頁
│   ├── blog/
│   │   ├── index.md       # 文章列表頁面
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
