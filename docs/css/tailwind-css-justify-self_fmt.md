# Tailwind CSS justify-self

> 原文：[https://www.geeksforgeeks.org/tailwind-css-justify-self/](https://www.geeksforgeeks.org/tailwind-css-justify-self/)

这个类在 Tailwind CSS 中接受两个值。不同的属性包含在类表单中。它是 [`CSS justify-self` 属性](https://www.geeksforgeeks.org/css-justify-self-property/)的替代品。此类用于指定 CSS 网格中内容位置与适当轴的对齐方式。

**`justify-self` 类选项：**

*   `justify-self-auto`
*   `justify-self-start`
*   `justify-self-end`
*   `justify-self-center`
*   `justify-self-stretch`

**自对齐：** 是用于根据网格的 `self-alignment` 类的值对齐项目的值。

**语法：**

```html
<element class="justify-self-auto">...</element>
```

**示例：**

## HTML

```html
<!DOCTYPE html> 
<head> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 
    <b>Tailwind CSS Justify Self Class</b> 
    <div id="main" class="grid justify-items-stretch grid-cols-2"> 
        <div class="justify-self-auto bg-green-500 rounded-lg m-4 h-12">

        </div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">2</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">3</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">4</div>
    </div> 
</body> 

</html>
```

**输出：**

![](img/4f07ffa9b50b7b0031f6afb928ac5674.png)

**`justify-self-start`：** 它允许内容自身对齐单元格的左侧。

**语法：**

```html
<element class="justify-self-start">...</element>
```

**示例：**

## HTML

```html
<!DOCTYPE html> 
<head> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 
    <b>Tailwind CSS Justify Self Class</b> 
    <div id="main" class="grid justify-items-stretch grid-cols-2"> 
        <div class="justify-self-start 
            bg-green-500 rounded-lg m-4 h-12">1</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">2</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">3</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">4</div>
    </div> 
</body> 

</html>
```

**输出：**

![](img/501ae50997ba53fd602e660205fa03ac.png)

**`justify-self-end`：** 它允许内容自身对齐单元格的右侧。

**语法：**

```html
<element class="justify-self-end">...</element>
```

**示例：**

## HTML

```html
<!DOCTYPE html> 
<head> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 
    <b>Tailwind CSS Justify Self Class</b> 
    <div id="main" class="grid justify-items-stretch grid-cols-2"> 
        <div class="justify-self-end bg-green-500 
            rounded-lg m-4 h-12">1</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">2</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">3</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">4</div>
    </div> 
</body> 

</html>
```

**输出：**

![](img/ef93a42ba3c2f4085764ea038a27a2b5.png)

**`justify-self-center`：** 它允许内容自身与单元格的中心对齐。

**语法：**

```html
<element class="justify-self-center">...</element>
```

**示例：**

## HTML

```html
<!DOCTYPE html> 
<head> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 
    <b>Tailwind CSS Justify Self Class</b> 
    <div id="main" class="grid justify-items-stretch grid-cols-2"> 
        <div class="justify-self-center bg-green-500 
            rounded-lg m-4 h-12">1</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">2</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">3</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">4</div>
    </div> 
</body> 

</html>
```

**输出：**

![](img/f0849fc45111ad4a2a905a7a5f7dc5e2.png)

**`justify-self-stretch`：** 这是该属性的默认值，它使内容填充单元格的整个宽度。

**语法：**

```html
<element class="justify-self-stretch">...</element>
```

**示例：**

## HTML

```html
<!DOCTYPE html> 
<head> 
    <link href=
"https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" 
          rel="stylesheet"> 
</head> 

<body class="text-center"> 
    <h1 class="text-green-600 text-5xl font-bold">
        GeeksforGeeks
    </h1> 
    <b>Tailwind CSS Justify Self Class</b> 
    <div id="main" class="grid justify-items-stretch grid-cols-2"> 
        <div class="justify-self-stretch bg-green-500 
            rounded-lg m-4 h-12">1</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">2</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">3</div> 
        <div class="bg-green-500 rounded-lg m-4 h-12">4</div>
    </div> 
</body> 

</html>
```

**输出：**

![](img/3c7782eb09d8403ba3e574eb3af7fc52.png)