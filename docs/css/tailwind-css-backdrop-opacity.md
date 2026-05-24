# 泰风 CSS 背降不透明

> 原文:[https://www . geesforgeks . org/tail wind-CSS-background-opacity/](https://www.geeksforgeeks.org/tailwind-css-backdrop-opacity/)

背景不透明度类是一个内置函数，用于对图像应用滤镜，将图像转换为棕褐色图像。在 CSS 中，我们通过使用 [CSS 不透明度()函数来实现。](https://www.geeksforgeeks.org/css-opacity-function/)2.1 版本中 Tailwind CSS 新增了特色亮度。

**背景不透明度:**

*   **背景-不透明度-编号:**

**注:**这里的数字是一个变量，可以用 0 到 100 代替，间隔 5，如 5，10，15 ……。高达 100。

**语法:**

```html
<element class="filter backdrop-opacity-{number}">..</element>
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
    <b>Tailwind CSS Backdrop Opacity Class</b>
    <div class=" mx-16 mt-18 h-36 relative">
        <div class="absolute w-full py-18">
            <img class="rounded-lg object-cover" 
            src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210605213323/Screenshot20210605213311.png" 
            alt="image">
        </div>
         <div class="relative h-32 flex overflow-x-auto space-x-4">
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-hue-rotate-90 w-1/2">
            </div>
            <div class="flex-shrink-0 border-4 border-green-500 
                        backdrop-filter backdrop-hue-rotate-90 
                        backdrop-opacity-25 w-1/2">
            </div>
        </div>        
    </div>
</body>

</html>
```

**输出:**

![](img/23ca98aec7bdd5932b04f705562f381f.png)