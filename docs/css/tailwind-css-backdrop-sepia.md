# 顺风 CSS 背景棕

> 原文:[https://www.geeksforgeeks.org/tailwind-css-backdrop-sepia/](https://www.geeksforgeeks.org/tailwind-css-backdrop-sepia/)

背景棕褐色类是一个内置类，用于对图像应用滤镜，将图像转换为棕褐色图像。顺风 CSS 在 2.1 版本中新增了特色亮度。

**背景棕褐色:**

*   **背景色-棕褐色-0:** 此类用于表示原始图像
*   **背景色-棕褐色:**此类用于表示棕褐色图像。

**语法:**

```html
<element class="filter backdrop-sepia |
    backdrop-sepia-0">
</element>
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

<body class="text-center mx-4 ">
  <h1 class="text-green-600 text-5xl font-bold">
      GeeksforGeeks
  </h1>

  <b>Tailwind CSS Backdrop Sepia Class</b>

  <div class=" mx-16 mt-18 h-36 relative">
    <div class="absolute w-full py-18">
      <img class="rounded-lg object-cover" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210605213323/Screenshot20210605213311.png" 
        alt="image">
    </div>

    <div class="relative h-32 flex overflow-x-auto space-x-4">
        <div class="flex-shrink-0 border-4 border-green-500 
             backdrop-filter backdrop-sepia-0 w-1/2">
        </div>

        <div class="flex-shrink-0 border-4 border-green-500 
             backdrop-filter backdrop-sepia w-1/2">
        </div>
    </div>

  </div>
</body>

</html>
```

**输出:**

![](img/cdea5d8d83b2cf26caf429d98d9f9c2a.png)