# SVG 窗口.性能属性

> 原文:[https://www . geesforgeks . org/SVG-window-performance-property/](https://www.geeksforgeeks.org/svg-window-performance-property/)

性能属性用于收集当前文档的性能信息。

**语法:**

```html
var p = window.performance

```

**返回值:**该属性返回一个性能对象。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <button onclick="get()">
            Click Here
        </button>

        <svg viewBox="0 0 10000 10000" 
            xmlns="http://www.w3.org/2000/svg">

            <script type="text/javascript">
                function get() {
                    var g = document.getElementById("g");
                    console.log(window.performance);
                }
            </script>
        </svg>
    </center>
</body>

</html>
```

**输出:**

![](img/a104dd78bb13763933925afbb9783e1b.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器