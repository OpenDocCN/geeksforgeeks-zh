# 顺风 CSS 背景对比

> 原文:[https://www . geesforgeks . org/tail wind-CSS-background-contrast/](https://www.geeksforgeeks.org/tailwind-css-backdrop-contrast/)

背景对比度类用于设置图像的对比度。此类可以增加或减少对比度。顺风 CSS 在 2.1 版本中新增了特色亮度。

**背景对比:**

*   **background-contrast-0:**这个类用来在一个元素上设置相当于 CSS contrast(0)的对比度。
*   **背景-对比度-50:** 这个类用来设置元素上的对比度，相当于 CSS 对比度(0.5)。
*   **背景-对比度-75:** 这个类用来设置元素上的对比度，相当于 CSS 对比度(0.75)。
*   **background-contrast-100:**这个类用来在一个元素上设置相当于 CSS 对比度(1.0)的对比度。
*   **背景-对比度-125:** 这个类用来设置一个元素上的对比度，相当于 CSS 对比度(1.25)。
*   **背景-对比度-150:** 这个类用来设置元素上的对比度，相当于 CSS 对比度(1.50)。
*   **background-contrast-200:**这个类用来在一个元素上设置相当于 CSS 对比度(2.0)的对比度。

**语法:**

```html
<element class="filter backdrop-contrast-{amount}">..</element>
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
    <b>Tailwind CSS Backderop Contrast Class</b>
    <div class=" mx-16 mt-18 h-36 relative">
        <div class="absolute w-full py-18">
            <img class="rounded-lg object-cover" 
          src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210605213323/Screenshot20210605213311.png" 
             alt="image">
        </div>
        <div class="relative h-32 flex overflow-x-auto space-x-4">
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-contrast-75 w-1/3">
            </div>
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-contrast-110 w-1/3">
            </div>
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-contrast-200 w-1/3">
            </div>

        </div>

    </div>
</body>

</html>
```

**输出:**

![](img/b65fd8be7af053a99da127090d7eb003.png)