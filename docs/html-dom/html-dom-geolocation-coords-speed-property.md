# HTML DOM 地理位置坐标速度属性

> 原文:[https://www . geesforgeks . org/html-DOM-geolocation-coords-speed-property/](https://www.geeksforgeeks.org/html-dom-geolocation-coords-speed-property/)

在本文中，我们将讨论地理定位速度属性。HTML 中的地理定位用来获取用户的地理位置。

**坐标速度**属性用于返回该位置的速度，单位为米/秒(mps)。

**语法:**

```html
coords.speed
```

**示例:**下面的 HTML 代码将返回速度。

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
    <p><b> Displaying Speed in MPS</b></p>

    <button onclick="getlocation()"> Click Me </button>
    <p id="paraID"></p>

    <script>
      var variable1 = document.getElementById("paraID");

      function getlocation() {
          navigator.geolocation.getCurrentPosition(showLoc);
      }

      function showLoc(pos) {
          variable1.innerHTML = "Speed: " 
            + pos.coords.speed;
      }
    </script>
</body>

</html>
```

**输出:**

![](img/45c660aeb0340a0c5d2c85af4ac6c1a5.png)