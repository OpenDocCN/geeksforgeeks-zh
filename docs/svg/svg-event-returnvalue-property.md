# SVG 事件.返回值属性

> 原文:[https://www . geesforgeks . org/SVG-event-return value-property/](https://www.geeksforgeeks.org/svg-event-returnvalue-property/)

SVG `<em>` Event.returnValue 属性返回一个包含事件类型的字符串。

**语法:**

```html
let eventType = event.type5

```

**返回值:**这个属性返回一个包含事件类型的字符串。

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
                    "This Event is type : ", 
                    event.type);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/5b0cae42d1de759f1728ec4d0463acbd.png)

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
                    "This Event type is : ", 
                    event.type);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/4a3399630461dde4209b0be32f407537.png)

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
                    "This Event type is : ", 
                    event.type);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/a211aa2f05959d763810875b6bf2baa9.png)

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
                    "This Event type is : ", 
                    event.type);
            }
        </script>
    </svg>
</body>

</html>
```

**输出:**

![](img/8faa2b43a8fbb0d2b18ca9d9fb8db9c5.png)