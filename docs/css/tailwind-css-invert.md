# 泰国风 CSS 反转

> 原文:[https://www.geeksforgeeks.org/tailwind-css-invert/](https://www.geeksforgeeks.org/tailwind-css-invert/)

反转类是一个内置函数，用于对图像应用过滤器，以设置样本图像颜色的反转版本。在 CSS 中，我们通过使用 [CSS 反转()函数](https://www.geeksforgeeks.org/css-invert-function/)来实现。

**反转等级:**

*   **反转-0:** 这个类用来表示原始颜色。
*   **反转:**这个类用来表示那个原始颜色的反转颜色。

**语法:**

```html
<element class="filter invert | invert-0">..</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link href=
"https://unpkg.com/tailwindcss@^2.1/dist/tailwind.min.css"
        rel="stylesheet">
</head>

<body class="text-center mx-20 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Invert Class</b>
    <div class="grid grid-flow-col text-center mx-44">
        <img class="rounded-lg filter invert" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
             alt="image">
        <img class="rounded-lg filter invert-0" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/e86cf690b76cc27ab0e3462072e3439d.png)