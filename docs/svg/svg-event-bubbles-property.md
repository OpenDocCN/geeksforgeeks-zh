# SVG 事件.气泡属性

> 原文:[https://www.geeksforgeeks.org/svg-event-bubbles-property/](https://www.geeksforgeeks.org/svg-event-bubbles-property/)

**SVG 事件气泡属性**指示事件是否通过 DOM 出现气泡。

**语法:**

```html
var doesItBubble = event.bubbles
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
                    "This Event Bubbles : ", 
                    event.bubbles);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/c4fcb7e802a4867ed34e581b405445fd.png)

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
                    "This Event Bubbles : ", 
                    event.bubbles);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/28b8c729cea5ea12f6458afd66263599.png)

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
                    "This Event Bubbles : ", 
                    event.bubbles);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/bf0ab40b554a472a24f23d959866e35e.png)

**示例 4:** 在本例中，我们将使用 onmouseover 事件

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
                    "This Event Bubbles : ", 
                    event.bubbles);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/7a2aa6c2a73ec6596d904d82a36ba906.png)