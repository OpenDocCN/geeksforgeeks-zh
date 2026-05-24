# HTML |画布阴影偏移属性

> 原文:[https://www . geeksforgeeks . org/html-canvas-shadowoffset-property/](https://www.geeksforgeeks.org/html-canvas-shadowoffsety-property/)

**画布阴影偏移属性**用于**设置**或**返回** *阴影与形状*的垂直距离。
此属性保存正值或负值，其中正值表示底部阴影，负值表示顶部阴影。

**语法:**

```html
context.shadowOffsetY = number
```

**属性值:**

*   **数字:**用于设置代表阴影垂直距离的正数或负数。

**示例-1:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML canvas shadowOffsetY Property
    </title>
</head>

<body>
    <canvas id="GFG"
            width="500" 
            height="300">
  </canvas>

    <script>
        var x =
            document.getElementById("GFG");
        var contex =
            x.getContext("2d");
        contex.shadowBlur = 20;

        // vertical distance of shadow
        contex.shadowOffsetY = 40;
        contex.shadowColor = "blue";
        contex.fillStyle = "green";
        contex.fillRect(50, 50, 350, 200);
        contex.stroke();
    </script>

</body>

</html>
```

**输出:**
![](img/32a0e5612fdd0af98a27f8dfbdf6b59f.png)

**示例-2:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML canvas shadowOffsetY Property
    </title>
</head>

<body>
    <canvas id="GFG" 
            width="500"
            height="300">
  </canvas>

    <script>
        var x =
            document.getElementById("GFG");
        var contex =
            x.getContext("2d");
        contex.shadowBlur = 5;

        // vertical distance of shadow.
        contex.shadowOffsetY = -40;
        contex.shadowColor = "rgb(0, 153, 0)";
        contex.fillStyle = "rgb(255, 0, 255)";
        contex.fillRect(50, 50, 350, 200);
        contex.stroke();
    </script>

</body>

</html>
```

**输出:**
![](img/57db637b381aed1407ada6ef868caa6a.png)

**支持的浏览器:**

*   谷歌 Chrome
*   Internet Explorer 9.0
*   火狐浏览器
*   旅行队
*   歌剧