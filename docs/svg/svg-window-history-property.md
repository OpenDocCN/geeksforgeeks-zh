# SVG 窗口历史属性

> 原文:[https://www.geeksforgeeks.org/svg-window-history-property/](https://www.geeksforgeeks.org/svg-window-history-property/)

历史属性返回对历史对象的引用。

**语法:**

```html
var e = window.history
```

**返回值:**该属性返回对历史对象的引用。

**示例 1:** 在本例中，我们将使用 onclick 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <button onclick="get()">
            Get History
        </button>

        <br><br>
        <div id="g"></div>

        <svg viewBox="0 0 1000 1000" 
            xmlns="http://www.w3.org/2000/svg">

            <script type="text/javascript">
                function get() {
                    console.log(window.history);
                }
            </script>
        </svg>
    </center>
</body>

</html>
```

**输出:**

![](img/cc95fc6587a5366081e403b23706112e.png)

**示例 2:** 在本例中，我们将使用 onmouseover 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <button onmouseover="get()">
            Get History
        </button>

        <br><br>
        <div id="g"></div>

        <svg viewBox="0 0 1000 1000" 
            xmlns="http://www.w3.org/2000/svg">

            <script type="text/javascript">
                function get() {
                    console.log(window.history);
                }
            </script>
        </svg>
    </center>
</body>

</html>
```

**输出:**

![](img/9cd39276a25a6102450fcb5a37a86af8.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器