# 顺风 CSS 亮度

> 原文:[https://www.geeksforgeeks.org/tailwind-css-brightness/](https://www.geeksforgeeks.org/tailwind-css-brightness/)

亮度类别用于设置图像的亮度。这个类使用图像的线性乘数来增加或减少亮度。在 CSS 中，我们通过使用 [CSS 亮度()函数](https://www.geeksforgeeks.org/css-brightness-function/)来实现。顺风 CSS 在 2.1 版本中新增了特色亮度。

**亮度:**

*   **亮度-0:** 这个类用来设置相当于 CSS 亮度(0)的亮度。
*   **亮度-50:** 这个类用来设置相当于 CSS 亮度(0.5)的亮度。
*   **亮度-75:** 这个类用来设置相当于 CSS 亮度(0.75)的亮度。
*   **亮度-90:** 这个类用来设置相当于 CSS 亮度(0.9)的亮度。
*   **亮度-95:** 这个类用来设置相当于 CSS 亮度(0.95)的亮度。
*   **亮度-100:** 这个类用来设置相当于 CSS 亮度(1.0)的亮度。
*   **亮度-105:** 这个类用来设置相当于 CSS 亮度(1.05)的亮度。
*   **亮度-110:** 这个类用来设置相当于 CSS brightness1.10 的亮度。
*   **亮度-125:** 这个类用来设置相当于 CSS 亮度(1.25)的亮度。
*   **亮度-150:** 这个类用来设置相当于 CSS 亮度(1.50)的亮度。
*   **亮度-200:** 这个类用来设置相当于 CSS 亮度(2.0)的亮度。

**语法:**

```html
<element class="filter brightness-{amount}">..</element>
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
    <b>Tailwind CSS brightness Class</b>
    <div class="grid grid-flow-col text-center p-4">
        <img class="rounded-lg filter brightness-0" 
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter brightness-50" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter brightness-75" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter brightness-110" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter brightness-200" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/6d74d926626c0898357e523026f8fed8.png)