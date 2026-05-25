# HTML DOM onmouseenter 事件

> 哎哎哎:# t0]https://www . geeksforgeeks . org/html-DOM-onoussener-event/

当鼠标指针移动到一个元素上时，就会出现 HTML 中的 **DOM onmouseenter 事件**。这个事件与 **onmouseleave** 事件相反。
本次活动类似于 **onmouseover** 事件。

**支持的标签：** 支持所有 HTML 元素，除了：

*   `<base>`
*   `<bdo>`
*   `<br>`
*   `<head>`
*   `<html>`
*   `<iframe>`
*   `<meta>`
*   `<param>`
*   `<script>`
*   `<style>`
*   `<title>`

**语法：**

*   **在 HTML 中：**

```html
<element onmouseenter="myScript">
```

*   **在 JavaScript 中：**

```javascript
object.onmouseenter = function(){myScript};
```

*   **在 JavaScript 中，使用 `addEventListener()` 方法：**

```javascript
object.addEventListener("mouseenter", myScript);
```

## 示例：使用 `addEventListener()` 方法

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM onmouseenter Event
    </title>
</head>

<body>
    <center>
        <h1 id="demo">GeeksforGeeks</h1>
    </center>
    <script>
        document.getElementById(
          "demo").addEventListener(
          "mouseenter", enter);

        function enter() {
            document.getElementById(
              "demo").style.color = "green";
        }
    </script>

</body>

</html>
```

**输出：**

![](img/3c321c688260a4516567181c445577fe.png)

## 支持的浏览器

事件中 HTML DOM 支持的浏览器如下：

*   Google Chrome 30.0
*   Internet Explorer 5.5
*   Firefox
*   Safari 6.1
*   Opera 11.5