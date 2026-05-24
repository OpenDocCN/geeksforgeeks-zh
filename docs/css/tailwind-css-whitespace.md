# 泰国风 CSS 白色空间

> 原文:[https://www.geeksforgeeks.org/tailwind-css-whitespace/](https://www.geeksforgeeks.org/tailwind-css-whitespace/)

该类在[顺风 CSS](https://www.geeksforgeeks.org/css-tailwind-introduction/) 中接受多个值。所有的属性都包含在类的形式中。它是 [CSS 空白属性的替代品。](https://www.geeksforgeeks.org/css-white-space-property/)此类用于控制文本换行和白间距。此属性中有几种类型的值可供使用。

**空白类:**

*   **空白-正常**
*   **空白-nowrap**
*   **空白-前置**
*   **空白-行前**
*   **空白-预包装**

**空白-正常:**这是这个类的默认值。当顺风的*空白*类别设置为正常时，两个或更多空白的每个序列将作为单个空白出现。元素中的内容将在任何需要的地方换行。

**语法:**

```html
<element class="whitespace-normal">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
          rel="stylesheet">
</head>

<body class="text-center mx-4 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Whitespace Class</b>
    <div class="mx-24 bg-green-200 rounded-lg">
        <p class="p-4 whitespace-normal text-justify">
            Geeksforgeeks: A Computer Science portal for Geeks
            those who wants to pursue an engineering degree or
            wants to create a career on engineering field.
        </p>

    </div>
</body>

</html>
```

**输出:**

![](img/9a4839baf6d7c1d20544c9e509947d1f.png)

空白-正常

**空白-无 rap:** 当顺风的*空白*类别设置为*无 rap 时，*两个或更多空白的每个序列将作为单个*空白*出现。除非明确指定，否则元素中的内容不会换行。

**语法:**

```html
<element class="whitespace-nowrap">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
          rel="stylesheet">
</head>

<body class="text-center mx-4 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Whitespace Class</b>
    <div class="mx-24 bg-green-200 rounded-lg">
        <p class="p-4 whitespace-nowrap text-justify">
            Geeksforgeeks: A Computer Science portal for Geeks
            those who wants to pursue an engineering degree or
            wants to create a career on engineering field.
        </p>

    </div>
</body>

</html>
```

**输出:**

![](img/16dc17ffa6f5d39909447ecd747af005.png)

空白-nowrap

**空白-pre:** 该值使空白具有与 HTML 中的[<【pre】>](https://www.geeksforgeeks.org/html-pre-tag/)标签相同的效果。元素中的内容只有在使用换行符指定时才会换行。

**语法:**

```html
<element class="whitespace-pre">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
          rel="stylesheet">
</head>

<body class="text-center mx-4 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Whitespace Class</b>
    <div class="mx-24 bg-green-200 rounded-lg">
        <p class="p-4 whitespace-pre text-justify">
            Geeksforgeeks: A Computer Science portal for Geeks
            those who wants to pursue an engineering degree or
            wants to create a career on engineering field.
        </p>

    </div>
</body>

</html>
```

**输出:**

![](img/d276c1e20ff847d05a3870e2c5eedc77.png)

空白前置

**空白-行前:**当 tailwind 的空白类设置为行前值时，两个或更多空白的每个序列将作为单个空白出现。当需要和明确指定时，元素中的内容将被包装。

**语法:**

```html
<element class="whitespace-pre-line">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
          rel="stylesheet">
</head>

<body class="text-center mx-4 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Whitespace Class</b>
    <div class="mx-24 bg-green-200 rounded-lg">
        <p class="p-4 whitespace-pre-line text-justify">
            Geeksforgeeks: A Computer Science portal for Geeks
            those who wants to pursue an engineering degree or
            wants to create a career on engineering field.
        </p>

    </div>
</body>

</html>
```

**输出:**

![](img/8804af98637757b78b0862960f7c39f0.png)

空白-行前

**空白-预换行:**当顺风的*空白*类被设置为一个行前值时，每个空白序列将按原样出现。当需要和明确指定时，元素中的内容将被包装。

**语法:**

```html
<element class="whitespace-pre-wrap">...</element>
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<head>
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
          rel="stylesheet">
</head>

<body class="text-center mx-4 space-y-2">
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1>
    <b>Tailwind CSS Whitespace Class</b>
    <div class="mx-24 bg-green-200 rounded-lg">
        <p class="p-4 whitespace-pre-wrap text-justify">
            Geeksforgeeks: A Computer Science portal for Geeks
            those who wants to pursue an engineering degree or
            wants to create a career on engineering field.
        </p>

    </div>
</body>

</html>
```

**输出:**

![](img/186559b7726146b09c40b423efab8142.png)

空白预包装