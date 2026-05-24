# SVG 事件被调整属性

> 原文:[https://www.geeksforgeeks.org/svg-event-istrusted-property/](https://www.geeksforgeeks.org/svg-event-istrusted-property/)

**SVG event . istusted 属性**是一个布尔值，当事件由用户操作生成时为真。

**语法:**

```html
var eventIsTrusted = event.isTrusted
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
            onclick="check(event)" />

        <script type="text/javascript">
            function check(event) {
                document.write(
                    "This Event is Trusted : ", 
                    event.isTrusted);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/edf74c3ad9f2e33551c7916d23f8a0d0.png)

**示例 2:** 在本例中，我们将使用 onclick 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000" 
        xmlns="http://www.w3.org/2000/svg">

        <text x="50" y="20" font-size="20px" 
            onclick="check(event)">
            GeeksForGeeks
        </text>

        <script type="text/javascript">
            function check(event) {
                document.write(
                    "This Event is Trusted : ", 
                    event.isTrusted);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/813d5a8fa36cb39ed03b3535b4334d80.png)

**示例 3:** 在本例中，我们将使用 onmouseover 事件。

```html
<!DOCTYPE html>
<html>

<body>
    <svg viewBox="0 0 1000 1000" 
        xmlns="http://www.w3.org/2000/svg">

        <circle cx="50" cy="50" r="50" 
            onmouseover="check(event)" />

        <script type="text/javascript">
            function check(event) {
                document.write(
                    "This Event is Trusted : ", 
                    event.isTrusted);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/7c6becb5544c4eddae0d37d14ac12ccc.png)

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
            function check(event) {
                document.write(
                    "This Event is Trusted : ", 
                    event.isTrusted);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/dbafd06d70de04adceaf82ca9e148243.png)