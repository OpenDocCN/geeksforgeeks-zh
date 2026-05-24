# HTML | DOM onplaying 事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onplaying-event/](https://www.geeksforgeeks.org/html-dom-onplaying-event/)

**DOM onplaying 事件**发生在音频/视频暂停并在缓冲区后播放时。

**支持的标签**

*   **<音频>**
*   **<视频>**

**语法:**

*   **在 HTML 中:**

```html
<element onplaying="myScript">
```

*   **在 JavaScript 中:**

```html
object.onplaying = function(){myScript};
```

*   **在 JavaScript 中，使用 addEventListener()方法:**

```html
object.addEventListener("playing", myScript);
```

**示例:**使用 addEventListener()方法

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM onplaying Event
    </title>
</head>

<body>
    <center>
        <h1 style="color:green">
          GeeksforGeks
      </h1>
        <h2>HTML DOM onplaying Event</h2>

        <video controls id="vidID"
               width="320" height="240">
            <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190401140735/g4g2.mp4"
                    type="video/mp4">
        </video>

        <script>
            document.getElementById(
              "vidID").addEventListener("playing", GFGfun);

            function GFGfun() {
                alert("Video playing");
            }
        </script>
    </center>
</body>

</html>
```

**输出:**

*   **上场前:**

![](img/58343c22e60652bf236abe31d4502a0a.png)

*   **播放后:**

![](img/3d060793d14128f111f3c9dee139de06.png)

**支持的浏览器:****HTML DOM on playing Event**支持的浏览器如下:

*   谷歌 Chrome
*   Internet Explorer 9.0
*   火狐浏览器
*   苹果 Safari
*   歌剧