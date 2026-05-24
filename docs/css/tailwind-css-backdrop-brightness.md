# 顺风 CSS 背景亮度

> 原文:[https://www . geesforgeks . org/tail wind-CSS-background-brightness/](https://www.geeksforgeeks.org/tailwind-css-backdrop-brightness/)

背景亮度类别用于设置图像的亮度。这个类使用图像的线性乘数来增加或减少亮度。顺风 CSS 在 2.1 版本中新增了特色亮度。

**背景亮度等级:**

*   **背景-亮度-0:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(0)。
*   **背景-亮度-50:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(0.5)。
*   **背景-亮度-75:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(0.75)。
*   **背景-亮度-90:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(0.9)。
*   **背景-亮度-95:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(0.95)。
*   **背景-亮度-100:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(1.0)。
*   **背景-亮度-105:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(1.05)。
*   **背景-亮度-110:** 这个类用来设置一个元素上的亮度，相当于 CSS brightness1.10)。
*   **背景-亮度-125:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(1.25)。
*   **背景-亮度-150:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(1.50)。
*   **背景-亮度-200:** 这个类用来设置一个元素上的亮度，相当于 CSS 亮度(2.0)。

**语法:**

```html
<element class="backdrop-filter 
                backdrop-brightness-{amount}">
..
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
    <b>Tailwind CSS Backdrop Brightness Class</b>
    <div class=" mx-16 mt-18 h-36 relative">
        <div class="absolute w-full py-18">
            <img class="rounded-lg object-cover" 
                  src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210605213323/Screenshot20210605213311.png" 
             alt="image">
        </div>
        <div class="relative h-32 flex overflow-x-auto space-x-4">
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-brightness-75 w-1/3">
            </div>
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-brightness-105 w-1/3">
            </div>
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-brightness-150 w-1/3">
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/36a6119f13884b41a72f636cd39a86f2.png)