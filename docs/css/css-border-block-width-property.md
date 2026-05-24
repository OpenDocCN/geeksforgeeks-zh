# CSS |边框块宽度属性

> 原文:[https://www . geesforgeks . org/CSS-border-block-width-property/](https://www.geeksforgeeks.org/css-border-block-width-property/)

CSS 中的**边框块宽度属性**用于在样式表中的一个地方设置单个逻辑块边框宽度属性值。它设置定义边框元素的顶部和底部的边框宽度。

**语法:**

```html
border-block-width: width;
```

**属性值:**

*   **宽度:**该属性保存边框的宽度。

以下示例说明了 CSS 中的**边框块宽度属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-width Property</title>
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
            border: 5px dashed cyan;
            border-block-width: 2px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/1271ca47eaa9e6391b10472aa65ebdcc.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-block-width Property</title>
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
            border-block-width: 2px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-block-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/41c399b8203cb51a97e6d648064bd85f.png)

**支持的浏览器:****边框块宽属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘