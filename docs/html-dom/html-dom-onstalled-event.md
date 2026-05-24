# HTML | DOM 舞台事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onstalled-event/](https://www.geeksforgeeks.org/html-dom-onstalled-event/)

当媒体数据被浏览器获取但数据不可用时，就会发生 HTML DOM 中的 onstalled 事件。

**语法:**

*   **在 HTML 中:**

    ```html
    <element onstalled="myScript">
    ```

*   **在 JavaScript 中:**

    ```html
    object.onstalled = function(){myScript};
    ```

*   **在 JavaScript 中，使用 addEventListener()方法:**

    ```html
    object.addEventListener("stalled", myScript); 
    ```

**支持的标签:**

**示例:**使用 addEventListener()方法

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM onseeked Event
    </title>
</head>

<body>
    <center>
        <h1 style="color:green">GeeksforGeeks</h1>
        <h2>HTML DOM onseeked Event</h2>

        <video controls id="videoID">
            <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190723123920/secondneon.mp4" 
                    type="video/mp4">
        </video>
    </center>
    <script>
        document.getElementById(
            "videoID").addEventListener("stalled", GFGfun);

        function GFGfun() {
            alert(
              "Data of this media not available");
        }
    </script>

</body>

</html>
```

**支持的浏览器:****HTML DOM 前台事件**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧