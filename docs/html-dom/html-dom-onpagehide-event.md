# HTML | DOM onpagehide 事件

> 哎哎哎:# t0]https://www . geeksforgeeks . org/html-DOM-onpagehide-event/

HTML 中的 **DOM onpagehide 事件**发生在用户从网页下车的时候。例如，关闭浏览器窗口、点击链接、刷新页面等。
不缓存在**空载事件**中的页面，使用 **onpagehide 事件**代替**空载事件**。
**支持的标签**

*   **<体>**

**语法:**

*   **在 HTML 中:**

```html
<element onpagehide="myScript">
```

*   **在 JavaScript 中:**

```html
object.onpagehide = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("pagehide", myScript); 
```

**示例 1:** 使用 Javascript

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
           DOM onpagehide event
        </title>
    </head>
<body>

<h1 id="hID"></h1>

<script>
document.getElementsByTagName(
    "BODY")[0].onpagehide = function()
    {GFGfun()};

function GFGfun() {
  document.getElementById(
      "hID").innerHTML = "Thank you!";
};

</script>

</body>
</html>
```