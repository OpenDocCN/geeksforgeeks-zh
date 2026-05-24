# 顺风 CSS 背景灰度

> 原文:[https://www . geesforgeks . org/tail wind-CSS-background-grade/](https://www.geeksforgeeks.org/tailwind-css-backdrop-grayscale/)

“背景灰度”类用于对图像应用滤镜来设置图像的灰度。顺风 CSS 在 2.1 版本中新增了特色亮度。

**背景灰度:**

*   **背景-灰度-0:** 这个类用来表示原始元素。
*   **背景-灰度:**这个类用来表示元素效果上的线性乘数。

**语法:**

```html
<element class="filter backdrop-grayscale | 
         backdrop-grayscale-0">
    /* ... */
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

  <b>Tailwind CSS Backderop Grayscale Class</b>

  <div class=" mx-16 mt-18 h-36 relative">
    <div class="absolute w-full py-18">
      <img class="rounded-lg object-cover" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210605213323/Screenshot20210605213311.png" 
       alt="image">
    </div>

    <div class="relative h-32 flex overflow-x-auto space-x-4">
      <div class="flex-shrink-0 border-4 border-green-500 
           backdrop-filter backdrop-grayscale w-1/2">
      </div>

      <div class="flex-shrink-0 border-4 border-green-500 
           backdrop-filter backdrop-grayscale-0 w-1/2">
      </div>
    </div>
  </div>
</body>

</html>
```

**输出:**

![](img/4277490dfa203ba941ce1d8cba53d0f5.png)