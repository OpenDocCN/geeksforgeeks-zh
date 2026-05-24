# HTML | DOM onffline 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onoffline-event/](https://www.geeksforgeeks.org/html-dom-onoffline-event/)

浏览器离线工作时出现 DOM **onoffline** 事件。**线上**事件与**线上**事件冲突。
**注意:** *navigator.onLine* 属性用于检查浏览器的模式。
**支持的标签**

*   **<体>**

**语法:**

*   **在 HTML 中:**

```html
<element onoffline="myScript">
```

*   **在 JavaScript 中:**

```html
object.onoffline = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("offline", myScript);
```

**示例:**使用 addEventListener()方法

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM onoffline Event
    </title>
</head>

<body>
    <h1>
      GeeksforGeeks
  </h1>
    <h2>
      HTML DOM onoffline Event
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

**支持的浏览器:****HTML DOM onffline 事件**支持的浏览器如下:

*   火狐浏览器