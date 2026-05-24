# HTML | DOM MouseEvent 页面属性

> 原文:[https://www . geesforgeks . org/html-DOM-mouse event-pagey-property/](https://www.geeksforgeeks.org/html-dom-mouseevent-pagey-property/)

**鼠标事件页面**属性是只读属性，用于在事件触发时**返回鼠标指针的垂直坐标**。

**语法:**

```html
event.pageY
```

**返回值:**返回一个数字，以像素为单位表示鼠标指针的垂直坐标。

下面的程序说明了 MouseEvent pageY 属性:

**示例:**当鼠标按钮点击一个元素时，找出鼠标指针的垂直坐标。

```html
<!DOCTYPE html>
<html>

<head>
    <title>MouseEvent pageY Property in HTML</title>
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
    <h2>MouseEvent pageY Property Property</h2>

    <p onclick="coord(event)">
      Click somewhere in the paragraph to get 
      the y(vertical) coordinates of the mouse 
      pointer when it was clicked.
  </p>

    <p id="test"></p>

    <script>
        function coord(event) {

            var y = event.pageY;
            var coords = "Y coordinates: " + y;
            document.getElementById(
              "test").innerHTML = coords;
        }
    </script>

</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/25295a82863f85bf1fdeee9b8869b06a.png)
*   **点击按钮后:**
    ![](img/6e42fc86f8b82343af3c99660588b40b.png)

**支持的浏览器:**

*   歌剧
*   微软公司出品的 web 浏览器
*   谷歌 Chrome
*   火狐浏览器
*   苹果 Safari