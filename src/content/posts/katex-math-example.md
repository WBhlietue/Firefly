---
title: KaTeX математик томьёоны жишээ
published: 1970-01-02
description: Firefly загварын KaTeX математик томьёоны дэмжлэгийг танилцуулах бөгөөд мөрийн томьёо, блок томьёо болон нийлмэл математик тэмдэгтүүдийг багтаана.
tags: [KaTeX, Math, Жишээ]
category: Өгүүллийн жишээ
image: api
slug: katex-math-example
series: "Firefly функцын жишээ2"
seriesOrder: 6
---

Энэ өгүүлэл нь [Firefly](https://github.com/CuteLeaf/Firefly) загварын KaTeX математик томьёо дүрслэх дэмжлэгийг танилцуулна.

## Мөрийн томьёо (Inline)

Мөрийн томьёог нэг `$` тэмдгээр хүрээлж бичнэ.

Жишээ нь: Эйлерийн томьёо $e^{i\pi} + 1 = 0$ нь математикийн хамгийн гоёмсог томьёоны нэг юм.

Масс-энергийн тэгшитгэл $E = mc^2$ нь ч бас өргөн танигдсан.

## Блок томьёо (Block)

Блок томьёог хоёр `$$` тэмдгээр хүрээлж бичих ба голлосон байдлаар харагдана.

$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$

$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

## Нийлмэл жишээ

### Матриц (Matrices)

$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
\begin{pmatrix}
\alpha & \beta \\
\gamma & \delta
\end{pmatrix} =
\begin{pmatrix}
a\alpha + b\gamma & a\beta + b\delta \\
c\alpha + d\gamma & c\beta + d\delta
\end{pmatrix}
$$

### Хязгаар ба нийлбэр (Limits and Sums)

$$
\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}
$$

$$
\lim_{x \to 0} \frac{\sin x}{x} = 1
$$

### Максвеллийн тэгшитгэл (Maxwell's Equations)

$$
\begin{aligned}
\nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \mathbf{B} &= 0 \\
\nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\
\nabla \times \mathbf{B} &= \mu_0\mathbf{J} + \mu_0\varepsilon_0\frac{\partial \mathbf{E}}{\partial t}
\end{aligned}
$$

### Химийн тэгшитгэл (Chemical Equations)

$$
\ce{CH4 + 2O2 -> CO2 + 2H2O}
$$

## Нэмэлт тэмдэгтүүд

| Тэмдэгт | Код | Дүрслэл |
| :--- | :--- | :--- |
| Alpha | `\alpha` | $\alpha$ |
| Beta | `\beta` | $\beta$ |
| Gamma | `\Gamma` | $\Gamma$ |
| Pi | `\pi` | $\pi$ |
| Infinity | `\infty` | $\infty$ |
| Right Arrow | `\rightarrow` | $\rightarrow$ |
| Partial | `\partial` | $\partial$ |

KaTeX-ийн бусад синтаксийг [KaTeX Supported Functions](https://katex.org/docs/supported.html)-аас үзнэ үү.
