# 泰风 CSS sepa

> 原文:[https://www.geeksforgeeks.org/tailwind-css-sepia/](https://www.geeksforgeeks.org/tailwind-css-sepia/)

棕褐色类是一个内置类，用于对图像应用滤镜，将图像转换为棕褐色图像。在 CSS 中，我们通过使用 [CSS sepia()函数](https://www.geeksforgeeks.org/css-Sepia-function/)来实现。顺风 CSS 在 2.1 版本中新增了特色亮度。

**乌贼:**

*   **棕褐色-0:** 此类用于表示原始图像
*   **棕褐色:**此类用于表示棕褐色图像。

**语法:**

```html
<element class="filter sepia| sepia-0">..</element>
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
    <b>Tailwind CSS Sepia Class</b>
    <div class="grid grid-flow-col text-center mx-44">
        <img class="rounded-lg filter sepia" 
            src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
            alt="image">
        <img class="rounded-lg filter sepia-0" 
            src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210604014825/QNHrwL2q.jpg" 
            alt="image">

    </div>
</body>

</html>
```

**输出:**

![](img/b6d0b0558912b8e96adeed2826ec0dc3.png)