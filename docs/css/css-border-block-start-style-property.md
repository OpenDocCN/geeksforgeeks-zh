# CSS |边框-块-开始-样式属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-start-style-property/](https://www.geeksforgeeks.org/css-border-block-start-style-property/)

CSS 中的**边框块开始样式属性**用于在样式表中的一个位置定义单个逻辑块开始边框属性值。此属性设置定义元素边框顶部的边框样式。

**语法:**

```html
border-block-start-style: border-style;
```

**属性值:**

*   **边框样式:**该属性保存边框的样式。

以下示例说明了 CSS 中的**边框块开始样式属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-start-style Property</title>
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
            border-block-start-style: dotted;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-start-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/d4d57eeff9672ddcac6deb9f768c88dc.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-start-style Property</title>
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
            border-block-start-style: dashed;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-start-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/2198b68860285c5eae89e1758c37abd9.png)

**支持的浏览器:****边框块开始样式属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘