---
title: Markdown Mermaid диаграм
published: 1970-01-01
pinned: false
description: Mermaid агуулсан Markdown блогын энгийн жишээ.
tags: [Markdown, Блог, Mermaid, Firefly]
category: Өгүүллийн жишээ
slug: markdown-mermaid
series: "Firefly функцын жишээ2"
seriesOrder: 3
---
## Markdown дахь Mermaid диаграмын бүрэн гарын авлага

Энэ өгүүлэл нь Markdown баримт бичигт Mermaid ашиглан урсгал диаграм, дарааллын диаграм, ER диаграм, класс диаграм, төлөвийн диаграм, XY диаграм, Gantt диаграм, сэтгэлгээний зураг зэрэг олон төрлийн нийлмэл диаграм хэрхэн бүтээхийг танилцуулна.

> Mermaid диаграмыг [Merman](https://github.com/Latias94/merman) хэрэгжүүлсэн. Firefly нь Astro-ийн бүтээх үе шатанд гэрэл болон харанхуй гэсэн хоёр багц статик SVG үүсгэдэг тул хөтөч дотор Mermaid-ийн дүрслэх runtime ачаалах шаардлагагүй. [Merman Playground](http://frankorz.com/merman/) руу орж синтаксийг шууд засаж, дүрслэлийн үр дүнг урьдчилан үзэж болно.

## Урсгал диаграмын жишээ

Урсгал диаграм нь урсгал эсвэл алгоритмын алхмыг илэрхийлэхэд маш тохиромжтой.




```mermaid
graph TD
    A[Эхлэл] --> B{Нөхцөл шалгах}
    B -->|Тийм| C[Боловсруулах алхам 1]
    B -->|Үгүй| D[Боловсруулах алхам 2]
    C --> E[Дэд процесс]
    D --> E
    subgraph E [Дэд процессын дэлгэрэнгүй]
        E1[Дэд алхам 1] --> E2[Дэд алхам 2]
        E2 --> E3[Дэд алхам 3]
    end
    E --> F{Өөр нэг шийдвэр}
    F -->|Сонголт 1| G[Үр дүн 1]
    F -->|Сонголт 2| H[Үр дүн 2]
    F -->|Сонголт 3| I[Үр дүн 3]
    G --> J[Төгсгөл]
    H --> J
    I --> J
```

## Дарааллын диаграмын жишээ

Дарааллын диаграм нь объектуудын хоорондын цаг хугацааны харилцан үйлчлэлийг харуулна.

```mermaid
sequenceDiagram
    participant User as Хэрэглэгч
    participant WebApp as Вэб апп
    participant Server as Сервер
    participant Database as Мэдээллийн сан

    User->>WebApp: Нэвтрэх хүсэлт илгээх
    WebApp->>Server: Баталгаажуулах хүсэлт илгээх
    Server->>Database: Хэрэглэгчийн мэдээлэл шалгах
    Database-->>Server: Хэрэглэгчийн өгөгдөл буцаах
    Server-->>WebApp: Баталгаажуулалтын үр дүн буцаах

    alt Баталгаажуулалт амжилттай
        WebApp->>User: Тавтай морил хуудас харуулах
        WebApp->>Server: Хэрэглэгчийн өгөгдөл хүсэх
        Server->>Database: Хэрэглэгчийн тохиргоо авах
        Database-->>Server: Тохиргоог буцаах
        Server-->>WebApp: Хэрэглэгчийн өгөгдөл буцаах
        WebApp->>User: Хувийн интерфэйс ачаалах
    else Баталгаажуулалт бүтэлгүйтсэн
        WebApp->>User: Алдааны мэдээлэл харуулах
        WebApp->>User: Дахин оруулахыг сануулах
    end
```

## ER диаграмын жишээ

ER диаграм (entity relationship diagram) нь мэдээллийн сангийн бүтцийг илэрхийлэхэд маш тохиромжтой.

```mermaid
erDiagram
    USER {
        int id PK
        string username
        string email
        datetime created_at
    }
    ARTICLE {
        int id PK
        string title
        text content
        datetime published
        int author_id FK
    }
    COMMENT {
        int id PK
        text content
        datetime created_at
        int user_id FK
        int article_id FK
    }
    CATEGORY {
        int id PK
        string name
        string description
    }
    USER ||--o{ ARTICLE : "writes"
    USER ||--o{ COMMENT : "posts"
    ARTICLE ||--o{ COMMENT : "has"
    ARTICLE }o--o{ CATEGORY : "belongs to"
```

## Класс диаграмын жишээ

Класс диаграм нь системийн статик бүтцийг, үүний дотор класс, шинж чанар, метод болон тэдгээрийн харилцааг харуулна.

```mermaid
classDiagram
    class User {
        +String username
        +String password
        +String email
        +Boolean active
        +login()
        +logout()
        +updateProfile()
    }

    class Article {
        +String title
        +String content
        +Date publishDate
        +Boolean published
        +publish()
        +edit()
        +delete()
    }

    class Comment {
        +String content
        +Date commentDate
        +addComment()
        +deleteComment()
    }

    class Category {
        +String name
        +String description
        +addArticle()
        +removeArticle()
    }

    User "1" -- "*" Article : бичих
    User "1" -- "*" Comment : нийтлэх
    Article "1" -- "*" Comment : агуулах
    Article "1" -- "*" Category : хамаарах
```

## Төлөвийн диаграмын жишээ

Төлөвийн диаграм нь объектын амьдралын мөчлөгт дамждаг төлөвийн дарааллыг харуулна.

```mermaid
stateDiagram-v2
    [*] --> Ноорог

    Ноорог --> Хяналтад : Илгээх
    Хяналтад --> Ноорог : Татгалзах
    Хяналтад --> Зөвшөөрсөн : Зөвшөөрөх
    Зөвшөөрсөн --> Нийтлэгдсэн : Нийтлэх
    Нийтлэгдсэн --> Архивласан : Архивлах
    Нийтлэгдсэн --> Ноорог : Буцаах

    state Нийтлэгдсэн {
        [*] --> Идэвхтэй
        Идэвхтэй --> Нуугдсан : Түр нуух
        Нуугдсан --> Идэвхтэй : Сэргээх
        Идэвхтэй --> [*]
        Нуугдсан --> [*]
    }

    Архивласан --> [*]
```

## XY диаграмын жишээ

XY диаграм нь чиг хандлага болон харьцуулах өгөгдлийг харуулахад маш тохиромжтой.

```mermaid
xychart-beta
    title "Сарын зочлолтын чиг хандлага"
    x-axis [1-р сар, 2-р сар, 3-р сар, 4-р сар, 5-р сар, 6-р сар]
    y-axis "Зочлолт" 0 --> 5000
    bar [2500, 3200, 4100, 3800, 4500, 4800]
    line [2500, 3200, 4100, 3800, 4500, 4800]
```

## Дугуй диаграмын жишээ

Дугуй диаграм нь хэсэг бүрийн бүхэлд эзлэх хувийг шууд харуулахад тохиромжтой.

```mermaid
pie showData
    title Агуулгын төрлийн хувь
    "Техникийн өгүүлэл" : 45
    "Төслийн тэмдэглэл" : 30
    "Амьдралын ноорог" : 15
    "Бусад" : 10
```

## Gantt диаграмын жишээ

Gantt диаграм нь төслийн үе шат, даалгаврын хамаарал болон одоогийн явцыг цаг хугацааны тэнхлэгээр харуулна.

```mermaid
gantt
    title Блогын хувилбар гаргах төлөвлөгөө
    dateFormat YYYY-MM-DD
    axisFormat %m/%d
    section Бэлтгэл
    Шаардлага цэгцлэх :done, req, 2026-07-01, 3d
    Визуал загвар :done, design, after req, 4d
    section Хөгжүүлэлт
    Функц хэрэгжүүлэх :active, dev, after design, 7d
    Агуулга шилжүүлэх :content, after design, 5d
    section Гаргах
    Бүтээцийн шалгалт :test, after dev, 2d
    Албан ёсоор нээх :milestone, release, after test, 0d
```

## Сэтгэлгээний зургийн жишээ

Сэтгэлгээний зураг нь сэдвийн шатлал болон мэдлэгийн бүтцийг цэгцлэхэд тохиромжтой.

```mermaid
mindmap
  root((Firefly))
    Агуулга
      Техникийн өгүүлэл
      Амьдралын тэмдэглэл
    Туршлага
      Хайлт
      Харанхуй горим
      Диаграм
    Инженерчлэл
      Astro
      Svelte
      Merman
```

## Цаг хугацааны шугамын жишээ

Цаг хугацааны шугамыг төслийн чухал үйл явдлыг он эсвэл үе шатаар харуулахад ашиглана.

```mermaid
timeline
    title Firefly-ийн хөгжлийн цаг хугацааны шугам
    2024 : Блог байгуулсан
         : Үндсэн загварыг дуусгасан
    2025 : Хайлт болон зургийн санг нэмсэн
         : Агуулгын системийг сайжруулсан
    2026 : Astro 7 руу шинэчилсэн
         : Merman-аар диаграм дүрсэлсэн
```

## Хэрэглэгчийн аяллын диаграмын жишээ

Хэрэглэгчийн аяллын диаграм нь хэрэглэгчийн өөр өөр үе шатны үйлдэл болон туршлагын үнэлгээг дүрсэлж чадна.

```mermaid
journey
    title Уншигчийн өгүүлэл үзэх аялал
    section Агуулга олж илрүүлэх
      Нүүр хуудас нээх: 5: Уншигч
      Сэдэв хайх: 4: Уншигч
    section Өгүүлэл унших
      Үндсэн хэсгийг үзэх: 5: Уншигч
      Диаграм харах: 5: Уншигч
    section Үргэлжлүүлэн судлах
      Холбоотой өгүүлэл харах: 4: Уншигч
      Өгүүлэл хуваалцах: 3: Уншигч
```

## Git диаграмын жишээ

Git диаграм нь салбар, commit болон merge-ийн түүхийг тодорхой харуулна.

```mermaid
gitGraph
    commit id: "init"
    branch feature
    checkout feature
    commit id: "add-diagrams"
    commit id: "polish-themes"
    checkout main
    merge feature id: "merge-feature"
    commit id: "release"
```

## Kanban жишээ

Kanban нь даалгавруудын ажлын үе шатуудын хоорондох хуваарилалтыг харуулахад тохиромжтой.

```mermaid
kanban
  todo[Хийх]
    task1[Шаардлага цэгцлэх]
    task2[Жишээ бэлтгэх]
  doing[Хийгдэж байгаа]
    task3[Merman холбох]
  done[Дууссан]
    task4[Сервер талын дүрслэл]
    task5[Гэрэл/харанхуй сэдэв]
```

## Sankey диаграмын жишээ

Sankey диаграм нь шугамын өргөнөөр дамжуулан урсгалын зангилаануудын хоорондох чиглэлийг харуулна.

```mermaid
sankey-beta
Home,Post list,1200
Home,Search,450
Post list,Post detail,900
Search,Post detail,320
Post detail,Related posts,260
Post detail,External shares,180
```

## Дүгнэлт

Mermaid нь Markdown баримт бичигт олон төрлийн диаграм бүтээх хүчирхэг хэрэгсэл юм. Энэ өгүүлэл урсгал диаграм, дарааллын диаграм, ER диаграм, класс диаграм, төлөвийн диаграм, XY диаграм, дугуй диаграм, Gantt диаграм, сэтгэлгээний зураг, цаг хугацааны шугам, хэрэглэгчийн аяллын диаграм, Git диаграм, Kanban болон Sankey диаграмыг танилцууллаа. Эдгээр диаграм нь нийлмэл ойлголт, урсгал болон өгөгдлийн бүтцийг илүү тодорхой илэрхийлэхэд тусална.

Mermaid ашиглахын тулд кодын блок дотор mermaid хэлийг зааж, товч текстийн синтаксоор диаграмыг тодорхойлоход хангалттай. Диаграм нь бүтээх үед SVG болж автоматаар дүрслэгдэх тул клиент талын JavaScript ачаалах шаардлагагүй.

[Merman Playground](http://frankorz.com/merman/) руу орж илүү олон синтаксийг туршиж, диаграмын кодоо өгүүлэлд буулгаж болно.
