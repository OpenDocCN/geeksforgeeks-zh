# HTML |画布 clearRect()方法

> 原文:[https://www.geeksforgeeks.org/html-canvas-clearrect-method/](https://www.geeksforgeeks.org/html-canvas-clearrect-method/)

**清除矩形()方法**用于*清除给定矩形*内的指定像素。

**语法:**

```html
context.clearRect( x, y, width, height )
```

**参数:**

*   **x:** 存储矩形左上角的 x 坐标。
*   **y:** 存储矩形左上角的 y 坐标。
*   **宽度:**以像素为单位存储宽度。
*   **高度:**以像素为单位存储高度。

**示例-1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML canvas clearRect() Method
    </title>
</head>

<body>
    <canvas id="GFG"
            width="500"
            height="300">
  </canvas>

    <script>
        var x = document.getElementById("GFG");
        var contex = x.getContext("2d");
        contex.fillRect(50, 50, 350, 200);
        contex.clearRect(100, 100, 250, 100);
        contex.stroke();
    </script>
</body>

</html>
```

**输出:**
![](img/204f460e87dda5193ea7c35e4ae14c12.png)

**示例-2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML canvas clearRect() Method
    </title>
</head>

<body>
    <canvas id="GFG"
            width="500"
            height="300">
  </canvas>

    <script>
        var x = document.getElementById("GFG");
        var contex = x.getContext("2d");
        contex.fillStyle = "green";
        contex.fillRect(50, 50, 350, 200);
        contex.clearRect(130, 60, 250, 100);
        contex.stroke();
    </script>

</body>

</html>
```

**输出:**
![](img/3fd08b7cc1c5f36a4944da9762dbd373.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Internet Explorer 9.0
*   火狐浏览器
*   旅行队
*   歌剧