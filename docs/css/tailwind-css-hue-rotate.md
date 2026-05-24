# 顺风 CSS 色相旋转

> 原文:[https://www.geeksforgeeks.org/tailwind-css-hue-rotate/](https://www.geeksforgeeks.org/tailwind-css-hue-rotate/)

色调旋转类是一个内置函数，用于对图像应用滤镜来设置图像的色调旋转。在 CSS 中，我们通过使用 [CSS 色相-旋转()函数](https://www.geeksforgeeks.org/css-hue-rotate-function/)来实现。顺风 CSS 在 2.1 版本中新增了特色亮度。

**色调旋转:**

*   **-色相-旋转-180:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(-180)。
*   **-色相-旋转-90:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(-90)。
*   **-色相-旋转-60:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(-60)。
*   **-色相-旋转-30:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(-30)。
*   **-色相-旋转-15:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(-15)。
*   **色相-旋转-0:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(0)。
*   **色相-旋转-15:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(15)。
*   **色相-旋转-30:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(30)。
*   **色相-旋转-60:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(60)。
*   **色相-旋转-90:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(90)。
*   **色相-旋转-180:** 这个类用来设置色相-旋转等价于 CSS 色相-旋转(180)。

**语法:**

```html
<element class="filter hue-rotate-{amount}">..</element>
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
    <b>Tailwind CSS Hue Rotate Class</b>
    <div class="grid grid-flow-col text-center p-4">
        <img class="rounded-lg filter -hue-rotate-180" 
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter -hue-rotate-60" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter -hue-rotate-0" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter hue-rotate-60" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter hue-rotate-180" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/dfe5dbe5feb164dc99bdd1a470926381.png)