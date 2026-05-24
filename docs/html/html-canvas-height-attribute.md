# HTML | canvas 身高属性

> 原文:[https://www.geeksforgeeks.org/html-canvas-height-attribute/](https://www.geeksforgeeks.org/html-canvas-height-attribute/)

**HTML <画布>高度属性**用于*以像素*为单位指定<画布>元素的高度。

**语法:**

```html
<canvas height="pixels">
```

**属性值:**包含单值**像素**，以像素为单位指定画布的高度。它的默认值为 150。

**示例:**此示例说明了 Canvas Element 中高度属性的使用。

```html
<!-- HTML code to illustrate 
height attribute of canvas tag -->
<!DOCTYPE html>
<html>

<head>
    <title>HTML canvas height attribute</title>
</head>

<body style="text-align:center;">
    <h1>GeeksForGeeks</h1>
    <h2>HTML Canvas Height Attribute</h2>
    <canvas id="geeks"
            height="200"
            width="200" 
            style="border:1px solid black">
    </canvas>

    <script>
        var c = document.getElementById("geeks");
        var cx = c.getContext("2d");
        cx.beginPath();
        cx.arc(100, 100, 90, 0, 2 * Math.PI);
        cx.stroke();
    </script>
</body>

</html>
```

**输出:**
![](img/d1c6e30e95ca913ec2b995cfb17dc0ea.png)

**支持的浏览器:**以下是 *HTML <画布>高度属性*支持的浏览器:

*   谷歌 Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 2.0
*   Safari 3.1
*   Opera 9.0