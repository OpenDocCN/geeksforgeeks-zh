# HTML |画布图像数据高度属性

> 原文:[https://www . geesforgeks . org/html-canvas-imagedata-height-property/](https://www.geeksforgeeks.org/html-canvas-imagedata-height-property/)

**图像数据高度**属性用于返回图像数据对象的高度，以像素为单位。

**语法:**

```html
imgData.height;

```

**示例:**

```html
<!DOCTYPE html>
<html>

<body>
    <h3 style="color:green">GeeksforGeeks</h3>
    <h3>HTML canvas ImageData height property</h3>
    <canvas id="myCanvas" 
            width="200" 
            height="200"
            style="border:2px solid ;">
  </canvas>
    <p id=g eeks></p>
    <script>
        var can = document.getElementById("myCanvas");
        var gfg = can.getContext("2d");
        var imgData = gfg.createImageData(150, 100);

        var i;
        for (i = 0; i < imgData.data.length; i += 3) {
            imgData.data[i + 0] = 100;
            imgData.data[i + 1] = 0;
            imgData.data[i + 2] = 0;
        }

        gfg.putImageData(imgData, 10, 10);

        document.getElementById("geeks").innerHTML =
            "Height of imgData is: " + imgData.height
    </script>

</body>

</html>
```

**输出:**
![](img/beb64d116c45d5d8fd4f35af95305c20.png)

**支持的浏览器:**

*   铬
*   Internet Explorer 9.0
*   旅行队
*   火狐浏览器
*   歌剧