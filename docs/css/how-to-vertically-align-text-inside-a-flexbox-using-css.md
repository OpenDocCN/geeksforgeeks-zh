# 如何使用 CSS 在 flexbox 内部垂直对齐文本？

> 原文:[https://www . geeksforgeeks . org/如何在 flexbox 内部垂直对齐文本-使用-css/](https://www.geeksforgeeks.org/how-to-vertically-align-text-inside-a-flexbox-using-css/)

**CSS flex box:**CSS 中的 flex 属性是 flex-grow、flex-short 和 flex-based 属性的组合。用于设置柔性物品的长度。flex 属性响应速度快，移动友好。很容易定位子元素和主容器。页边距不会随着内容页边距而折叠。无需编辑 HTML 部分，任何元素的顺序都可以轻松更改。几年前，flexbox 被添加到 CSS 标准中，用于管理空间分布和元素对齐。基本上是一维布局语法。

**垂直居中对齐:**flex box 属性用于将内容设置为垂直对齐。通过设置以下显示属性，可以垂直对齐文本内容:

*   对齐项目
*   调整内容
*   挠曲方向

对齐项目和对齐内容是绝对水平和垂直居中文本的重要属性。水平居中由对齐内容属性管理，垂直居中由对齐项属性管理。

**示例 1:** 本示例将文本内容设置为垂直居中对齐。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        Vertically align text content
    </title>

    <!-- CSS property to vertical align text
        content using flex-box -->
    <style>
        .GFG {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            width: 100%;
            text-align: center;
            min-height: 400px;
            background-color: green;
            align-items: center;
        }
    </style>
</head>

<body>
    <div class="GFG">
        <h1>GeeksforGeeks</h1>
        <h2>Vertically align text using Flexbox</h2>
    </div>
</body>

</html>
```

**输出:**
![](img/c9c96bf4d0cc14c1568d58f9f4245c91.png)

**示例 2:** 此示例说明了如何使用 CSS 在弹性框中设置左对齐垂直文本。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        Vertically align text content
    </title>

    <!-- CSS property to vertical align text
        content using flex-box -->
    <style>
        .GFG {
            display: flex;
            align-items: left;
            justify-content: left;
            flex-direction: column;
            text-align: left;
            margin: 13% 0;
            min-height: 300px;
            background-color:green;
            align-items: left;
        }
    </style>
</head>

<body>
    <div class="GFG">
        <h1>GeeksforGeeks</h1>

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-6.png" 
        style="display: inline;">
    </div>
</body>

</html>                    
```

**输出:**
![](img/b81d55c7c26d8db0386c8075ed34b221.png)