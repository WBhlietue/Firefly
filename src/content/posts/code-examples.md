---
title: Firefly кодын блокийн жишээ
published: 1970-01-03
pinned: false
description: Firefly дотор Expressive Code ашигласан кодын блок Markdown дотор хэрхэн харагдахыг харуулна.
tags: [Markdown, Firefly]
category: Өгүүллийн жишээ
image: ./images/firefly3.avif
slug: code-examples
series: "Firefly функцын жишээ2"
seriesOrder: 5
---

Энд бид [Expressive Code](https://expressive-code.com/) ашиглан кодын блокыг хэрхэн үзүүлэхийг судлах болно. Өгөгдсөн жишээнүүд нь албан ёсны баримт бичигт суурилсан тул илүү дэлгэрэнгүй мэдээллийг тэндээс үзэж болно.

## Expressive Code

### Синтакс тодотгол

[Синтакс тодотгол](https://expressive-code.com/key-features/syntax-highlighting/)

#### Энгийн синтакс тодотгол

```js
console.log('Энэ код синтакс тодотголтой!')
```

#### ANSI escape дарааллыг дүрслэх

```ansi
[1;4mStandard ANSI colors:[0m
- Dimmed:     [2;30m Black [2;31m Red [2;32m Green [2;33m Yellow [2;34m Blue [2;35m Magenta [2;36m Cyan [2;37m White [0m
- Foreground: [30m Black [31m Red [32m Green [33m Yellow [34m Blue [35m Magenta [36m Cyan [37m White [0m
- Background: [40m Black [41m Red [42m Green [43m Yellow [44m Blue [45m Magenta [46m Cyan [47m White [0m
- Reversed:   [7;30m Black [7;31m Red [7;32m Green [7;33m Yellow [7;34m Blue [7;35m Magenta [7;36m Cyan [7;37m White [0m

[1;4m8-bit colors (showing colors 160-171 as an example):[0m
- Dimmed:     [2;38;5;160m 160 [2;38;5;161m 161 [2;38;5;162m 162 [2;38;5;163m 163 [2;38;5;164m 164 [2;38;5;165m 165 [2;38;5;166m 166 [2;38;5;167m 167 [2;38;5;168m 168 [2;38;5;169m 169 [2;38;5;170m 170 [2;38;5;171m 171 [0m
- Foreground: [38;5;160m 160 [38;5;161m 161 [38;5;162m 162 [38;5;163m 163 [38;5;164m 164 [38;5;165m 165 [38;5;166m 166 [38;5;167m 167 [38;5;168m 168 [38;5;169m 169 [38;5;170m 170 [38;5;171m 171 [0m
- Background: [48;5;160m 160 [48;5;161m 161 [48;5;162m 162 [48;5;163m 163 [48;5;164m 164 [48;5;165m 165 [48;5;166m 166 [48;5;167m 167 [48;5;168m 168 [48;5;169m 169 [48;5;170m 170 [48;5;171m 171 [0m
- Reversed:   [7;38;5;160m 160 [7;38;5;161m 161 [7;38;5;162m 162 [7;38;5;163m 163 [7;38;5;164m 164 [7;38;5;165m 165 [7;38;5;166m 166 [7;38;5;167m 167 [7;38;5;168m 168 [7;38;5;169m 169 [7;38;5;170m 170 [7;38;5;171m 171 [0m

[1;4m24-bit colors (full RGB):[0m
- Dimmed:     [2;38;2;34;139;34m ForestGreen - RGB(34,139,34) [2;38;2;102;51;153m RebeccaPurple - RGB(102,51,153) [0m
- Foreground: [38;2;34;139;34m ForestGreen - RGB(34,139,34) [38;2;102;51;153m RebeccaPurple - RGB(102,51,153) [0m
- Background: [48;2;34;139;34m ForestGreen - RGB(34,139,34) [48;2;102;51;153m RebeccaPurple - RGB(102,51,153) [0m
- Reversed:   [7;38;2;34;139;34m ForestGreen - RGB(34,139,34) [7;38;2;102;51;153m RebeccaPurple - RGB(102,51,153) [0m

[1;4mFont styles:[0m
- Default
- [1mBold[0m
- [2mDimmed[0m
- [3mItalic[0m
- [4mUnderline[0m
- [7mReversed[0m
- [9mStrikethrough[0m
```

### Загварчилсан код болон терминалын хүрээ

[Загварчилсан код болон терминалын хүрээ](https://expressive-code.com/key-features/frames/)

#### Код засварлагчийн хүрээ

```js title="my-test-file.js"
console.log('Гарчгийн шинж чанарын жишээ')
```

---

```html
<!-- src/content/index.html -->
<div>Файлын нэрийн тайлбарын жишээ</div>
```

#### Терминалын хүрээ

```bash
echo "Энэ терминалын хүрээ гарчиггүй"
```

---

```powershell title="PowerShell терминалын жишээ"
Write-Output "Энэ нь гарчигтай!"
```

#### Хүрээний төрлийг дарж бичих

```sh frame="none"
echo "Хар даа, хүрээ байхгүй!"
```

---

```ps frame="code" title="PowerShell Profile.ps1"
# Хэрэв дарж бичихгүй бол энэ нь терминалын хүрээ болно
function Watch-Tail { Get-Content -Tail 20 -Wait $args }
New-Alias tail Watch-Tail
```

### Текст болон мөрийн тэмдэглэгээ

[Текст болон мөрийн тэмдэглэгээ](https://expressive-code.com/key-features/text-markers/)

#### Бүтэн мөр болон мөрийн мужийг тэмдэглэх

```js {1, 4, 7-8}
// 1-р мөр - мөрийн дугаараар тодорхойлсон
// 2-р мөр
// 3-р мөр
// 4-р мөр - мөрийн дугаараар тодорхойлсон
// 5-р мөр
// 6-р мөр
// 7-р мөр - "7-8" мужоор тодорхойлсон
// 8-р мөр - "7-8" мужоор тодорхойлсон
```

#### Мөрийн тэмдэглэгээний төрлийг сонгох (mark, ins, del)

```js title="line-markers.js" del={2} ins={3-4} {6}
function demo() {
  console.log('Энэ мөрийг устгасан гэж тэмдэглэв')
  // Энэ мөр болон дараагийн мөрийг нэмсэн гэж тэмдэглэв
  console.log('Энэ бол хоёр дахь нэмсэн мөр')

  return 'Энэ мөр саармаг өгөгдмөл тэмдэглэгээний төрөл ашиглана'
}
```

#### Мөрийн тэмдэглэгээнд шошго нэмэх

```jsx {"1":5} del={"2":7-8} ins={"3":10-12}
// labeled-line-markers.jsx
<button
  role="button"
  {...props}
  value={value}
  className={buttonClassName}
  disabled={disabled}
  active={active}
>
  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>
```

#### Тусдаа мөрөнд урт шошго нэмэх

```jsx {"1. Provide the value prop here:":5-6} del={"2. Remove the disabled and active states:":8-10} ins={"3. Add this to render the children inside the button:":12-15}
// labeled-line-markers.jsx
<button
  role="button"
  {...props}

  value={value}
  className={buttonClassName}

  disabled={disabled}
  active={active}
>

  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>
```

#### Diff-төстэй синтакс ашиглах

```diff
+Энэ мөрийг нэмсэн гэж тэмдэглэнэ
-Энэ мөрийг устгасан гэж тэмдэглэнэ
Энэ бол энгийн мөр
```

---

```diff
--- a/README.md
+++ b/README.md
@@ -1,3 +1,4 @@
+this is an actual diff file
-all contents will remain unmodified
 no whitespace will be removed either
```

#### Синтакс тодотгол болон diff-төстэй синтаксийг хослуулах

```diff lang="js"
  function thisIsJavaScript() {
    // Бүхэл блок JavaScript-ээр тодотгогдоно,
    // бас diff тэмдэглэгээ нэмж болно!
-   console.log('Устгах хуучин код')
+   console.log('Шинэ гялалзсан код!')
  }
```

#### Мөр доторх тусдаа текстийг тэмдэглэх

```js "given text"
function demo() {
  // Мөр доторх аливаа өгөгдсөн текстийг тэмдэглэнэ
  return 'Өгөгдсөн текстийн олон тохиолдлыг дэмжинэ';
}
```

#### Регуляр илэрхийлэл

```ts /ye[sp]/
console.log('yes болон yep гэсэн үгс тэмдэглэгдэнэ.')
```

#### Налуу зураасыг escape хийх

```sh /\/ho.*\//
echo "Test" > /home/test.txt
```

#### Мөр доторх тэмдэглэгээний төрлийг сонгох (mark, ins, del)

```js "return true;" ins="inserted" del="deleted"
function demo() {
  console.log('Эдгээр нь нэмсэн болон устгасан тэмдэглэгээний төрлүүд');
  // return өгүүлбэр өгөгдмөл тэмдэглэгээний төрөл ашиглана
  return true;
}
```

### Автомат мөр таслах

[Автомат мөр таслах](https://expressive-code.com/key-features/word-wrap/)

#### Блок бүрд автомат мөр таслахыг тохируулах

```js wrap
// Мөр таслалт идэвхжсэн жишээ
function getLongString() {
  return 'Энэ бол маш урт тэмдэгт мөр бөгөөд сав нь маш өргөн биш бол боломжтой зайд багтахгүй байх магадлалтай'
}
```

---

```js wrap=false
// wrap=false-ийн жишээ
function getLongString() {
  return 'Энэ бол маш урт тэмдэгт мөр бөгөөд сав нь маш өргөн биш бол боломжтой зайд багтахгүй байх магадлалтай'
}
```

#### Мөр таслалтын догол мөрийг тохируулах

```js wrap preserveIndent
// preserveIndent жишээ (өгөгдмлөөр идэвхтэй)
function getLongString() {
  return 'Энэ бол маш урт тэмдэгт мөр бөгөөд сав нь маш өргөн биш бол боломжтой зайд багтахгүй байх магадлалтай'
}
```

---

```js wrap preserveIndent=false
// preserveIndent=false-ийн жишээ
function getLongString() {
  return 'Энэ бол маш урт тэмдэгт мөр бөгөөд сав нь маш өргөн биш бол боломжтой зайд багтахгүй байх магадлалтай'
}
```

## Эвхэгдэх хэсэг

[Эвхэгдэх хэсэг](https://expressive-code.com/plugins/collapsible-sections/)

```js collapse={1-5, 12-14, 21-24}
// Эдгээр бүх boilerplate тохиргооны кодыг эвхнэ
import { someBoilerplateEngine } from '@example/some-boilerplate'
import { evenMoreBoilerplate } from '@example/even-more-boilerplate'

const engine = someBoilerplateEngine(evenMoreBoilerplate())

// Энэ хэсэг өгөгдмлөөр харагдана
engine.doSomething(1, 2, 3, calcFn)

function calcFn() {
  // Та олон эвхэгдэх хэсэгтэй байж болно
  const a = 1
  const b = 2
  const c = a + b

  // Энэ нь харагдсаар байх болно
  console.log(`Тооцооллын үр дүн: ${a} + ${b} = ${c}`)
  return c
}

// Блокийн төгсгөл хүртэлх бүх кодыг дахин эвхнэ
engine.closeConnection()
engine.freeMemory()
engine.shutdown({ reason: 'Жишээ boilerplate кодын төгсгөл' })
```

## Мөрийн дугаар

[Мөрийн дугаар](https://expressive-code.com/plugins/line-numbers/)

### Блок бүрд мөрийн дугаар харуулах

```js showLineNumbers
// Энэ кодын блок мөрийн дугаар харуулна
console.log('2-р мөрнөөс мэндчилгээ!')
console.log('Би 3-р мөрөнд байна')
```

---

```js showLineNumbers=false
// Энэ блок мөрийн дугаарыг унтраасан
console.log('Сайн уу?')
console.log('Уучлаарай, би хэддүгээр мөрөнд байгааг мэдэх үү?')
```

### Эхлэх мөрийн дугаарыг өөрчлөх

```js showLineNumbers startLineNumber=5
console.log('5-р мөрнөөс мэндчилгээ!')
console.log('Би 6-р мөрөнд байна')
```

## Tab кодын блок

[rehype-code-group](https://github.com/ITZSHOAIB/rehype-code-group)-оос үзүүлсэн бөгөөд синтакс нь [VitePress кодын бүлэг](https://vitepress.dev/guide/markdown#code-groups)-тэй ижил: `::: code-group labels=[...]`-ээр олон кодын блокийг хүрээлбэл нэг бүлэг tab болж нэгдэнэ.

> [!NOTE]
> `labels=[...]` дахь шошгууд нь бүлэг доторх кодын блокуудтай дарааллаар харгалзах бөгөөд англи таслалаар тусгаарлана; `:::` ба `code-group`-ын хоорондох зайг орхиж болохгүй.

### Үндсэн хэрэглээ

````markdown
::: code-group labels=[code.js, code.py, code.html]

```js
export function greet(name) {
  return `Hello, ${name}!`;
}
```

```py
def greet(name):
    return f"Hello, {name}!"
```

```html
<p>Hello, world!</p>
```

:::
````

Дүрслэлийн үр дүн:

::: code-group labels=[code.js, code.py, code.html]

```js
export function greet(name) {
  return `Hello, ${name}!`;
}
```

```py
def greet(name):
    return f"Hello, {name}!"
```

```html
<p>Hello, world!</p>
```

:::

### Шошгонд Emoji ашиглах

Шошго нь [emoji богино код](https://github.com/omnidan/node-emoji#readme)-ыг дэмжих бөгөөд бүтээх үед автоматаар emoji болж хөрвөнө:

````markdown
::: code-group labels=[:package: npm, :package: pnpm, :yarn: yarn]
````

::: code-group labels=[:package: npm, :package: pnpm, :yarn: yarn]

```bash
npm create astro@latest
```

```bash
pnpm create astro@latest
```

```bash
yarn create astro
```

:::

### Бусад кодын блокийн функцтэй хослуулах

Бүлэг доторх нь энгийн Expressive Code кодын блок хэвээр байх бөгөөд гарчиг, мөрийн дугаар, мөрийн тэмдэглэгээ, эвхэлт, терминалын хүрээ зэрэг функцийг ердийнхөөрөө ашиглаж болно.

::: code-group labels=[Тохиргооны файл, Терминал, Эвхэлт]

```js title="astro.config.mjs" showLineNumbers {2} ins={3}
export default {
  theme: "firefly",
  codeGroup: true,
};
```

```bash title="Байршуулалт"
pnpm build && pnpm preview
```

```js collapse={1-3}
// Эдгээр гурван мөр өгөгдмлөөр эвхэгдэнэ
import { a } from "a";
import { b } from "b";

console.log(a, b);
```

:::

### Зөвхөн кодын блок биш

Tab дотор дурын агуулга, жишээ нь текст, жагсаалт эсвэл зураг байрлуулж болно:

::: code-group labels=[Тайлбар, Жагсаалт]

Энэ бол энгийн догол мөрийн агуулга.

- Жагсаалтын нэгдүгээр зүйл
- Жагсаалтын хоёрдугаар зүйл

:::

> [!TIP]
> Шошгон жагсаалт бүтээх үед үүсдэг бөгөөд өгөгдмлөөр эхний зүйлийг нээлттэй харуулна; хулганы товшилт болон гарын <kbd>←</kbd> / <kbd>→</kbd> / <kbd>Home</kbd> / <kbd>End</kbd> товчоор сольж болно.

### Анхааруулах хайрцгийн дотор ашиглах (MDX компонент)

`::: code-group` болон `::: tip` зэрэг Docusaurus хэв маягийн анхааруулах хайрцгууд бүгд `:::` савны синтакс ашиглах бөгөөд micromark-directive нь эцэг/хүү савны давхар цэгийн тоо ялгаатай байхыг заадаг тул `::: code-group` нь `::: tip` зэрэг анхааруулах хайрцгийн дотор **үүрлэх боломжгүй** (бүхэл блок хүчингүй болно).

Ийм тохиолдолд MDX компонент [`TabGroup`](@/components/common/TabGroup.svelte) ашиглана: MDX компонент нь `:::` зааврын задлан шинжилгээгээр дамждаггүй тул анхааруулах хайрцгийн дотор болон гадна аль алинд нь хэвийн ажиллах бөгөөд ирээдүйд илүү олон UI компонент нэмэхэд ч тохиромжтой. Өгүүллийн өргөтгөлийг `.mdx` болгож, нэгдсэн [`@/components/firefly-mdx`](@/components/firefly-mdx.ts) оролтоос оруулна (олон компонентыг нэг удаа оруулж болно):

````mdx
import { TabGroup } from "@/components/firefly-mdx";

:::tip

<TabGroup labels={["test.js", "test.py"]} client:load>
  ```js
  console.log(1)
  ```

  ```py
  print("hello world")
  ```
</TabGroup>

:::
````

:::tip
- `labels` массив нь кодын блок бүрт шошго зарлах бөгөөд дараалал нь нэг нэгээр харгалзана
- Компонент `client:load`-оор tab солихыг идэвхжүүлнэ
:::
