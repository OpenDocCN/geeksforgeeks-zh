# 顺风 CSS 分幅

> 原文:[https://www.geeksforgeeks.org/tailwind-css-divide-width/](https://www.geeksforgeeks.org/tailwind-css-divide-width/)

这个类接受 [<u>顺风 CSS</u>](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中的大量值，其中所有属性都以类的形式覆盖。这个类用来创建元素间的划分作为边框。为了实现这一点，CSS 中使用了 [CSS 边框-顶宽属性](https://www.geeksforgeeks.org/css-border-top-width-property/)或 [CSS 边框-底宽属性](https://www.geeksforgeeks.org/css-border-bottom-width-property/)。

**划分宽度等级:**

*   **divide-x:** 该类用于设置 x 轴分割线。
*   **除-x-反:**此类用于设置 x 轴反除。
*   **divide-y:** 该类用于设置 y 轴分割线。
*   **分-y-反:**此类用于设置 y 轴反分。

**注意:**除-y-{amount}和除-x-{amount}的个数可以在 0 到 8 之间变化，跨度为 2。

**添加水平子元素之间的边框:**在本节中，我们要使用 *divide-x-{amount}* 实用程序来添加水平元素之间的边框。

**语法:**

```html
<element class="divide-x-{number}">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
<head> 
    <link
    href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold"> 
    GeeksforGeeks 
    </h1> 
    <b>Tailwind CSS Divide Width Class</b> 
    <div class="mx-4 bg-green-200 p-2">
        <div class="grid grid-cols-3 divide-x-4 
                    divide-green-500">
            <div>GeeksforGeeks</div>
            <div>A Computer Science Portal</div>
            <div>For Geeks</div>
        </div>
    </div>
</body> 
</html>
```

**输出:**

![](img/52216af9de6094620cfa30fb54187670.png)

**在垂直子元素之间添加边框:**在本节中，我们希望使用 *divide-y-{amount}* 实用程序来划分垂直元素之间的边框。

**语法:**

```html
<element class="divide-y-{number}">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
<head> 
    <link
    href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold"> 
    GeeksforGeeks 
    </h1> 
    <b>Tailwind CSS Divide Width Class</b> 
    <div class="mx-4 bg-green-200 p-2">
        <div class="grid grid-cols-1 divide-y-4
                    divide-green-500">
            <div>GeeksforGeeks</div>
            <div>A Computer Science Portal</div>
            <div>For Geeks</div>
        </div>
    </div>
</body> 
</html>
```

**输出:**

![](img/2fc9b450b1edbb1089c0be9f691577d1.png)

**在水平子元素之间添加边框:**在本节中，我们希望确保将边框添加到每个元素的正确一侧。为此，使用*折行反转*或*折列反转*，然后使用*分割 x 反转*或*分割 y 反转*。

**语法:**

```html
<element class="divide-{axis}-reverse">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 
<head> 
    <link
    href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold"> 
    GeeksforGeeks 
    </h1> 
    <b>Tailwind CSS Divide Width Class</b> 
    <div class="mx-4 bg-green-200 p-2">
        <div class="flex flex-col-reverse divide-y-4 
                    divide-y-reverse divide-green-500">
            <div>GeeksforGeeks</div>
            <div>A Computer Science Portal</div>
            <div>For Geeks</div>
        </div>
    </div>
</body> 
</html>
```

**输出:**

![](img/6bca9c3d1adc50b74848a4eba25166a8.png)

划分反向类