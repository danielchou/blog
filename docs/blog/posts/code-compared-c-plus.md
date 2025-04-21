---
date: 2025-04-21
title: C++與其他語言的比較
description: 探討C和C++的主要差異
author: DanielChou
categories:
  - 技術
  - C++
  - 程式語言
---

# C/C++ 語言比較

本文將探討 C 和 C++ 這兩種程式語言的主要差異。

<!-- more -->

## 基本概念

C++ 是 C 的超集，這意味著任何合法的 C 程式碼在 C++ 中也是合法的（有少數例外）。
但 C++ 提供了更多的功能，特別是在物件導向程式設計方面。

## 主要差異

1. 物件導向支援
2. 模板（Template）
3. 異常處理
4. 標準函式庫
5. 記憶體管理

### 前端開發中的條件渲染比較

在前端開發中，條件渲染是一個非常常見的需求。讓我們來看看在不同語言中如何實現這個功能。

=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
