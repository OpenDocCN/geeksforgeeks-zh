# 顺风 CSS 歪斜

> 原文:[https://www.geeksforgeeks.org/tailwind-css-skew/](https://www.geeksforgeeks.org/tailwind-css-skew/)

这个类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受很多值，其中所有的属性都以类的形式被覆盖。**扭曲**用于变换 **2D 平面**中的元素。倾斜一个元素意味着选择一个点，并向不同的方向推或拉它。在 CSS 中，我们可以通过使用 [CSS 偏斜属性来做到这一点。](https://www.geeksforgeeks.org/css-skew-function/)

**偏斜等级:**

*   **歪斜-x-{amount}:** 此类指定 x 轴对应的歪斜角度。
*   **-歪斜-x-{amount}:** 该类指定与反 x 轴对应的歪斜角度。
*   **歪斜-y-{amount}:** 该类指定 y 轴对应的歪斜角度。
*   **-歪斜-y-{amount}:** 此类指定与反 y 轴对应的歪斜角度。

**注释 1:** 首先使用**变换**实用程序启用变换，然后使用**倾斜-x-{amount}** 和**倾斜-y-{amount}** 实用程序指定倾斜角度，从而倾斜元素。

**注 2:****的金额完全取决于你的选择，你可以将其设置为百分比满，或者直接放入*雷姆*值。**

****语法:****

```html
<element class="transform skew-{axis}-{amount}">...</element>
```

****例 1:** 正 x 轴和 y 轴对应的斜角。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet">
</head>

<body class="text-center">
    <h1 class="text-green-600 text-5xl font-bold">
    GeeksforGeeks
    </h1>
    <b>Tailwind CSS Skew Class</b>
    <div class="bg-green-300
                mx-16
                p-4
                justify-between
                grid grid-flow-col">
    <div class="bg-no-repeat
                w-16 h-16 transform skew-x-0"
        style=
        "background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    <div class="bg-no-repeat
                w-16 h-16 transform skew-x-12"
        style=
        "background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    <div class="bg-no-repeat
                w-16 h-16 transform skew-y-6"
        style="background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    <div class="bg-no-repeat
                w-16 h-16 transform skew-y-12"
        style="background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    </div>
</body>
</html>
```

****输出:****

**![](img/4fb650d64ee5a0d4ce8221ff6a24e879.png)**

****例 2:** 与反 *x 轴*和 *y 轴*对应的斜角。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet">
</head>

<body class="text-center">
    <h1 class="text-green-600 text-5xl font-bold">
    GeeksforGeeks
    </h1>
    <b>Tailwind CSS Skew Class</b>
    <div class="bg-green-300
                mx-16
                p-4
                justify-between
                grid grid-flow-col">
    <div class="bg-no-repeat
                w-16 h-16 transform -skew-x-6"
        style=
        "background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    <div class="bg-no-repeat
                w-16 h-16 transform -skew-x-12"
        style=
        "background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    <div class="bg-no-repeat
                w-16 h-16 transform -skew-y-6"
        style="background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    <div class="bg-no-repeat
                w-16 h-16 transform -skew-y-12"
        style="background-image:url(
https://media.geeksforgeeks.org/wp-content/uploads/20210222211217/Screenshot20210222211207.png)">
    </div>
    </div>
</body>
</html>
```

****输出:****

**![](img/fbbee1e07363f851024f00bd6caebcf8.png)**