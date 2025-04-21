---
title: Danfo.js 入門與範例
date: 2025-04-23
author: DanielChou
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

<div class="result" markdown>

<div id="vue-danfo-demo">
  <h3>{{ title }}</h3>
  
  <!-- 學生成績資料表格 -->
  <div>
    <b>學生成績資料：</b>
    <table border="1" style="border-collapse: collapse; width: 100%; margin-top: 10px;">
      <thead>
        <tr>
          <th v-for="header in tableHeaders" :key="header">
            {{ header }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(student, index) in students" :key="index">
          <td>{{ student.姓名 }}</td>
          <td>{{ student.數學 }}</td>
          <td>{{ student.英文 }}</td>
          <td>{{ student.平均 }}</td>
        </tr>
      </tbody>
    </table>
    <p><small>使用 Vue 3 與 Danfo.js 風格處理資料並計算平均分數</small></p>
  </div>
  
  <!-- 統計資訊表格 -->
  <div style="margin-top: 20px;">
    <b>成績統計資訊：</b>
    <table border="1" style="border-collapse: collapse; width: 100%; margin-top: 10px;">
      <thead>
        <tr>
          <th>統計項目</th>
          <th>數學</th>
          <th>英文</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(stat, index) in statistics" :key="index">
          <td>{{ stat.name }}</td>
          <td>{{ stat.math }}</td>
          <td>{{ stat.english }}</td>
        </tr>
      </tbody>
    </table>
  </div>
  
  <!-- Danfo.js 代碼範例 -->
  <div style="margin-top: 20px;">
    <b>Danfo.js 代碼範例：</b>
    <pre style="background-color: #f5f5f5; padding: 10px; border-radius: 5px;">
// 創建 DataFrame
const df = new dfd.DataFrame({
  "姓名": ["小明", "小華", "小美"],
  "數學": [90, 80, 70],
  "英文": [85, 88, 92]
});

// 計算平均分數
df.addColumn({
  column: "平均",
  value: df["數學"].add(df["英文"]).div(2),
  inplace: true
});

// 顯示統計資訊
const mathMean = df["數學"].mean();
const englishMean = df["英文"].mean();
    </pre>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  // 確保 Vue 與 Danfo.js 已經載入
  if (typeof Vue === 'undefined') {
    document.getElementById('vue-danfo-demo').innerHTML = '<p style="color:red;">錯誤：Vue.js 未能正確載入</p>';
    return;
  }
  
  if (typeof dfd === 'undefined') {
    document.getElementById('vue-danfo-demo').innerHTML = '<p style="color:red;">錯誤：Danfo.js 未能正確載入</p>';
    return;
  }
  
  try {
    // 創建 Vue 應用
    const { createApp, ref } = Vue;
    
    createApp({
      data() {
        // 原始數據
        const rawData = {
          "姓名": ["小明", "小華", "小美"],
          "數學": [90, 80, 70],
          "英文": [85, 88, 92]
        };
        
        // 使用 Danfo.js 創建 DataFrame
        const df = new dfd.DataFrame(rawData);
        
        // 使用 Danfo.js 計算平均分數
        let avgScores = [];
        try {
          // 嘗試使用 Danfo.js 的 API 計算平均
          const mathSeries = df.column("數學");
          const englishSeries = df.column("英文");
          
          // 如果支援 add 和 div 方法
          if (typeof mathSeries.add === 'function' && typeof mathSeries.div === 'function') {
            const avgSeries = mathSeries.add(englishSeries).div(2);
            avgScores = avgSeries.values || Array.from(avgSeries);
          } else {
            // 如果不支援，手動計算
            avgScores = rawData["數學"].map((val, i) => 
              Math.round((val + rawData["英文"][i]) / 2)
            );
          }
        } catch (e) {
          // 如果 Danfo.js API 出錯，手動計算
          console.error("Danfo.js API error:", e);
          avgScores = rawData["數學"].map((val, i) => 
            Math.round((val + rawData["英文"][i]) / 2)
          );
        }
        
        // 使用 Danfo.js 計算統計資訊
        let mathMean, englishMean, mathMax, englishMax;
        
        try {
          // 嘗試使用 Danfo.js 的統計方法
          const mathSeries = df.column("數學");
          const englishSeries = df.column("英文");
          
          mathMean = mathSeries.mean ? mathSeries.mean().toFixed(2) : 
                   (rawData["數學"].reduce((a, b) => a + b, 0) / rawData["數學"].length).toFixed(2);
                   
          englishMean = englishSeries.mean ? englishSeries.mean().toFixed(2) : 
                      (rawData["英文"].reduce((a, b) => a + b, 0) / rawData["英文"].length).toFixed(2);
                      
          mathMax = mathSeries.max ? mathSeries.max() : Math.max(...rawData["數學"]);
          englishMax = englishSeries.max ? englishSeries.max() : Math.max(...rawData["英文"]);
        } catch (e) {
          // 如果 Danfo.js API 出錯，手動計算
          console.error("Danfo.js statistics API error:", e);
          const mathSum = rawData["數學"].reduce((a, b) => a + b, 0);
          const englishSum = rawData["英文"].reduce((a, b) => a + b, 0);
          mathMean = (mathSum / rawData["數學"].length).toFixed(2);
          englishMean = (englishSum / rawData["英文"].length).toFixed(2);
          mathMax = Math.max(...rawData["數學"]);
          englishMax = Math.max(...rawData["英文"]);
        }
        
        // 將數據轉換為學生對象陣列
        const students = [];
        for (let i = 0; i < rawData["姓名"].length; i++) {
          students.push({
            "姓名": rawData["姓名"][i],
            "數學": rawData["數學"][i],
            "英文": rawData["英文"][i],
            "平均": avgScores[i]
          });
        }
        
        return {
          title: '使用 Vue 3 與 Danfo.js 分析學生成績',
          tableHeaders: ['姓名', '數學', '英文', '平均'],
          students: students,
          statistics: [
            { name: '平均分', math: mathMean, english: englishMean },
            { name: '最高分', math: mathMax, english: englishMax }
          ],
          danfoLoaded: true
        };
      }
    }).mount('#vue-danfo-demo');
  } catch (error) {
    document.getElementById('vue-danfo-demo').innerHTML = `<p style="color:red;">使用 Vue 與 Danfo.js 時發生錯誤：${error.message}</p>`;
    console.error(error);
  }
});
</script>

</div>

以上程式碼會實際執行並顯示一個互動式表格。以下是程式碼部分：

```javascript
const data = {
  "姓名": ["小明", "小華", "小美"],
  "數學": [90, 80, 70],
  "英文": [85, 88, 92]
};
const df = new dfd.DataFrame(data);

// 計算每位同學平均分數
df.addColumn({
  column: "平均",
  value: df["數學"].add(df["英文"]).div(2),
  inplace: true
});
```

---

## 延伸閱讀
- [Danfo.js 官方文件](https://danfo.jsdata.org/)
- [pandas (Python)](https://pandas.pydata.org/)

---

> 本頁面示範如何在 MkDocs Material 部落格中嵌入 Danfo.js 並進行互動式資料分析展示。
