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