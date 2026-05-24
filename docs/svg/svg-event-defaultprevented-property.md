# SVG 事件.默认阻止属性

> 原文:[https://www . geesforgeks . org/SVG-event-default prevented-property/](https://www.geeksforgeeks.org/svg-event-defaultprevented-property/)

**SVG event . DefaultProtected 属性**返回一个布尔值，指示对 Event.preventDefault()的调用是否取消了事件。

**语法:**

```html
var defaultWasPrevented = event.defaultPrevented
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
                    "This Event is defaultPrevented : ", 
                    event.defaultPrevented);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/365bacf2d7b8a70a0de27b23a4155ec5.png)

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
                    "This Event is defaultPrevented : ",
                    event.defaultPrevented);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/6803bb0725402e3d7ea4483d6f41ad19.png)

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
                    "This Event is defaultPrevented : ", 
                    event.defaultPrevented);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/32260deba6e3fd97b4a4fa24a5625b72.png)

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
                    "This Event is defaultPrevented : ",
                    event.defaultPrevented);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/6ef3c2bcb0ec1357ccfd62817031b581.png)