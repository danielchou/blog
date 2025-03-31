---
date: 2025-03-24
title: MkDocs 的mermaid語法展示
description: 展示 MkDocs 的mermaid語法展示
authors:
  - danielchou
categories:
  - mkdocs
tags:
  - Markdown
  - MkDocs
  - 教學
---

# mermaid語法展示流程圖

本文將展示Mermaid語法的使用方法。

<!-- more -->

## Diagrams

### 流程圖 (left - right)：

```mermaid
graph LR
    A[開始] --> B{判斷}
    B -->|Yes| C[執行]
    B -->|No| D[跳過]
    C --> E[結束]
    D --> E
```

### 流程圖 (top - down)：

```mermaid
flowchart TD
    A[Christmas] -->|Get money| B(Go shopping)
    B --> C{Let me think}
    C -->|One| D[Laptop]
    C -->|Two| E[iPhone]
    C -->|Three| F[fa:fa-car Car]
```

### 時序圖：

```mermaid
sequenceDiagram
    participant 使用者
    participant 系統
    使用者->>系統: 登入請求
    系統-->>使用者: 要求驗證
    使用者->>系統: 提供驗證
    系統-->>使用者: 登入成功
```

### 時序圖2：

``` mermaid
sequenceDiagram
  autonumber
  Alice->>John: Hello John, how are you?
  loop Healthcheck
      John->>John: Fight against hypochondria
  end
  Note right of John: Rational thoughts!
  John-->>Alice: Great!
  John->>Bob: How about you?
  Bob-->>John: Jolly good!
```

### 甘特圖：

``` mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section A section
    A task           :a1, 2014-01-06, 3d
    Another task     :after a1  , 2d
```

### 甘特圖2：

```mermaid
gantt
    title A Gantt Diagram
    dateFormat  YYYY-MM-DD
    section Section
    A task           :a1, 2024-01-01, 30d
    Another task     :after a1  , 20d
    section Another
    Task in sec      :2024-01-12  , 12d
    another task      : 24d
```

### 甘特圖3：

``` mermaid
gantt
section Section
    Completed :done,    des1, 2014-01-06,2014-01-08
    Active        :active,  des2, 2014-01-07, 3d
    Parallel 1   :         des3, after des1, 1d
    Parallel 2   :         des4, after des1, 1d
    Parallel 3   :         des5, after des3, 1d
    Parallel 4   :         des6, after des4, 1d
```

### 使用 Mermaid 繪製狀態圖：

``` mermaid
stateDiagram-v2
    [*] --> State1
    State1 --> [*]
```

### 使用 Mermaid 繪製活動圖：

``` mermaid
activityDiagram
    title 簡單活動流程
    start
    :讀取資料;
    if (資料有效?) then (yes)
      :處理資料;
      :儲存結果;
    else (no)
      :記錄錯誤;
    endif
    stop
```

### 使用 Mermaid 繪製類別圖：

``` mermaid
classDiagram
    title 動物類別範例
    class Animal {
      +String name
      +Int age
      +eat()
      +sleep()
    }
    class Dog {
      +bark()
    }
    class Cat {
      +meow()
    }
    Animal <|-- Dog
    Animal <|-- Cat
```

### 類別圖2

``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```

### entity-relationship diagram

``` mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  ORDER ||--|{ LINE-ITEM : contains
  LINE-ITEM {
    string name
    int pricePerUnit
  }
  CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

### 圓餅圖

```mermaid
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```
### 心智圖

```mermaid
mindmap
  root((mindmap))
    Origins
      Long history
      ::icon(fa fa-book)
      Popularisation
        British popular psychology author Tony Buzan
    Research
      On effectivness<br/>and features
      On Automatic creation
        Uses
            Creative techniques
            Strategic planning
            Argument mapping
    Tools
      Pen and paper
      Mermaid
```

### 用戶旅程

```mermaid
journey
  title My working day
  section Go to work
    Make tea: 5: Me
    Go upstairs: 3: Me
    Do work: 1: Me, Cat
  section Go home
    Go downstairs: 5: Me
    Sit down: 3: Me
```