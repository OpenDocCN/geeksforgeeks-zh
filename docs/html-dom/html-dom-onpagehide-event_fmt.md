# HTML DOM onpagehide 事件

> 哎哎哎: [https://www.geeksforgeeks.org/html-DOM-onpagehide-event/](https://www.geeksforgeeks.org/html-DOM-onpagehide-event/)

HTML 中的 `DOM onpagehide` 事件发生在用户离开网页的时候。例如，关闭浏览器窗口、点击链接、刷新页面等。
不缓存在 `pagehide` 事件中的页面，使用 `onpagehide` 事件代替 `onunload` 事件。

## 支持的标签

*   `<body>`

## 语法

*   在 HTML 中:

```html
<element onpagehide="myScript">
```

*   在 JavaScript 中:

```html
object.onpagehide = function(){myScript};
```

*   在 JavaScript 中，使用 `addEventListener()` 方法:

```html
object.addEventListener("pagehide", myScript); 
```

## 示例 1: 使用 Javascript

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