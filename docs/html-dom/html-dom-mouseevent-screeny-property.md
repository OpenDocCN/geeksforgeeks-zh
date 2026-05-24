# HTML | DOM 鼠标事件屏幕属性

> 原文:[https://www . geesforgeks . org/html-DOM-mouse event-screeny-property/](https://www.geeksforgeeks.org/html-dom-mouseevent-screeny-property/)

**鼠标事件屏幕**属性是只读属性，用于在事件被触发时*返回鼠标指针的垂直坐标*。

**语法:**

```html
event.screenY
```

**返回值:**返回一个数字，以像素为单位表示鼠标指针的垂直坐标。

下面的程序说明了 MouseEvent screenY 属性:
**示例:**当鼠标按钮被点击在一个元素上时，找出鼠标指针相对于屏幕的水平坐标。

```html
<!DOCTYPE html>
<html>

<head>
    <title>MouseEvent screenY Property in HTML</title>
    <style>
        h1 {
            color: green;
        }

        h2 {
            font-family: Impact;
        }

        body {
            text-align: center;
        }
    </style>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h2>MouseEvent screenY Property</h2>

    <p onclick="coord(event)">
      Click somewhere in the paragraph to get
      the y(vertical) coordinates of the mouse pointer.
  </p>

    <p id="test"></p>

    <script>
        function coord(event) {

            var y = event.screenY;
            var coords = " Y coords: " + y;
            document.getElementById(
              "test").innerHTML = coords;
        }
    </script>

</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/2e322b4e2dded4570683c89782a977d6.png)
*   **点击按钮后:**
    ![](img/4ecc4a27b9d85628923ac22b0a9c86e7.png)

**支持的浏览器:**

*   歌剧
*   微软公司出品的 web 浏览器
*   谷歌 Chrome
*   火狐浏览器
*   苹果 Safari