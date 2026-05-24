# 顺风 CSS 落影

> 原文:[https://www.geeksforgeeks.org/tailwind-css-drop-shadow/](https://www.geeksforgeeks.org/tailwind-css-drop-shadow/)

“投影”类用于对图像应用滤镜来设置图像的阴影。这个类在给定的偏移和颜色下创建一个模糊的阴影。在 CSS 中，我们通过使用 [CSS 阴影()函数来实现。](https://www.geeksforgeeks.org/css-drop-shadow-function/)2.1 版本中 Tailwind CSS 新增了特色亮度。

**投影:**

*   **投影-sm:** 这个类用来设置小阴影效果。
*   **投影:**这个类用来设置正常的阴影效果。
*   **投影-md:** 这个类用来设置中等阴影效果。
*   **投影-lg:** 这个类用来设置大阴影效果。
*   **投影-xl:** 这个类用来设置超大阴影效果。
*   **投影-2xl:** 这个类用来设置双超大阴影效果。
*   **暗影-无:**这个职业是用来去除暗影效果的。

**语法:**

```html
<element class="filter drop-shadow-{amount}">..</element>
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
    <b>Tailwind CSS Drop Shadow Class</b>
    <div class="grid grid-flow-col text-center p-4">
        <img class="rounded-lg filter drop-shadow-sm" 
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter drop-shadow" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter drop-shadow-md" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter drop-shadow-lg" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter drop-shadow-2xl" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/213c9099f5c36f5250f0979bf28030ec.png)