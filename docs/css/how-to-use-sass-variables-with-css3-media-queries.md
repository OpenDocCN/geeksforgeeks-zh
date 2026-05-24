# 如何在 CSS3 媒体查询中使用 Sass 变量？

> 原文:[https://www . geeksforgeeks . org/how-用法-sass-变量-with-css3-media-query/](https://www.geeksforgeeks.org/how-to-use-sass-variables-with-css3-media-queries/)

**SASS 变量:** SASS 变量非常容易理解和使用。SASS 变量为以$符号开头的名称赋值，然后只引用该名称而不是该值。尽管如此，它们是 SASS 提供的最有用的工具之一。
SASS 变量提供以下特性:

*   减少重复
*   做复杂的数学
*   配置库
*   还有更多…

**CSS 媒体查询:** CSS 媒体查询是 CSS3 的特性，它允许指定何时必须应用给定的 CSS 规则。媒体查询工作时要记住设备的功能。它们可以用来检查很多东西，例如:

*   视口的宽度和高度
*   设备的宽度和高度
*   方向(横向或纵向)
*   设备的分辨率

在 CSS3 媒体查询中使用 SASS 变量并不容易实现。只有当 SASS 将查询的所有属性抓取到包含 SASS 变量的样式表中，然后对它们进行相应的更改时，这才是可能的。
有两种方式可以做到:

*   使用[CSS 后变量](https://www.npmjs.com/package/postcss-variables)
*   使用[混合](https://www.geeksforgeeks.org/sass-mixin-and-include/)

**使用后期 CSS 变量:**下面的例子非常适合 SASS(即使对于较旧的浏览器)。

## 钢性铸铁

```html
$width1: 1280px;
$width2: 1720px;

:root {
    f-size: 20px;
    f-family: Helvetica, sans-serif;
}

@media (min-width: $width1) and (max-width: $width2) {
    :root {
        f-size: 22px;
        f-family: Helvetica;
        ;
    }
}

@media (min-width: $mq-hhd) {
    :root {
        f-size: 24px;
        f-family: sans-serif;
        ;
    }
}

.my-element {
    font-size: var(f-size);
    color: red;
    font-family: var(f-family);
}
```