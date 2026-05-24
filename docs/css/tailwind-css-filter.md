# 顺风 CSS 滤镜

> 原文:[https://www.geeksforgeeks.org/tailwind-css-filter/](https://www.geeksforgeeks.org/tailwind-css-filter/)

filter 类用于设置元素的视觉效果。这个类主要用于图像内容。在 CSS 中，我们通过使用 [CSS 过滤器属性](https://www.geeksforgeeks.org/css-filter-property/)来实现。Tailwind CSS 在 2.1 版本中新增了功能过滤器。

**过滤等级:**

*   **过滤器:**该类用于启用过滤器。
*   **过滤器-无:**此类用于移除过滤器。

**语法:**

```html
<element class="filter">..</element>
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

<body class="text-center mx-4 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Filter Class</b>
    <div class="grid grid-flow-col text-center p-4">
        <img class="rounded-lg filter brightness-50" 
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter invert" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter blur-lg" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter contrast-125" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter grayscale" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/10fd134e6dc0dc80d572134a9dc04090.png)