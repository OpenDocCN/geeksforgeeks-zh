# CSS |边框-内联-开始样式属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-start-style-property/](https://www.geeksforgeeks.org/css-border-inline-start-style-property/)

**边框内联开始样式**属性是 CSS 中的一个内置属性，它用于在样式表的单个位置定义单个逻辑内联结束边框属性值。此属性设置定义元素边框左侧的边框样式。

**语法:**

```html
border-inline-start-style: border-style;
```

**属性值:**

*   **边框样式:**该属性保存边框的样式。

以下示例说明了 CSS 中的**边框内联开始样式属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start-style Property</title>
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
            border-inline-start-style: dotted;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/9c056c9c272215a5dc8859ff84171c81.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-start-style Property</title>
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
            border-inline-start-style: dashed;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-start-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/fcf21a7fa4ab6dfb0950701f24236a7b.png)

**支持的浏览器:****边框内联开始样式属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-start-style](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-style)