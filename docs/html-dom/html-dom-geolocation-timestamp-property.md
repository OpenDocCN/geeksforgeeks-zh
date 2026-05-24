# HTML DOM 地理位置时间戳属性

> 原文:[https://www . geesforgeks . org/html-DOM-geolocation-timestamp-property/](https://www.geeksforgeeks.org/html-dom-geolocation-timestamp-property/)

在本文中，我们将讨论[地理位置](https://www.geeksforgeeks.org/html-geolocation/) *时间戳*属性。HTML 中的地理定位用来获取用户的地理位置。在这个地理定位中， **getCurrentPosition()** 方法在成功时返回一个对象。

**语法**:

```html
timestamp
```

**返回值** :-该地理定位属性在成功时返回一个对象。

**示例:**下面的 HTML 代码返回时间戳。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <h2 style="color:green">
        GeeksforGeeks
    </h2>

<p>
        <b>Displaying Timestamp</b>
    </p>

    <button onclick="getlocation()">
        Click Me
    </button>

    <p id="paraID"></p>

    <script>
        var variable1 = document.getElementById("paraID");

        function getlocation() {
            navigator.geolocation
            .getCurrentPosition(showLoc);
        }

        function showLoc(pos) {
            variable1.innerHTML
                = "Timestamp: " + pos.timestamp;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/f44a78d16348a5af4753c7d2e4b4deb1.png)