---
date: 2025-03-30
title: 示範 DataTable 基本用法
description: 展示 Material for MkDocs 的Data Table 擴展功能
# authors:
#   - danielchou
categories:
  - mkdocs
tags:
  - Markdown
  - DataTable
  - 教學
---


# 示範 DataTable 基本用法

本文將示範使用markdown寫出Table用法，包含排序。

<!-- more -->

## 基本型

| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |

## 文字對齊

### 這是文字靠左

| Method      | Description                          |
| :---------- | :----------------------------------- |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |

### 這是文字置中。

| Method      | Description                          |
| :---------: | :----------------------------------: |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |


## 進階用法

### 排序

| Method      | Description                          |
| ----------- | ------------------------------------ |
| `GET`       | :material-check:     Fetch resource  |
| `PUT`       | :material-check-all: Update resource |
| `DELETE`    | :material-close:     Delete resource |

### CSV檔案匯入

參考 https://timvink.github.io/mkdocs-table-reader-plugin/readers/

{{ read_csv('assets/csv/stock_subject.csv') }}


<!-- ### 接上外部URL JSON

<div id="data-table"></div>
ssss

<script>
async function fetchDataAndRenderTable() {
  try {
    const response = await fetch('https://beow.us/static/currStockMarket.json');
    const data = await response.json();
    
    // 创建表格
    let tableHTML = '<table>';
    
    // 添加表头
    tableHTML += '<thead><tr>';
    Object.keys(data[0]).forEach(key => {
      tableHTML += `<th>${key}</th>`;
    });
    tableHTML += '</tr></thead>';
    
    // 添加表格内容
    tableHTML += '<tbody>';
    data.forEach(item => {
      tableHTML += '<tr>';
      Object.values(item).forEach(value => {
        tableHTML += `<td>${value}</td>`;
      });
      tableHTML += '</tr>';
    });
    tableHTML += '</tbody></table>';
    
    document.getElementById('data-table').innerHTML = tableHTML;
  } catch (error) {
    console.error('获取数据时出错:', error);
    document.getElementById('data-table').innerHTML = '加载数据时出错';
  }
}

document.addEventListener('DOMContentLoaded', fetchDataAndRenderTable);
</script> -->