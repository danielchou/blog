---
title: Danfo.js 入門與範例
date: 2025-04-23
categories:
  - JavaScript
  - 資料分析
  - Danfo.js
  - 前端
tags:
  - danfojs
  - dataframe
  - js
---

# Danfo.js 入門與範例

[Danfo.js](https://danfo.jsdata.org/) 是一個用於 JavaScript 的高效資料處理與分析函式庫，靈感來自 Python 的 pandas。它讓你在瀏覽器或 Node.js 中也能輕鬆進行資料科學與資料處理。

<!-- more -->

## 特色
- 與 pandas 類似的 API，容易上手
- 支援 DataFrame 與 Series 操作
- 可在瀏覽器直接進行資料分析
- 適合前端互動式資料應用

!!! note
    這是一個 **筆記** 提示框。

??? example "點擊展開範例"
    這是一個可以摺疊的提示框。


## 安裝與引用

你可以直接在 HTML 中用 CDN 引入 Danfo.js：

```html
<script src="https://cdn.jsdelivr.net/npm/danfojs@1.4.0/lib/bundle.min.js"></script>
```

---

## 基本範例

以下展示如何在網頁中用 Danfo.js 建立 DataFrame 並進行基本操作：

<div id="danfo-demo"></div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const data = {
    "姓名": ["小明", "小華", "小美"],
    "數學": [90, 80, 70],
    "英文": [85, 88, 92]
  };
  const df = new dfd.DataFrame(data);

  // 顯示 DataFrame
  let html = '<b>原始資料：</b>';
  html += df.toHTML();

  // 計算每位同學平均分數
  df.addColumn({
    column: "平均",
    value: df["數學"].add(df["英文"]).div(2),
    inplace: true
  });
  html += '<br><b>加入平均分數後：</b>';
  html += df.toHTML();

  document.getElementById('danfo-demo').innerHTML = html;
});
</script>

---

## 延伸閱讀
- [Danfo.js 官方文件](https://danfo.jsdata.org/)
- [pandas (Python)](https://pandas.pydata.org/)

---

> 本頁面示範如何在 MkDocs Material 部落格中嵌入 Danfo.js 並進行互動式資料分析展示。
