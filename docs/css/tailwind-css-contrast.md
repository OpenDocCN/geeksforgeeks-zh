# 顺风 CSS 对比

> 原文:[https://www.geeksforgeeks.org/tailwind-css-contrast/](https://www.geeksforgeeks.org/tailwind-css-contrast/)

对比度类用于设置图像的对比度。此类可以增加或减少对比度。在 CSS 中，我们通过使用 [CSS 对比度()函数](https://www.geeksforgeeks.org/css-contrast-function/)来实现。顺风 CSS 在 2.1 版本中新增了特色亮度。

**对比:**

*   **对比度-0:** 此类用于设置与 CSS 对比度(0)相当的对比度。
*   **对比度-50:** 这个类用来设置相当于 CSS 对比度(0.5)的对比度。
*   **对比度-75:** 这个类用来设置相当于 CSS 对比度(0.75)的对比度。
*   **对比度-100:** 这个类用来设置相当于 CSS 对比度(1.0)的对比度。
*   **对比度-125:** 这个类用来设置相当于 CSS 对比度(1.25)的对比度。
*   **对比度-150:** 这个类用来设置相当于 CSS 对比度(1.50)的对比度。
*   **对比度-200:** 这个类用来设置相当于 CSS 对比度(2.0)的对比度。

**语法:**

```html
<element class="filter Contrast-{amount}">..</element>
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
    <b>Tailwind CSS contrast Class</b>
    <div class="grid grid-flow-col text-center p-4">
        <img class="rounded-lg filter contrast-0" 
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter contrast-50" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter contrast-75" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter contrast-110" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter contrast-200" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/5de06edd1b34a8b524362b95f51ffe59.png)