# CSS |边框块端样式属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-end-style-property/](https://www.geeksforgeeks.org/css-border-block-end-style-property/)

CSS 中的**边框-块-结束-样式属性**用于在样式表中的一个位置定义单个逻辑块-结束边框属性值。此属性设置定义元素边框底部的边框样式。

**语法:**

```html
border-block-end-style: border-style;
```

**属性值:**

*   **边框样式:**该属性保存边框的样式。

以下示例说明了 CSS 中的**边框块结束样式属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-end-style Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 220px;
            height: 40px;
        }
        .one {
            border: 5px solid gray;
            border-block-end-style: dotted;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/d546142ab2ab4776b5cfdfd5fb6f1932.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-end-style Property</title>
    <style>
        h1 {
            color: green;
        }

        div {
            background-color: yellow;
            width: 220px;
            height: 40px;
        }
        .one {
            border: 5px solid black;
            border-block-end-style: dashed;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/1c022dcce12a0aadee9d3d444e49d130.png)

**支持的浏览器:****边框块端样式属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘