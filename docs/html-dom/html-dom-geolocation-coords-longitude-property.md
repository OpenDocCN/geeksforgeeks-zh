# HTML DOM 地理位置坐标经度属性

> 原文:[https://www . geesforgeks . org/html-DOM-地理位置-坐标-经度-属性/](https://www.geeksforgeeks.org/html-dom-geolocation-coords-longitude-property/)

在本文中，我们将讨论[地理位置](https://www.geeksforgeeks.org/html-geolocation/) *经度*属性。

[HTML 中的地理定位](https://www.geeksforgeeks.org/html-geolocation/)用于获取用户的地理位置。这个地理定位中的 **getCurrentPosition()** 方法在成功时返回一个对象。

**坐标经度:**该属性将以十进制数的形式返回经度

**语法:**

```html
coords.longitude
```

**示例:**下面的 HTML 程序返回经度。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h2 style="color:green">
        GeeksforGeeks
    </h2>

    <p><b> Displaying location using longitude</b></p>

    <button onclick="getlocation()">
        Click Me
    </button>

    <p id="paraID"></p>

    <script>
        var variable1 = document.getElementById("paraID");

        function getlocation() {
            navigator.geolocation.getCurrentPosition(showLoc);
        }
        function showLoc(pos) {
            variable1.innerHTML =
                "Longitude: " + pos.coords.longitude;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/142e652b3ceb5903f368b7809e77a748.png)