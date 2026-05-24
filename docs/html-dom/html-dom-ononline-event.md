# HTML | DOM 在线事件

> 原文:[https://www.geeksforgeeks.org/html-dom-ononline-event/](https://www.geeksforgeeks.org/html-dom-ononline-event/)

浏览器在线工作时出现**DOM online 事件**。**在线**事件与**在线**事件冲突。
**注意:navigator.onLine** 属性用于检查浏览器的模式。
**支持的标签**

*   **<体>**

**语法:**

*   **在 HTML 中:**

```html
<element ononline="myScript">
```

*   **在 JavaScript 中:**

```html
object.ononline = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("online", myScript);
```

**示例:**使用**添加事件侦听器()**方法

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM ononline Event
    </title>
</head>

<body>
    <h1>
      GeeksforGeeks
  </h1>
    <h2>
      HTML DOM ononline Event
  </h2>

    <script>
        window.addEventListener("online", onlineGFG);
        window.addEventListener("offline", offlineGFG);

        function onlineGFG() {
            alert("Online");
        }

        function offlineGFG() {
            alert("Offline");
        }
    </script>

</body>

</html>
```

**支持的浏览器:****HTML DOM online Event**支持的浏览器如下:

*   Firefox 3.0