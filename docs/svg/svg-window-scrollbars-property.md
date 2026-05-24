# SVG 窗口.滚动条属性

> 原文:[https://www . geesforgeks . org/SVG-window-scroll bar-property/](https://www.geeksforgeeks.org/svg-window-scrollbars-property/)

SVG`<em>`window . scroll bar 属性返回scroll bar 对象，通过它我们可以检查可见性。

**语法:**

```html
var sb = window.scrollbars

```

**返回值:**该属性返回滚动条对象。

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
                    console.log(window.scrollbars);
                }
            </script>
        </svg>
    </center>
</body>

</html>
```

**输出:**

![](img/8f206ff733c922eff2ea7e54aea558d2.png)

**例 2:**

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

        <div id="g"></div>

        <svg viewBox="0 0 1000 1000" 
            xmlns="http://www.w3.org/2000/svg">

            <script type="text/javascript">
                function get() {
                    var g = document.getElementById("g");
                    g.innerHTML = "Is it visible? : "
                        + window.scrollbars.visible;
                }
            </script>
        </svg>
    </center>
</body>

</html>
```

**输出:**

![](img/b334c668db92109e2c9a11e4f4a695e1.png)

**支持的浏览器:**

*   谷歌 Chrome
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧
*   微软公司出品的 web 浏览器