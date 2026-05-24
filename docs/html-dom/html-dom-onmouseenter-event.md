# html \ DOM 是鼠标中心事件

> 哎哎哎:# t0]https://www . geeksforgeeks . org/html-DOM-onoussener-event/

当鼠标指针移动到一个元素上时，就会出现 HTML 中的 **DOM onmouseenter 事件**。这个事件与**上一个**事件相反。
本次活动类似于**上的**活动。
**支持的标签:支持所有 HTML 元素，除了:**

*   **T2>基地**
*   **<【bdo】>**
*   **<【br】>**
*   **<头像>**
*   **< html >**
*   **< iframe >**
*   **< 当 >**
*   **<停止>**
*   **<剧本>**
*   **<风格>**
*   **<称号>**

**语法:**

*   **在 HTML 中:**

```html
<element onmouseenter="myScript">
```

*   **在 JavaScript 中:**

```html
object.onmouseenter = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("mouseenter", myScript);
```

**示例:**使用 addEventListener()方法

## 超文本标记语言

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

**输出:**

![](img/3c321c688260a4516567181c445577fe.png)

**支持的浏览器:**事件中 **HTML DOM 支持的浏览器如下:** 

*   谷歌 Chrome 30.0
*   Internet Explorer 5.5
*   火狐浏览器
*   苹果 Safari 6.1
*   歌剧 11.5