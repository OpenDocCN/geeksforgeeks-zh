# SVG 窗口关闭属性

> 原文:[https://www.geeksforgeeks.org/svg-window-closed-property/](https://www.geeksforgeeks.org/svg-window-closed-property/)

**SVG Window.closed 属性**表示被引用的窗口是否关闭。

**语法:**

```html
const isClosed = windowRef.closed
```

**返回值:**该属性返回事件元素的布尔值。

**示例 1:** 在本例中，我们将使用 onclick 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000" 
        xmlns="http://www.w3.org/2000/svg">

        <circle cx="50" cy="50" r="50" 
            onclick="check()" />

        <script type="text/javascript">
            function check() {
                document.write(
                    "This Window is closed : ", 
                    window.closed);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/202917bd5ca0fa9b1bfc0755af92ba02.png)

**示例 2:** 在本例中，我们将使用 onclick 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000"
        xmlns="http://www.w3.org/2000/svg">

        <text x="50" y="20" font-size="20px" 
            onclick="check()">
            GeeksForGeeks
        </text>

        <script type="text/javascript">
            function check() {
                document.write(
                    "This Window is closed : ", 
                    window.closed);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/0164dd0e18c456e8b3496810fd9523b4.png)

**示例 3:** 在本例中，我们将使用 onmouseover 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000" 
        xmlns="http://www.w3.org/2000/svg">

        <circle cx="50" cy="50" r="50" 
            onmouseover="check()" />

        <script type="text/javascript">
            function check() {
                document.write(
                    "This Window is closed : ", 
                    window.closed);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/1a414275ed50527ff1d11400fcf4a4a7.png)

**示例 4:** 在本例中，我们将使用 onmouseover 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000" 
        xmlns="http://www.w3.org/2000/svg">

        <text x="50" y="20" font-size="20px" 
            onmouseover="check(event)">
            GeeksForGeeks
        </text>

        <script type="text/javascript">
            function check() {
                document.write(
                    "This Window is closed : ",
                    window.closed);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/0f97388c3097c33d2647ddec4c1b13bd.png)