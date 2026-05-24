# CSS |边框-块-开始-颜色属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-start-color-property/](https://www.geeksforgeeks.org/css-border-block-start-color-property/)

CSS 中的**边框块开始颜色属性**用于在样式表的一个地方定义单个逻辑块开始边框属性值。此属性设置定义元素边框顶部的边框颜色。

**语法:**

```html
border-block-start-color: border-color;
```

**属性值:**

*   **边框颜色:**该属性保存边框的颜色。

下面的例子说明了 CSS 中的**边框块开始颜色属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-start-color Property</title>
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
            border-block-start-color: yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-start-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/b38b66dae6ed043b6d0dd34049dd2935.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-start-color Property</title>
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
            border-block-start-color: green;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-start-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/cc08e5c4f8ec939546484a0a3c3f7231.png)

**支持的浏览器:****边框块起始颜色属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘