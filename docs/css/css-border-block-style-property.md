# CSS |边框块样式属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-style-property/](https://www.geeksforgeeks.org/css-border-block-style-property/)

CSS 中的**边框块样式属性**用于在样式表中的单个位置设置单个逻辑块边框样式属性值。它设置定义边框元素的顶部和底部的边框样式。

**语法:**

```html
border-block-style: style;
```

**属性值:**

*   **样式:**该属性保存边框虚线、边框、虚线等样式。

以下示例说明了 CSS 中的**边框块样式属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-style Property</title>
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
            border: 5px solid cyan;
            border-block-style: dashed;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/e114e71cb19d73968d8b07e5763b6f97.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-style Property</title>
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
            border: 5px dotted cyan;
            border-block-style: solid;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-style Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/7f556bd16fc0b59bf13a17c2c9c2f47b.png)

**支持的浏览器:****边框块样式属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘