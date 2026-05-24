# HTML 中一个 id 和类的区别？

> 原文:[https://www . geeksforgeeks . org/an-id-和-class-in-html 的区别/](https://www.geeksforgeeks.org/difference-between-an-id-and-class-in-html/)

**HTML id 属性:**id 属性是用于指定文档的唯一标识符。它被 CSS 和 JavaScript 用来为一个独特的元素执行特定的任务。在 CSS 中，id 属性是使用#符号后跟 id 编写的。
**语法:**

```html
<element id="id_name">

In CSS Stylesheet:
#id_name {
    // CSS Property
}
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML id attribute
    </title>

    <style>
        #geeks{
            color:green;
            font-size:25px;
        }
    </style>
</head>

<body style="text-align:center">
    <h1>Geeks for Geeks</h1>
    <p id="geeks">Welcome to Geeks for Geeks</p>

<p>A Computer Science portal for geeks</p>

</body>

</html>                    
```

**输出:**

![](img/fd54d672b876aad93824d9c071c89bd3.png)

**HTML 类属性:**类属性用于为一个 HTML 元素指定一个或多个类名。类属性可以用于任何 HTML 元素。CSS 和 JavaScript 可以使用类名为具有指定类名的元素执行某些任务。CSS 样式表中的类名使用**。”**符号。
**语法:**

```html
<element class="class_name">

In CSS Stylesheet:
.class {
    // CSS Property
}
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        .geeks{
            color:green;
            font-size:25px;
        }
    </style>
</head>

<body style="text-align:center;">
    <h1>Geeks for Geeks</h1>

<p> Welcome to Geeks for Geeks</p>

    <p class="geeks">
        A Computer Science portal for geeks
    </p>

</body>

</html>                    
```

**输出:**

![](img/efa85cbe73aad358da377887fd82662a.png)

**id 和类属性的区别:**它们唯一的区别是“id”在一个页面中是唯一的，最多只能应用于一个元素，而“类”选择器可以应用于多个元素。

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。