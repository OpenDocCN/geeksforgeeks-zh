# HTML 前台属性

> 原文:[https://www.geeksforgeeks.org/html-onstalled-attribute/](https://www.geeksforgeeks.org/html-onstalled-attribute/)

**HTML onstaled Attribute**是一个事件属性，当媒体数据通过浏览器但数据不可用时发生。

**支持的标签:**

*   **<音频>**
*   **<视频>**

**语法:**

```html
<element onstalled="myScript">
```

**属性值:**该属性包含一个单值脚本，在启动事件属性调用时工作。该属性由 [**<【音频】>**](https://www.geeksforgeeks.org/html5-audio/)[**<和【视频】>**](https://www.geeksforgeeks.org/html5-video/) 标签支持。

**示例 1:** 在本例中，我们将在视频标签上应用 onstalled 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML onstalled Attribute
    </title>
</head>

<body>
    <center>
        <h1 style="color:green">GeeksforGeeks</h1>
        <h2>HTML onstalled Attribute</h2>

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

**输出:**

![](img/547687f4e193a20f1060c319770c6574.png)

**示例 2:** 在本例中，我们将在音频标签上应用 onstalled 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML onstalled Attribute
    </title>
</head>

<body>
    <center>
        <h1 style="color:green">GeeksforGeeks</h1>
        <h2>HTML onstalled Attribute</h2>

        <audio controls id="audioID">

          <source src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190531165842/Recording1514.ogg"
                type="audio/ogg">    
        </audio>
    </center>
    <script>
        document.getElementById(
            "audioID").addEventListener("stalled", GFGfun);

        function GFGfun() {
            alert(
            "Data of this media not available");
        }
    </script>

</body>

</html>
```

输出

![](img/01e2f6e6504f0be70c43cdada0380693.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧