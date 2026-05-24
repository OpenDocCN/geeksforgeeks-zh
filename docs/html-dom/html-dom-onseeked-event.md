# HTML | DOM onseeked 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onseeked-event/](https://www.geeksforgeeks.org/html-dom-onseeked-event/)

当用户完成跳过媒体到一个新的位置时，在 HTML DOM 中出现 **onseeked 事件**。**突发事件**和**突发事件**正好相反。要获取媒体的当前位置，请使用*当前时间*。
**支持的标签**

*   **<音频>**
*   **<视频>**

**语法:**

*   **在 HTML 中:**

```html
<element onseeked="Script">
```

*   **在 JavaScript 中:**

```html
object.onseeked = function(){Script};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("seeked", Script);
```

**示例:**使用 addEventListener()方法。

## 超文本标记语言

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
          "videoID").addEventListener("seeked", GFGfun);

        function GFGfun() {
            alert("Media Skipped");
        }
    </script>

</body>

</html>
```

**输出:**
**前:**

![](img/c73459c4879b2ee74c02b4ad7862df72.png)

**之后:**

![](img/f9b8876e949d6a1bc5c61fdec0d156f9.png)

**支持的浏览器:****HTML DOM on seeked Event**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 9+
*   火狐浏览器
*   苹果 Safari
*   歌剧