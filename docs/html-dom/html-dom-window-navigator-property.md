# HTML DOM 窗口导航器属性

> 原文:[https://www . geesforgeks . org/html-DOM-window-navigator-property/](https://www.geeksforgeeks.org/html-dom-window-navigator-property/)

HTML DOM **窗口导航器**属性用于返回一个 navigator 对象。这个导航对象包含运行脚本的应用程序的方法和属性。

**语法:**

```html
var nav = window.navigator;
```

**返回值:**导航器对象。

**示例:**这个示例展示了如何使用这个属性获取文档的 Navigator 对象。

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<body style="text-align:center;">
    <h1 style="color:green;">
        GeeksforGeeks
    </h1>

    <p>
        HTML | window navigator property
    </p>

    <button onclick="Geeks()">
        Click Here
    </button>

    <script>
        function Geeks() {
            console.log(window.navigator);
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**

    ![](img/f955e8969257231afa7a075da9d8c9fb.png)

*   **点击按钮后:**在控制台中，可以看到导航器对象。

    ![](img/6716543b2c0aeb59ad722500709314d3.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧