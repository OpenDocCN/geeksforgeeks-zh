# CSS |特异性

> 原文:[https://www.geeksforgeeks.org/css-specificity/](https://www.geeksforgeeks.org/css-specificity/)

当一组以上的 CSS 规则应用于同一个元素时，浏览器必须决定哪个特定的规则集将应用于该元素。浏览器遵循的规则统称为**特异性**

**特异性规则包括:**

*   通过引用外部样式表应用的 CSS 样式优先级最低，被内部和内联 CSS 覆盖。
*   内部 CSS 被内联 CSS 覆盖。
*   内联 CSS 具有最高优先级，并覆盖所有其他选择器。

**示例:**

## 超文本标记语言

```html
<html>

<head>
    <link rel="stylesheet" type="text/css" href="external.css">
    <style type="text/css">
        h1 {
            background-color: red;
            color: white;
        }

        h2 {
            color: blue;
        }
    </style>
</head>

<body>
    <h1>
        Internal CSS overrides external CSS
    </h1>
    <h2 style="color: green;">
        Inline CSS overrides internal CSS
    </h2>
</body>

</html>
```

**【例-1 的**:

## 超文本标记语言

```html
h1{
    background-color: lightgreen;
}
h2{
    color: pink;
}
```