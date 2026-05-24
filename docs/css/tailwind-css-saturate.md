# 泰国风 CSS 饱和

> 原文:[https://www.geeksforgeeks.org/tailwind-css-saturate/](https://www.geeksforgeeks.org/tailwind-css-saturate/)

顺风 CSS **饱和**类是一个内置函数，用于对输入图像进行过饱和或去饱和。在 CSS 中，我们通过使用 [CSS 饱和()函数](https://www.geeksforgeeks.org/css-Saturate-function/)来实现。顺风 CSS 在 2.1 版本中新增了特色亮度。

**饱和等级:**

*   **饱和-0:** 这个类用来设置饱和值，相当于 CSS 饱和(0)。
*   **饱和-50:** 这个类用来设置饱和值，相当于 CSS 饱和(50)。
*   **饱和-100:** 这个类用来设置饱和值，相当于 CSS 饱和(100)。
*   **饱和-150:** 这个类用来设置饱和值，相当于 CSS 饱和(150)。
*   **饱和-200:** 这个类用来设置饱和值，相当于 CSS 饱和(200)。

**语法:**

```html
<element class="filter saturate-{amount}">..</element>
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
    <b>Tailwind CSS Saturate Class</b>
    <div class="grid grid-flow-col text-center p-4">
        <img class="rounded-lg filter saturate-0" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
             alt="image">
        <img class="rounded-lg filter saturate-50" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
             alt="image">
        <img class="rounded-lg filter saturate-75" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
             alt="image">
        <img class="rounded-lg filter saturate-110" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
             alt="image">
        <img class="rounded-lg filter saturate-200" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
             alt="image">
    </div>
</body>

</html>
```

**输出:**

![](img/9bd2a16706c224a71f85abaf8c268e8c.png)