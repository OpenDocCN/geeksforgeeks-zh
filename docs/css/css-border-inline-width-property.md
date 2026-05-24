# CSS |边框内联宽度属性

> 原文:[https://www . geesforgeks . org/CSS-border-inline-width-property/](https://www.geeksforgeeks.org/css-border-inline-width-property/)

CSS 中的**边框内联宽度属性**用于在样式表中的一个位置设置单个逻辑内联边框宽度属性值。它设置定义边框元素的顶部和底部的边框宽度。

**语法:**

```html
border-inline-width: width;
```

**属性值:**

*   **宽度:**该属性保存边框的宽度。

以下示例说明了 CSS 中的**边框内联宽度属性**:

**例 1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-width Property</title>
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
            border-inline-width: 2px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/9d16b544b35331e96b9f11f0fcf22811.png)

**例 2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>CSS | border-inline-width Property</title>
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
            border-inline-width: 2px;
            background-color: purple;
        }
    </style>
</head>

<body>
    <center>
        <h1>Geeksforgeeks</h1>
        <b>CSS | border-inline-width Property</b>
        <br><br>
        <div class="one">A Computer Science Portal</div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/c5cab5790f7d3556574fa7fd20bd97b0.png)

**支持的浏览器:****边框内联宽度属性**支持的浏览器如下:

*   火狐浏览器
*   歌剧
*   边缘

**参考:**[https://developer . Mozilla . org/en-US/docs/Web/CSS/border-inline-width](https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-width)