---
title: Markdown өргөтгөсөн функцууд
published: 1970-01-01
updated: 1970-01-01
description: "Firefly дахь Markdown функцуудтай танилцана уу"
image: ""
tags: [Жишээ, Демо, Markdown, Firefly]
category: "Өгүүллийн жишээ"
slug: markdown-extended
series: "Firefly функцын жишээ2"
seriesOrder: 2
---

## GitHub репозиторийн карт

Та GitHub репозиторид холбогдсон динамик карт нэмж болох бөгөөд хуудас ачаалагдах үед репозиторийн мэдээлэл GitHub API-аас татагдана.

::github{repo="CuteLeaf/Firefly"}

`::github{repo="CuteLeaf/Firefly"}` кодыг ашиглан GitHub репозиторийн карт үүсгэнэ.

```markdown
::github{repo="CuteLeaf/Firefly"}
```

## Анхааруулах хайрцаг (Admonitions) тохиргоо

Firefly нь [rehype-callouts](https://github.com/lin-stephanie/rehype-callouts) плагиныг ашиглах бөгөөд `GitHub`、`Obsidian`、`VitePress` болон `Docusaurus` гэсэн дөрвөн хэв маягийн сэдвийг дэмжинэ. Та `src/config/siteConfig.ts` дотор тохируулж болно:

```typescript
// src/config/siteConfig.ts
export const siteConfig: SiteConfig = {
  // ...
  rehypeCallouts: {
    // Сонголт: "github" | "obsidian" | "vitepress" | "docusaurus"
    theme: "github",
  },
  // ...
};
```

Анхаар: **Тохиргоог өөрчилсний дараа хөгжүүлэлтийн серверийг дахин эхлүүлснээр хүчин төгөлдөр болно.**

Доорх нь сэдэв бүрийн дэмждэг төрлүүдийн жагсаалт бөгөөд сэдэв бүрийн хэв маяг, синтакс ялгаатай тул хүслээрээ сонгоно уу.

### 1. GitHub хэв маяг

Энэ нь GitHub-ийн албан ёсоор дэмждэг 5 үндсэн төрөл юм.

![GitHub](./images/github.avif)

**Үндсэн синтакс**

```markdown
> [!NOTE] NOTE
> Хэрэглэгчийн анхаарах ёстой мэдээллийг онцлон харуулна.

> [!TIP] TIP
> Хэрэглэгчид илүү амжилттай ажиллахад туслах нэмэлт мэдээлэл.

> [!IMPORTANT] IMPORTANT
> Хэрэглэгчийн амжилтад зайлшгүй шаардлагатай чухал мэдээлэл.

> [!WARNING] WARNING
> Яаралтай анхаарал шаардсан чухал агуулга.

> [!CAUTION] CAUTION
> Үйлдлийн сөрөг болзошгүй үр дагавар.

> [!NOTE] Гарын үсгийн гарчиг
> Энэ бол өөрийн гарчигтай жишээ юм.
```

---

### 2. Obsidian хэв маяг

[Obsidian](https://obsidian.md/) хэв маяг нь маш баялаг төрөл болон alias-г дэмжинэ.

<details>
<summary>Obsidian синтаксийн жагсаалтыг дарж нээх</summary>

```markdown

> [!NOTE] NOTE
> Ерөнхий тэмдэглэлийн блок.

> [!ABSTRACT] ABSTRACT
> Өгүүллийн хураангуй.

> [!SUMMARY] SUMMARY
> Өгүүллийн дүгнэлт (Abstract-тай ижил).

> [!TLDR] TLDR
> Хэт урт, уншихгүй (Abstract-тай ижил).

> [!INFO] INFO
> Нэмэлт мэдээлэл өгнө.

> [!TODO] TODO
> Гүйцэтгэх ёстой зүйлс.

> [!TIP] TIP
> Хэрэгтэй арга эсвэл зөвлөмж.

> [!HINT] HINT
> Илрүүлэг (Tip-тэй ижил).

> [!IMPORTANT] IMPORTANT
> Чухал мэдээлэл (Obsidian хэв маягт ихэвчлэн ижил төстэй icon ашигладаг).

> [!SUCCESS] SUCCESS
> Үйлдэл амжилттай.

> [!CHECK] CHECK
> Шалгалт давсан (Success-тай ижил).

> [!DONE] DONE
> Дууссан (Success-тай ижил).

> [!QUESTION] QUESTION
> Асуулт тавьсан.

> [!HELP] HELP
> Тусламж хүссэн (Question-той ижил).

> [!FAQ] FAQ
> Түгээмэл асуулт (Question-той ижил).

> [!WARNING] WARNING
> Анхааруулах мэдээлэл.

> [!CAUTION] CAUTION
> Анхаарах зүйл (Warning-той ижил).

> [!ATTENTION] ATTENTION
> Анхаарал татсан (Warning-той ижил).

> [!FAILURE] FAILURE
> Үйлдэл бүтэлгүйтсэн.

> [!FAIL] FAIL
> Бүтэлгүйтэл (Failure-тай ижил).

> [!MISSING] MISSING
> Дутуу агуулга (Failure-тай ижил).

> [!DANGER] DANGER
> Аюултай үйлдлийн анхааруулга.

> [!ERROR] ERROR
> Алдааны мэдээлэл (Danger-тай ижил).

> [!BUG] BUG
> Програм хангамжийн алдаа мэдээлэх.

> [!EXAMPLE] EXAMPLE
> Жишээ харуулах.

> [!QUOTE] QUOTE
> Нэг хэсэг ишлэл.

> [!CITE] CITE
> Ишлэл (Quote-той ижил).

> [!NOTE] Гарын үсгийн гарчиг
> Энэ бол өөрийн гарчигтай жишээ юм.
```
</details>

![Obsidian](./images/obsidian.avif)

---

### 3. VitePress хэв маяг

[VitePress](https://vitepress.dev/) хэв маяг нь орчин үеийн, хавтгай өгөгдмөл стилийг санал болгоно. Одоогоор зөвхөн GitHub-тай ижил **5** үндсэн төрлийг агуулна.

<details>
<summary>VitePress синтаксийн жагсаалтыг дарж нээх</summary>

```markdown
> [!NOTE] NOTE
> GitHub-ийн Note-той харгалзана.

> [!TIP] TIP
> GitHub-ийн Tip-той харгалзана.

> [!IMPORTANT] IMPORTANT
> GitHub-ийн Important-той харгалзана.

> [!WARNING] WARNING
> GitHub-ийн Warning-той харгалзана.

> [!CAUTION] CAUTION
> GitHub-ийн Caution-той харгалзана.

> [!TIP] Гарын үсгийн гарчиг
> VitePress хэв маяг ч мөн өөрийн гарчигийг дэмжинэ.
```
</details>

![VitePress](./images/vitepress.avif)

---

### 4. Docusaurus хэв маяг

[Docusaurus](https://docusaurus.io/docs/markdown-features/admonitions) хэв маяг нь орчин үеийн анхааруулах хайрцгийн стилийг санал болгож, 5 төрлийг дэмжинэ.

<details>
<summary>Docusaurus синтаксийн жагсаалтыг дарж нээх</summary>

Дараах төрлийн анхааруулах хайрцгийг дэмжинэ: `note` `tip` `info` `warning` `danger`

```markdown
:::note
Хэрэглэгчийн анхаарах ёстой мэдээллийг хурдан харж байсан ч ойлгомжтой байдлаар онцлон харуулна.
:::

:::tip
Хэрэглэгчид илүү амжилттай ажиллахад туслах нэмэлт мэдээлэл.
:::

:::info
Ерөнхий мэдээлэл.
:::

:::warning
Болзошгүй эрсдэлийн улмаас яаралтай анхаарал шаардсан чухал агуулга.
:::

:::danger
Үйлдлийн сөрөг болзошгүй үр дагавар.
:::

:::tip[Гарын үсгийн гарчиг]
Хэрэглэгчид илүү амжилттай ажиллахад туслах нэмэлт мэдээлэл.
:::
```

</details>

![Docusaurus](./images/docusaurus.avif)

---

## Спойлер

Та текстэд спойлер нэмж болно. Текст нь **Markdown** синтаксийг ч дэмжинэ.

Агуулга :spoiler[нуугдсан **ха-ха**]!

```markdown
Агуулга :spoiler[нуугдсан **ха-ха**]!
```

## Зургийн grid (Image Grid)

`[grid]` болон `[/grid]` шошгыг ашиглан олон зургийг босоогоор зэрэгцүүлэн харуулж болно. Энэ нь зургийн цуглуулга эсвэл харьцуулах зураг харуулахад маш тохиромжтой. Систем нь дотор нь хүрээлэгдсэн зургийн тоогоор (нэг мөрөнд дээд тал нь 4 зураг) responsive grid байрлалыг автоматаар тохируулна.

**Зургийн өндрийг автоматаар дүүргэх:** Нэг мөрөнд өндөр, хэмжээ эсвэл харьцаа нь ялгаатай зургууд байвал «9 нүхтэй цомог» шиг автоматаар дүүрнэ. Богино эсвэл зохицохгүй зургуудыг object-cover ашиглан төгс голлосон crop-аар харах талбарыг нөхнө. Зургийн хүрээ хэвтээгээр яг зэрэгцэж зайгүй болох боловч crop хийгдсэн тул зөвхөн зураг дээр дарж lightbox-оор бүтэн зургийг үзэх боломжтой тул нэг мөрөнд өөр өөр харьцаатай зургийг ашиглахгүй байхыг зөвлөж байна.

**Тайлбар үргэлж доод талд тэгшлэгдэнэ:** Дээрх зургийн өндөр, өргөн хэрхэн өөрчлөгдсөн ч нэг мөрөнд байгаа бүх зургийн тайлбар текст нь төгс хэвтээ суурь шугамд тэгшлэгдэнэ.

[grid]
![Жишээ зураг нэг](./images/firefly1.avif)
![Жишээ зураг хоёр](./images/firefly2.avif)
![Жишээ зураг хоёр](./images/firefly3.avif)
[/grid]

**Үндсэн синтакс**

```markdown
[grid]
![Жишээ зураг нэг](./images/firefly1.avif)
![Жишээ зураг хоёр](./images/firefly2.avif)
![Жишээ зураг хоёр](./images/firefly3.avif)
[/grid]
```


---
