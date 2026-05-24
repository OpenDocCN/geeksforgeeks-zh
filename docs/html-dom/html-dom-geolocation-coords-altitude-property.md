# HTML DOM 地理位置坐标海拔属性

> 原文:[https://www . geesforgeks . org/html-DOM-geolocation-coords-height-property/](https://www.geeksforgeeks.org/html-dom-geolocation-coords-altitude-property/)

在本文中，我们将讨论地理位置*高度*属性。HTML 中的地理定位用来获取用户的地理位置。在这个地理定位中， **getCurrentPosition()** 方法在成功时返回一个对象。

**坐标高度:**该属性将返回海拔高度，单位为米。

**语法:**

```html
coords.altitude
```

**示例:**下面的 HTML 代码将返回高度。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" 
          content="width=device-width,initial-scale=1">
</head>

<body>
    <h2 style="color:green">GeeksforGeeks</h2>
    <p><b> Displaying Altitude</b></p>

    <button onclick="getlocation()"> Click Me </button>
    <p id="paraID"></p>

    <script>
       var variable1 = document.getElementById("paraID");

        function getlocation() {
            navigator.geolocation.getCurrentPosition(showLoc);
        }

        function showLoc(pos) {
            variable1.innerHTML = "Altitude: " 
              + pos.coords.altitude;
        }
    </script>
</body>
</html>
```

**输出:**

![](img/ac07f107d7febaa2ca64ea6f38fbcc90.png)

**支持的浏览器:**

*   谷歌 Chrome 5.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Opera 16.0
*   Safari 5.0