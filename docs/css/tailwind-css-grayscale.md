# 顺风 CSS 灰度

> 原文:[https://www.geeksforgeeks.org/tailwind-css-grayscale/](https://www.geeksforgeeks.org/tailwind-css-grayscale/)

灰度类用于对图像应用滤镜来设置图像的灰度。在 CSS 中，我们通过使用 [CSS 灰度()函数](https://www.geeksforgeeks.org/css-grayscale-function/)来实现。顺风 CSS 在 2.1 版本中新增了特色亮度。

**灰度:**

1.  **灰度-0:** 这个类用来表示原始图像。
2.  **灰度:**这个类用来表示效果上的线性乘数。

**语法:**

```html
<element class="filter grayscale | grayscale-0">..</element>
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
    <b>Tailwind CSS Grayscale Class</b>
    <div class="grid grid-flow-col text-center mx-44">
        <img class="rounded-lg filter grayscale" 
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">
        <img class="rounded-lg filter grayscale-0" 
             src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q-100x100.jpg" 
             alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/2a9457c896006587917e9fef2255da2d.png)