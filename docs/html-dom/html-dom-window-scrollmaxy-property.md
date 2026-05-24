# HTML DOM 窗口滚动最大属性

> 原文:[https://www . geesforgeks . org/html-DOM-window-scroll maxy-property/](https://www.geeksforgeeks.org/html-dom-window-scrollmaxy-property/)

**窗口滚动最大值** 属性返回文档在当前窗口中可以垂直滚动的最大像素数。它是只读属性。

**语法:**

```html
var scrMaxY = window.scrollMaxY

```

**返回值:**该属性返回文档可以垂直滚动的最大像素数。

**示例:**该示例显示了如何使用该属性获取文档的最大像素数。

在这里，我们附加了一个长的垂直标题来超过框架，以允许垂直滚动。

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<body style="text-align:center;">
    <h1 style="color:green;">
        G<br>
        e<br>
        e<br>
        k<br>
        s<br>
        f<br>
        o<br>
        r<br>
        G<br>
        e<br>
        e<br>
        k<br>
        s<br>
    </h1>

    <p>
        HTML | window scrollMaxY property
    </p>

    <button onclick="Geeks()">
        Click Here
    </button>
    <p id="a"></p>

    <script>
        var a = document.getElementById("a");
        function Geeks() {
            a.innerHTML = "scrollMaxY is : " 
                    + window.scrollMaxY;
        }
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**

    ![](img/d01ec37da3ccfca30891008e25f51921.png)

*   **点击按钮后:**

    ![](img/df3d072126aca875417e11d76483d260.png)

**支持的浏览器:**

*   火狐浏览器
*   歌剧
*   微软公司出品的 web 浏览器