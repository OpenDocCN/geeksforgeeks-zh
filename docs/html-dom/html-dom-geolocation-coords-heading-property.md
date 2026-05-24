# HTML DOM 地理位置坐标标题属性

> 原文:[https://www . geesforgeks . org/html-DOM-geolocation-coords-heading-property/](https://www.geeksforgeeks.org/html-dom-geolocation-coords-heading-property/)

在本文中，我们将讨论**地理位置** **坐标标题**属性。HTML 中的地理定位用来获取用户的地理位置。这个地理定位中的 *getCurrentPosition()方法*在成功时返回一个对象。

**地理位置坐标标题** **属性**用于从北方以度为单位返回时钟方向。如果不适用，它将返回 null。

**语法**:

```html
coords.heading
```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<body>
    <h2 style="color:green">
      GeeksforGeeks
      </h2>
    <p><b> Displaying heading</b></p>

    <button onclick="getlocation()"> 
      Click Me 
      </button>
    <p id="paraID"></p>

    <script>
        var variable1 = document.getElementById("paraID");

        function getlocation() {
            navigator
              .geolocation
              .getCurrentPosition(showLoc, error, options);
        }

        function showLoc(pos) {
            variable1.innerHTML = "Heading: " 
              + pos.coords.heading;
        }

        function error(err) {
              console.warn(
              `ERROR(${err.code}): ${err.message}`
            );
        }
        var options = {
            enableHighAccuracy: true,
            timeout: 5000,
            maximumAge: 0
        };
    </script>
</body>
</html>
```

**输出:**

![](img/17f339a74c6601489f8b557a9539c532.png)

**支持的浏览器:**

*   谷歌 Chrome 5.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Opera 16.0
*   Safari 5.0