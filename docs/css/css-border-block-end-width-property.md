# CSS |边框块端宽属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-end-width-property/](https://www.geeksforgeeks.org/css-border-block-end-width-property/)

CSS 中的**边框-块-结束-宽度属性**用于在样式表的一个地方定义单个逻辑块-结束边框属性值。此属性设置定义元素边框底部的边框宽度。

**语法:**

```html
border-block-end-width: border-width;
```

**属性值:**

*   **边框宽度:**该属性保存边框的宽度。

以下示例说明了 CSS 中的**边框-块-结束-宽度属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-end-width Property</title>
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
            border-block-end-width: 8px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/d1474824d385dcda1a556aff8783475d.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-end-width Property</title>
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
            border-block-end-width: 2px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-end-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/3cf4debaa1ec6b8f851b6a9bc983e8d7.png)

**支持的浏览器:****边框块端宽属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘