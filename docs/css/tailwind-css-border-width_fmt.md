# 顺风 CSS 边框宽度

> 原文：[https://www.geeksforgeeks.org/tailwind-css-border-width/](https://www.geeksforgeeks.org/tailwind-css-border-width/)

这个类在顺风 CSS 中接受多个值。所有的属性都包含在类的形式中。它是 [CSS 边框宽度属性](https://www.geeksforgeeks.org/css-border-width-property/)的替代。此类用于设置元素所有四条边的边框宽度。边框宽度属性是四个属性的组合。

### 边框宽度等级

*   `border`
*   `border-0`
*   `border-2`
*   `border-4`
*   `border-8`
*   `border-t`
*   `border-t-0`
*   `border-t-2`
*   `border-t-4`
*   `border-t-8`
*   `border-r`
*   `border-r-0`
*   `border-r-2`
*   `border-r-4`
*   `border-r-8`
*   `border-b`
*   `border-b-0`
*   `border-b-2`
*   `border-b-4`
*   `border-b-8`
*   `border-l`
*   `border-l-0`
*   `border-l-2`
*   `border-l-4`
*   `border-l-8`

### 所有边

在本节中，类已经用于设置元素所有边的边框宽度。这些类是 `border`、`border-0`、`border-2`、`border-4` 和 `border-8`。

**语法：**

```html
<element class="border-{number}">...</element>
```

**示例：**

## 超文本标记语言

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

<b>Tailwind CSS Border Width Class</b>

<div class="mx-4 grid grid-cols-5 gap-2 bg-green-200 p-2">

<!-- First sub div is not for roundig-->
        <div class="border-0 border-green-900 
                    bg-green-400 w-full h-12">
            border-0
        </div>

<div class="border border-green-900 
                    bg-green-400 w-full h-12">
            border
        </div>

<div class="border-2 border-green-900 
                    bg-green-400 w-full h-12">
            border-2
        </div>

<div class="border-4 border-green-900 
                    bg-green-400 w-full h-12">
            border-4
        </div>

<div class="border-8 border-green-900 
                    bg-green-400 w-full h-12">
            border-8
        </div>
    </div>
</body>

</html>
```

**输出：**

![](img/a20ccb58a1bcf6b5ff63914337ba2728.png)

### 单个边

在本节中，类用于设置元素单个边的边框宽度。这些类是 `border-{side}-0`、`border-{side}-2`、`border-{side}-4`、`border-{side}-8` 和 `border-{side}`。

**语法：**

```html
<element class="border-{side}-{number}">...</element>
```

**示例：**

## 超文本标记语言

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

<b>Tailwind CSS Border Width Class</b>

<div class="mx-4 grid grid-cols-4 gap-2 bg-green-200 p-2">

<!-- First sub div is not for roundig-->
        <div class="border-b-2 border-green-900 
                    bg-green-400 w-full h-12">
            border-b-2
        </div>

<div class="border-r-2 border-green-900 
                    bg-green-400 w-full h-12">
            border-r-2
        </div>

<div class="border-l-2 border-green-900 
                    bg-green-400 w-full h-12">
            border-l-2
        </div>

<div class="border-t-2 border-green-900 
                    bg-green-400 w-full h-12">
            border-t-2
        </div>
    </div>
</body>

</html>
```

**输出：**

![](img/8115b66fa07ebe4ff8c699b80243204e.png)