# SVG 事件.返回值属性

> 原文:[https://www . geesforgeks . org/SVG-event-return value-property-2/](https://www.geeksforgeeks.org/svg-event-returnvalue-property-2/)

SVG `<em>` Event.returnValue 属性指示此事件的默认操作是否已被阻止。

**语法:**

```html
var bool = event.returnValue
```

**返回值:**该属性返回事件元素的布尔值。

**示例 1:** 在本例中，我们将使用 *onclick* 事件作为 SVG `<em>`圆元素。

## 超文本标记语言

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
                    "This Event is returnValue : ",
                    event.returnValue);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/f06eb1024a89dad18b410088a314d477.png)

**示例 2:** 在本例中，我们将对 SVG `<em>`文本元素使用 *onclick* 事件。

## 超文本标记语言

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
                    "This Event is returnValue : ",
                    event.returnValue);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/0152649cc6e9abe507982693dd9b5616.png)

**示例 3:** 在本例中，我们将使用 *onmouseover* 事件作为 SVG `<em>`圆元素。

## 超文本标记语言

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
                    "This Event is returnValue : ",
                    event.returnValue);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/4c90827656ce96dad1b700afc6ab4951.png)

**示例 4:** 在本例中，我们将对 SVG `<em>`文本元素使用 *onmouseover* 事件。

## 超文本标记语言

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
                    "This Event is returnValue : ",
                    event.returnValue);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/5634029f6e60ac1eab43dd377de046f9.png)