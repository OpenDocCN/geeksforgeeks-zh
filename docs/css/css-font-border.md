# CSS |字体边框

> 原文:[https://www.geeksforgeeks.org/css-font-border/](https://www.geeksforgeeks.org/css-font-border/)

有时我们需要创建文本，并在文本中添加轮廓。主要有两种方法可以为下面列出的字体创建边框:

*   使用[文本阴影属性](https://www.geeksforgeeks.org/css-text-shadow-property/)
*   使用文本笔画属性

**方法一:使用文字-阴影属性:**文字-阴影属性用于给文字添加字体边框或阴影。
**语法:**

```html
text-shadow: h-shadow v-shadow blur-radius color|none|initial|inherit;
```

**属性值:**

*   **h-shadow:** 设置字体周围的水平阴影。
*   **v 形阴影:**设置字体周围的垂直阴影。
*   **模糊半径:**设置字体周围的模糊半径。
*   **颜色:**设置字体周围的颜色。
*   **无:**不设置字体周围的任何内容。
*   **初始值:**设置字体边框为默认值。
*   **继承:**它从其父值继承属性值。

**返回值:**返回文本周围的字体边框/阴影。
**示例 1:** 本示例使用文本-阴影属性为文本创建阴影。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-shadow property
    </title>

    <style>
        h1 {
            text-shadow: 0 0 3px #FF0000, 0 0 5px #0000FF;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
</body>

</html>                    
```

**输出:**

![](img/21a8ff9bffde51aedfe1c85be3fe8dc3.png)

**示例 2:** 本示例使用文本阴影属性创建带边框的文本。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-shadow property
    </title>

    <!-- Style to use text-shadow property -->
    <style>
        .GFG {
            color: white;
            font-size: 50px;
            text-shadow: -1px 1px 0 #000,
                          1px 1px 0 #000,
                         1px -1px 0 #000,
                        -1px -1px 0 #000;
        }
    </style>
</head>

<body>
    <p class="GFG">GeeksforGeeks</p>

</body>

</html>                    
```

**输出:**

![](img/67c396eb783b85001dcc04f190ee04f8.png)

**方法二:使用文字笔画属性:**文字笔画属性用于给文字添加笔画。此属性可用于更改文本的宽度和颜色。使用-webkit-前缀支持此属性。
**示例:**本示例使用文本笔画属性创建带边框的文本。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS text-stroke property
    </title>

    <!-- Style to use text-stroke property -->
    <style>
        .GFG {
            color: white;
            font-size: 50px;
            -webkit-text-stroke-width: 1px;
            -webkit-text-stroke-color: black;
        }
    </style>
</head>

<body>
    <p class="GFG">GeeksforGeeks</p>

</body>

</html>                    
```

**输出:**

![](img/94884ccdc3dbc76796956db28bb52bd8.png)

**支持的浏览器:**

*   谷歌 Chrome 4.0
*   Internet Explorer 10.0
*   Firefox 3.5
*   歌剧 9.6
*   Safari 4.0

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。