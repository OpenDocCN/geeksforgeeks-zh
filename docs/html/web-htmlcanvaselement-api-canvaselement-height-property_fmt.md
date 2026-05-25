
# Web HTML CanvasElement API | CanvasElement 高度属性

> 原文: [https://www.geeksforgeeks.org/web-html-canvaselement-api-canvaselement-height-property/](https://www.geeksforgeeks.org/web-htmlcanvaselement-api-canvaselement-height-property/)

在 HTML 中，**画布元素**具有一个高度属性，该属性以 CSS 像素为单位表示画布的高度。`HTMLCanvasElement.height` 属性允许我们从画布元素中获取这个高度属性，它是一个正整数。

**语法:**

```html
var heightVal = canvas.height;
canvas.height = heightVal;
```

**注意:** 如果没有提供高度属性值或者设置为未定义的值，比如负值，那么默认值设置为 150。

**示例 1:** 高度属性设置为 300

```html
<!DOCTYPE html>
<html>

<head>

<style>
    a:focus {
        background-color: magenta;
    }
</style>
<canvas id="canvas" width="300" height="300"></canvas>
<script type="text/javascript">
    function getHeight() {
        var canvas = document.getElementById('canvas');
        document.getElementById('height').innerHTML = canvas.height;
    }
</script>

</head>

<body>
    <center>

    <h1 style="color:green;">
            GeeksForGeeks
    </h1>

    <h2>HTML Canvas Element height property</h2>
    <button onclick="getHeight();">Get Height</button>
    <p id='height'></p>
    </center>
</body>

</html>
```

**输出:**
**点击按钮:**
![](img/568328cd47206632685898b7b8b916e2.png)

**点击按钮时:**
![](img/8da69cc166c679477f5339ec74ca4c32.png)

**示例 2:** 未提供高度属性

```html
<!DOCTYPE html>
<html>

<head>

<style>
    a:focus {
        background-color: magenta;
    }
</style>
<canvas id="canvas"></canvas>
<script type="text/javascript">
    function getHeight() {
        var canvas = document.getElementById('canvas');
        document.getElementById('height').innerHTML = canvas.height;
    }
</script>

</head>

<body>
    <center>

    <h1 style="color:green;">
            GeeksForGeeks
    </h1>

    <h2>HTML Canvas Element height property</h2>
    <button onclick="getHeight();">Get Height</button>
    <p id='height'></p>
    </center>
</body>

</html>
```

**输出:**
**点击按钮:**
![](img/568328cd47206632685898b7b8b916e2.png)

**点击按钮时:**
![](img/6762f626cd96bec9fc1c9a8ba554c99b.png)

**支持的浏览器:**

*   谷歌 Chrome 4
*   边缘 12
*   Firefox 3.6
*   Safari 3.1
*   歌剧 9
*   Internet Explorer 9
