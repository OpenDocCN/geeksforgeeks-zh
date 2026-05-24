# 如何使用 HTML & CSS 在网页中创建多色文本？

> 原文:[https://www . geesforgeks . org/如何使用 html-css 创建网页中的多色文本/](https://www.geeksforgeeks.org/how-to-create-multicolored-text-in-a-web-page-using-html-css/)

在本文中，我们将学习使用 HTML & CSS 为网页中的文本着色。基本上，我们可以在 HTML 中使用[**<字体>颜色属性**](https://www.geeksforgeeks.org/html-font-color-attribute/) 或者 [**线性渐变**](https://www.geeksforgeeks.org/how-to-create-linear-gradient-text-using-html-and-css/) 来使用 CSS 对文本进行多色。我们将探索这两种方法&并通过例子了解它们的用法。

**方法:**

*   **[<字体>颜色属性:](https://www.geeksforgeeks.org/html-font-color-attribute/)** 用于指定<字体>元素内部的文字颜色。它可以用于您想要应用颜色的每个字符或整个单词。
*   **[【线性渐变】()功能](https://www.geeksforgeeks.org/css-linear-gradient-function/) :** 用于文本填充线性渐变颜色代码的文本样式。

**方法一:**使用<字体>颜色属性。

**语法:**

```html
<font color="color_name|hex_number|rgb_number">Text content</font>
```

**属性值:**

*   **十六进制数:**使用颜色十六进制码设置文本颜色。例如**“# 0000 ff”**。
*   **rgb_number:** 用 rgb 码设置文字颜色。例如:**“RGB(0，153，0)”**。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Page Title</title>
    <style>
        h1 {
            color: green;
            font-size: 60px;
        }
    </style>
</head>

<body>
    <center>
        <h1>
            Welcome To
            <font color="#FF2626">G</font>
            <font color="#252A34">e</font>
            <font color="#753422">e</font>
            <font color="#FFD523">k</font>
            <font color="#71EFA3">s</font>
            <font color="#0F52BA">for</font>
            <font color="#66CC66">G</font>
            <font color="#FF9966">e</font>
            <font color="#FFCCCC">e</font>
            <font color="#00C1D4">k</font>
            <font color="#EFE3D0">s</font>
        </h1>
    </center>
</body>

</html>
```

**输出:**

![](img/390ba3904d373463573daef7015f2030.png)

**方法二:**使用线性梯度属性。

**语法:**

```html
background: linear-gradient(to left, color names);
-webkit-background-clip: text;
color: transparent;
```

将多色添加到文本中的步骤:

*   用所需的选择器在标签内添加一个简单的文本。
*   将线性渐变属性应用于您选择的任何颜色。
*   应用 **webkit 属性**，用渐变背景填充文本，用透明背景声明颜色属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8" />
    <style>
        .multicolor-text {
            text-align: center;
            font-size: 50px;
            background: linear-gradient(to left,
                    violet,
                    indigo,
                    blue,
                    green,
                    yellow,
                    orange,
                    red);
            -webkit-background-clip: text;
            color: transparent;
        }
    </style>
</head>

<body>
    <div class="multicolor-text">
        Welcome To GeeksforGeeks!
    </div>
</body>

</html>
```

**输出:**

![](img/b51300022a4b9ec00737e5dffe672983.png)