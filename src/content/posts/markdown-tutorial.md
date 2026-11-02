---
title: Markdown заавар
published: 1970-01-01
pinned: false
description: Markdown блогын товч жишээ.
tags: [Markdown, Өгүүллийн жишээ]
category: Өгүүллийн жишээ
licenseName: "Зөвшөөрөлгүй"
author: emn178
sourceLink: "https://github.com/emn178/markdown"
slug: markdown-tutorial
series: "Firefly функцын жишээ2"
seriesOrder: 1
---

Энэ бол Markdown файл хэрхэн бичихийг харуулсан жишээ юм. Энэ баримт бичигт үндсэн синтакс болон нийтлэг өргөтгөлүүд (GFM)-ийг нэгтгэв.

- [Блок түвшний элементүүд](#block-elements)
    - [Догол мөр ба мөр таслах](#paragraphs-and-line-breaks)
    - [Гарчиг](#headers)
    - [Ишлэл](#blockquotes)
    - [Жагсаалт](#lists)
    - [Кодын блок](#code-blocks)
    - [Хуваагч шугам](#horizontal-rules)
    - [Хүснэгт](#table)
- [Мөр доторх элементүүд](#span-elements)
    - [Холбоос](#links)
    - [Онцлох бичиг](#emphasis)
    - [Мөр доторх код](#code)
    - [Зураг](#images)
    - [Тасалсан мөр](#strikethrough)
- [Бусад](#miscellaneous)
    - [Автомат холбоос](#automatic-links)
    - [Backslash escape](#backslash-escapes)
- [Мөр доторх HTML](#inline-html)

<a id="block-elements"></a>
## Блок түвшний элементүүд

<a id="paragraphs-and-line-breaks"></a>
### Догол мөр ба мөр таслах

#### Догол мөр

HTML шошго: `<p>`

Догол мөрийг нэг буюу хэд хэдэн хоосон мөрөөр тусгаарлана. (Зөвхөн **зай** эсвэл **tab** агуулсан мөрийг ч хоосон мөр гэж үзнэ.)

Код:

    This will be
    inline.

    This is second paragraph.

Урьдчилан харах:

---

This will be
inline.

This is second paragraph.

---

#### Мөр таслах

HTML шошго: `<br />`

Мөрийн төгсгөлд **хоёр буюу түүнээс дээш зай** нэмж мөр тасална.

Код:

    This will be not
    inline.

Урьдчилан харах:

---

This will be not  
inline.

---

<a id="headers"></a>
### Гарчиг

Markdown нь Setext болон atx гэсэн хоёр гарчгийн хэв маягийг дэмжинэ.

#### Setext

HTML шошго: `<h1>`，`<h2>`

**Тэнцүү тэмдэг (=)**-ээр `<h1>`-ийг, **зураас (-)**-аар `<h2>`-ийг илэрхийлэх бөгөөд тоо нь хязгааргүй, «доогуур зураас» болгон ашиглана.

Код:

    This is an H1
    =============
    This is an H2
    -------------

Урьдчилан харах:

---

# This is an H1

## This is an H2

---

#### atx

HTML шошго: `<h1>`，`<h2>`，`<h3>`，`<h4>`，`<h5>`，`<h6>`

Мөрийн эхэнд 1-6 ширхэг **# тэмдэг** хийх бөгөөд `<h1>`-ээс `<h6>` хүртэл харгалзана.

Код:

    # This is an H1
    ## This is an H2
    ###### This is an H6

Урьдчилан харах:

---

# This is an H1

## This is an H2

###### This is an H6

---

Сонголтоор: та мөрийн төгсгөлд atx гарчгийг «хааж» болно. Төгсгөлийн # тэмдгийн тоо эхнийхтэй **ижил байх шаардлагагүй**.

Код:

    # This is an H1 #
    ## This is an H2 ##
    ### This is an H3 ######

Урьдчилан харах:

---

# This is an H1

## This is an H2

### This is an H3

---

<a id="blockquotes"></a>
### Ишлэл

HTML шошго: `<blockquote>`

Markdown нь имэйлийн хэв маягийн **>** тэмдгийг ишлэлийн тэмдэг болгон ашиглана. Гараар мөр тасалж мөр бүрийн эхэнд > хийвэл хамгийн сайн харагдана.

Код:

    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    > consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    > Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
    >
    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    > id sem consectetuer libero luctus adipiscing.

Урьдчилан харах:

---

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

---

Markdown нь «залхуурахыг» зөвшөөрдөг: хатуу мөр таслалттай догол мөрөнд зөвхөн эхний мөрийн өмнө > хийхэд хангалттай.

Код:

    > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
    Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

    > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
    id sem consectetuer libero luctus adipiscing.

Урьдчилан харах:

---

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

---

Ишлэлийг үүрлэж болно (ишлэл доторх ишлэл), > түвшинг нэмэгдүүлснээр хийгдэнэ.

Код:

    > This is the first level of quoting.
    >
    > > This is nested blockquote.
    >
    > Back to the first level.

Урьдчилан харах:

---

> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.

---

Ишлэл дотор гарчиг, жагсаалт, кодын блок зэрэг бусад Markdown элементүүд орж болно.

Код:

    > ## This is a header.
    >
    > 1.   This is the first list item.
    > 2.   This is the second list item.
    >
    > Here's some example code:
    >
    >     return shell_exec("echo $input | $markdown_script");

Урьдчилан харах:

---

> ## This is a header.
>
> 1.  This is the first list item.
> 2.  This is the second list item.
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");

---

<a id="lists"></a>
### Жагсаалт

Markdown нь эрэмбэлэгдсэн (тоо) болон эрэмбэлэгдээгүй (цэг) жагсаалтыг дэмжинэ.

#### Эрэмбэлэгдээгүй жагсаалт

HTML шошго: `<ul>`

Эрэмбэлэгдээгүй жагсаалтад **од (\*)**、**нэмэх тэмдэг (+)** эсвэл **зураас (-)** ашиглаж болно.

Код:

    *   Red
    *   Green
    *   Blue

Урьдчилан харах:

---

- Red
- Green
- Blue

---

Дараахтай тэнцэнэ:

Код:

    +   Red
    +   Green
    +   Blue

Эсвэл:

Код:

    -   Red
    -   Green
    -   Blue

#### Эрэмбэлэгдсэн жагсаалт

HTML шошго: `<ol>`

Эрэмбэлэгдсэн жагсаалт нь тоо болон англи цэг ашиглана:

Код:

    1.  Bird
    2.  McHale
    3.  Parish

Урьдчилан харах:

---

1.  Bird
2.  McHale
3.  Parish

---

Анхаар: Доорх шиг бичвэл эрэмбэлэгдсэн жагсаалт «санамсаргүй идэвхжиж» болно:

Код:

    1986. What a great season.

Урьдчилан харах:

---

1986. What a great season.

---

Та **backslash escape (\\)**-ээр цэгийг escape хийж болно:

Код:

    1986\. What a great season.

Урьдчилан харах:

---

1986\. What a great season.

---

#### Жагсаалт доторх догол мөртэй агуулга

##### Жагсаалтын элемент доторх ишлэл

Жагсаалтын элемент дотор ишлэл хийхийн тулд > тэмдгийг бүхэлд нь догол мөрлөх шаардлагатай:

Код:

    *   A list item with a blockquote:

        > This is a blockquote
        > inside a list item.

Урьдчилан харах:

---

- A list item with a blockquote:

  > This is a blockquote
  > inside a list item.

---

##### Жагсаалтын элемент доторх кодын блок

Жагсаалтын элемент дотор кодын блок хийхийн тулд хоёр давхар догол мөрлөх шаардлагатай — **8 зай** эсвэл **хоёр Tab**:

Код:

    *   A list item with a code block:

            <code goes here>

Урьдчилан харах:

---

- A list item with a code block:

      <code goes here>

---

##### Үүрлэсэн жагсаалт

Код:

    * A
      * A1
      * A2
    * B
    * C

Урьдчилан харах:

---

- A
  - A1
  - A2
- B
- C

---

<a id="code-blocks"></a>
### Кодын блок

HTML шошго: `<pre>`

Кодын блокийн мөр бүрийг дор хаяж **4 зай** эсвэл **1 tab**-аар догол мөрлөнө.

Код:

    This is a normal paragraph:

        This is a code block.

Урьдчилан харах:

---

This is a normal paragraph:

    This is a code block.

---

Кодын блок нь догол мөрлөөгүй мөр (эсвэл баримт бичгийн төгсгөл) тохиолдох хүртэл үргэлжилнэ.

Кодын блок дотор **амперсанд (&)** болон өнцөг хаалт **(< >)** нь HTML entity болж автоматаар хөрвөнө.

Код:

        <div class="footer">
            &copy; 2004 Foo Corporation
        </div>

Урьдчилан харах:

---

    <div class="footer">
        &copy; 2004 Foo Corporation
    </div>

---

Дараах «хашаатай кодын блок» болон «синтакс тодотгол» нь өргөтгөсөн синтакс бөгөөд тэдгээрийг ч кодын блок бичихэд ашиглаж болно.

#### Хашаатай кодын блок

Хос backtick-ээр хүрээлбэл (доорх шиг) дөрвөн зайн догол мөр шаардлагагүй.

Код:

    Here's an example:

    ```
    function test() {
      console.log("notice the blank line before this function?");
    }
    ```

Урьдчилан харах:

---

Here's an example:

```
function test() {
  console.log("notice the blank line before this function?");
}
```

---

#### Синтакс тодотгол

Хашаатай кодын блокийн дараа сонголтоор хэлний тодорхойлогч нэмэхэд синтакс тодотгол идэвхжинэ (дэмжигдэх хэлний жагсаалтыг үзнэ үү).

Код:

    ```ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    ```

Урьдчилан харах:

---

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

---

<a id="horizontal-rules"></a>
### Хуваагч шугам (хэвтээ шугам)

HTML шошго: `<hr />`
Нэг мөрөнд **гурав буюу түүнээс дээш зураас (-)、од (\*) эсвэл доогуур зураас (\_)** байрлуулна. Тэмдгүүдийн хооронд зай байж болно.

Код:

    * * *
    ***
    *****
    - - -
    ---------------------------------------
    ___

Урьдчилан харах:

---

---

---

---

---

---

---

---

<a id="table"></a>
### Хүснэгт

HTML шошго: `<table>`

Энэ нь өргөтгөсөн синтакс.

Баганыг **босоо зураас (|)**-аар, толгойг **зураас (-)**-аар тусгаарлах бөгөөд **давхар цэг (:)**-ээр зэрэгцүүлэлтийг тодорхойлно.

Хоёр талын **босоо зураас (|)** болон зэрэгцүүлэлт нь сонголтоор. Толгой тусгаарлагчид багана бүрт дор хаяж **3 зураас** шаардлагатай.

Код:

```
| Left | Center | Right |
|:-----|:------:|------:|
|aaa   |bbb     |ccc    |
|ddd   |eee     |fff    |

 A | B
 ---|---
 123|456


A |B
--|--
12|45
```

Урьдчилан харах:

---

| Left | Center | Right |
| :--- | :----: | ----: |
| aaa  |  bbb   |   ccc |
| ddd  |  eee   |   fff |

| A   | B   |
| --- | --- |
| 123 | 456 |

| A   | B   |
| --- | --- |
| 12  | 45  |

---

<a id="span-elements"></a>
## Мөр доторх элементүүд

<a id="links"></a>
### Холбоос

HTML шошго: `<a>`

Markdown нь мөр доторх холбоос болон ишлэлт холбоос гэсэн хоёр хэв маягийг дэмжинэ.

#### Мөр доторх холбоос

Мөр доторх холбоосын формат: `[текст](URL "гарчиг")`

Гарчиг нь сонголтоор.

Код:

    This is [an example](http://example.com/ "Title") inline link.

    [This link](http://example.net/) has no title attribute.

Урьдчилан харах:

---

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

---

Нэг сайтын локал нөөцийг ишлэх бол харьцангуй зам ашиглаж болно:

Код:

    See my [About](/about/) page for details.

Урьдчилан харах:

---

See my [About](/about/) page for details.

---

#### Ишлэлт холбоос

Холбоосын ишлэлийг урьдчилан тодорхойлж болно. Тодорхойлолтын формат: `[id]: URL "гарчиг"`

Гарчиг нь ч мөн сонголтоор. Ишлэхдээ: `[текст][id]` ашиглана.

Код:

    [id]: http://example.com/  "Optional Title Here"
    This is [an example][id] reference-style link.

Урьдчилан харах:

---

[id]: http://example.com/ "Optional Title Here"

This is [an example][id] reference-style link.

---

Тайлбар:

- Дөрвөлжин хаалтанд холбоосын тодорхойлогч (**том/жижиг үсгийг ялгахгүй**, зүүн талаас дээд тал нь гурван зай догол мөрлөж болно);
- Дараа нь давхар цэг;
- Дараа нь нэг буюу хэд хэдэн зай (эсвэл tab);
- Дараа нь холбоосын URL;
- URL-ыг сонголтоор өнцөг хаалтаар хүрээлж болно;
- Сонголтоор гарчгийн шинж чанарыг хашилт эсвэл дугуй хаалтаар хүрээлж дагаж болно.

Дараах гурван тодорхойлолт тэнцүү:

Код:

    [foo]: http://example.com/  "Optional Title Here"
    [foo]: http://example.com/  'Optional Title Here'
    [foo]: http://example.com/  (Optional Title Here)
    [foo]: <http://example.com/>  "Optional Title Here"

Хоосон дөрвөлжин хаалт ашиглавал холбоосын текст өөрөө нэр болно.

Код:

    [Google]: http://google.com/
    [Google][]

Урьдчилан харах:

---

[Google]: http://google.com/

[Google][]

---

<a id="emphasis"></a>
### Онцлох бичиг

HTML шошго: `<em>`，`<strong>`

Markdown нь онцлох бичгийг **од (\*)** эсвэл **доогуур зураас (\_)**-аар илэрхийлнэ. **Нэг тусгаарлагч** нь `<em>`-тэй; **хоёр тусгаарлагч** нь `<strong>`-той харгалзана.

Код:

    *single asterisks*

    _single underscores_

    **double asterisks**

    __double underscores__

Урьдчилан харах:

---

_single asterisks_

_single underscores_

**double asterisks**

**double underscores**

---

Харин хоёр талд зай байвал энгийн тэмдэгт гэж үзэх бөгөөд онцлох синтакс биш.

Та backslash ашиглан escape хийж болно:

Код:

    \*this text is surrounded by literal asterisks\*

Урьдчилан харах:

---

\*this text is surrounded by literal asterisks\*

---

<a id="code"></a>
### Мөр доторх код

HTML шошго: `<code>`

**Backtick (`)**-ээр хүрээлнэ.

Код:

    Use the `printf()` function.

Урьдчилан харах:

---

Use the `printf()` function.

---

Мөр доторх код дотор backtick тэмдэгт оруулах шаардлагатай бол **олон backtick**-ийг хязгаарлагч болгон ашиглаж болно:

Код:

    ``There is a literal backtick (`) here.``

Урьдчилан харах:

---

``There is a literal backtick (`) here.``

---

Мөр доторх кодын хоёр талын хязгаарлагчид зай оруулах боломжтой (эхэнд нэг, төгсгөлд нэг) бөгөөд ингэснээр кодын эхлэл эсвэл төгсгөлд backtick тэмдэгт байрлуулахад хялбар болно:

Код:

    A single backtick in a code span: `` ` ``

    A backtick-delimited string in a code span: `` `foo` ``

Урьдчилан харах:

---

A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``

---

<a id="images"></a>
### Зураг

HTML шошго: `<img />`

Markdown-ийн зургийн синтакс нь холбоостой төстэй бөгөөд мөр доторх болон ишлэлт гэсэн хоёр аргыг дэмжинэ.

#### Мөр доторх зураг

Мөр доторх зургийн синтакс: `![орлуулах текст](URL "гарчиг")`

Гарчиг нь сонголтоор.

Код:

    ![Alt text](/path/to/img.jpg)

    ![Alt text](/path/to/img.jpg "Optional title")

Урьдчилан харах:

---

![Alt text](https://s2.loli.net/2024/08/20/5fszgXeOxmL3Wdv.webp)

![Alt text](https://s2.loli.net/2024/08/20/5fszgXeOxmL3Wdv.webp "Optional title")

---

Тайлбар:

- Нэг анхаарлын тэмдэг !;
- Дараа нь дөрвөлжин хаалт, дотор нь зургийн орлуулах текст;
- Дараа нь дугуй хаалт, дотор нь зургийн URL/зам болон сонголтоор гарчиг (хашилтаар хүрээлсэн).

#### Ишлэлт зураг

Ишлэлт зургийн синтакс: `![орлуулах текст][id]`

Код:

    [img id]: https://s2.loli.net/2024/08/20/5fszgXeOxmL3Wdv.webp  "Optional title attribute"
    ![Alt text][img id]

Урьдчилан харах:

---

[img id]: https://s2.loli.net/2024/08/20/5fszgXeOxmL3Wdv.webp "Optional title attribute"

![Alt text][img id]

---

<a id="strikethrough"></a>
### Тасалсан мөр

HTML шошго: `<del>`

Энэ нь өргөтгөсөн синтакс.

GFM нь тасалсан мөрийн синтаксийг нэмсэн.

Код:

```
~~Mistaken text.~~
```

Урьдчилан харах:

---

~~Mistaken text.~~

---

<a id="miscellaneous"></a>
## Бусад

<a id="automatic-links"></a>
### Автомат холбоос

Markdown нь «автомат холбоос» (URL болон имэйл хаяг) үүсгэх хялбар бичиглэлийг дэмжинэ: зүгээр л өнцөг хаалтаар хүрээлэхэд хангалттай.

Код:

    <http://example.com/>

    <address@example.com>

Урьдчилан харах:

---

<http://example.com/>

<address@example.com>

---

GFM нь стандарт URL-ыг автоматаар таньж холбоос болгоно.

Код:

```
https://github.com/emn178/markdown
```

Урьдчилан харах:

---

https://github.com/emn178/markdown

---

<a id="backslash-escapes"></a>
### Backslash escape

Markdown нь Markdown синтаксд зориулагдсан тусгай тэмдэгтүүдийг backslash ашиглан escape хийж, шууд утгаар нь харуулахыг зөвшөөрдөг.

Код:

    \*literal asterisks\*

Урьдчилан харах:

---

\*literal asterisks\*

---

Дараах тэмдэгтүүдийг backslash-аар escape хийж шууд утгаар нь гаргаж болно:

Код:

    \   backslash
    `   backtick
    *   asterisk
    _   underscore
    {}  curly braces
    []  square brackets
    ()  parentheses
    #   hash mark
    +   plus sign
    -   minus sign (hyphen)
    .   dot
    !   exclamation mark

<a id="inline-html"></a>
## Мөр доторх HTML

Markdown синтаксд хамаарахгүй тэмдэглэгээний хувьд шууд эх HTML ашиглахад хангалттай. Markdown-оос HTML руу шилжихийг тусгайлан зарлах шаардлагагүй, шошгыг шууд бичихэд л болно.

Код:

    This is a regular paragraph.

    <table>
        <tr>
            <td>Foo</td>
        </tr>
    </table>

    This is another regular paragraph.

Урьдчилан харах:

---

This is a regular paragraph.

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

This is another regular paragraph.

---

Анхаар: **блок түвшний HTML шошго** дотор Markdown синтакс боловсруулагдахгүй.

Блок түвшний шошгоос ялгаатай нь **мөр доторх түвшний шошго** дотор Markdown синтакс боловсруулагдана.

Код:

    <span>**Work**</span>

    <div>
        **No Work**
    </div>

Урьдчилан харах:

---

<span>**Work**</span>

<div>
  **No Work**
</div>
***
