---
date: 2025-03-28
title: 不同程式語言的迴圈實現方式
description: 比較不同程式語言中迴圈的寫法與使用場景
authors:
  - danielchou
categories:
  - 技術比較
tags:
  - JavaScript
  - CSS
  - 程式設計
  - 迴圈
---

# 不同程式語言的迴圈實現方式

讓我們來看看在不同的程式語言中，如何實現迴圈操作。

<!-- more -->

=== "JavaScript"

    ```javascript
    // JavaScript 的迴圈實現
    const array = [1, 2, 3, 4, 5];

    // for...of 迴圈
    for (const item of array) {
        console.log(item);
    }

    // forEach 方法
    array.forEach(item => console.log(item));

    // map 轉換
    const doubled = array.map(item => item * 2);

    // reduce 累加
    const sum = array.reduce((acc, curr) => acc + curr, 0);

    // filter 過濾
    const evenNumbers = array.filter(item => item % 2 === 0);
    ```

=== "CSS"

    ```css
    /_ CSS 的循環效果 _/
    /_ 使用 nth-child _/
    .list-item:nth-child(2n) {
    background-color: #f0f0f0;
    }

    /* 使用 animation 循環 */
    @keyframes rotate {
        0% { transform: rotate(0deg); }
        100% { transform: rotate(360deg); }
    }

    .rotating-element {
        animation: rotate 2s infinite linear;
    }

    /* 使用 CSS Grid 重複模式 */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 10px;
    }
    ```

=== "Pseudo Code"

    ```txt
    // 基本迴圈邏輯的偽代碼表示

    // 計數迴圈
    FOR i = 1 TO 5
        PRINT i
    END FOR

    // 條件迴圈
    WHILE condition IS TRUE
        DO something
        UPDATE condition
    END WHILE

    // 集合迴圈
    FOR EACH item IN collection
        PROCESS item
    END FOR

    // 無限迴圈
    LOOP
        IF exit_condition THEN
            BREAK
        END IF
    END LOOP
    ```

這些不同的迴圈實現方式各有特色：

1. JavaScript：提供了豐富的陣列方法和迭代器
2. CSS：通過選擇器和動畫實現視覺上的重複效果
3. 偽代碼：展示了最基本的迴圈邏輯結構

選擇適當的迴圈方式需要考慮：

- 程式碼可讀性
- 效能影響
- 使用場景需求
- 維護性考量
