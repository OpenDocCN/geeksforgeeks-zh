# CSS |边框-块-结束-颜色属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-end-color-property/](https://www.geeksforgeeks.org/css-border-block-end-color-property/)

CSS 中的**边框-块-结束-颜色属性**用于在样式表的一个地方定义单个逻辑块-结束边框属性值。此属性设置定义元素边框底部的边框颜色。

**语法:**

```html
border-block-end-color: border-color;
```

**属性值:**

*   **边框颜色:**该属性保存边框的颜色。

以下示例说明了 CSS 中的**边框块结束颜色属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS | border-block-end-color Property
    </title>
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
            border-block-end-color: yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/dc42995e2da8e437d596a2223e74eb26.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-end-color Property</title>
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
            border-block-end-color: green;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end-color Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/786329db058d3e7f015e28f8afb4e2f1.png)

**支持的浏览器:****边框块端色属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘