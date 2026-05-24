# CSS |边框块属性

> 原文:[https://www.geeksforgeeks.org/css-border-block-property/](https://www.geeksforgeeks.org/css-border-block-property/)

CSS 中的**边框块属性**用于在样式表的单个位置设置单个逻辑块边框属性值。它设置定义元素的顶部和底部边框。

**语法:**

```html
border-block: border-width|border-style|border-color;
```

**属性值:**

*   **边框宽度:**该属性值保存属性的宽度。
*   **边框样式:**该属性保存可以是虚线、实线等的边框样式。
*   **边框颜色:**该属性保存边框的颜色。

以下示例说明了 CSS 中的**边框块属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block Property</title>
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
            border-block: 5px solid yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/dd1393562cfd32c63a218f8d732cab7b.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block Property</title>
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
            border-block: 5px dashed yellow;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>
```

**输出:**
![](img/5a22dd66bd2fe35a51eaa620974a0a2b.png)

**支持的浏览器:****边框阻挡属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘