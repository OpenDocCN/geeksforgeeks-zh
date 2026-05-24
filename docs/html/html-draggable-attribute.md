# HTML |可拖动属性

> 原文:[https://www.geeksforgeeks.org/html-draggable-attribute/](https://www.geeksforgeeks.org/html-draggable-attribute/)

此属性用于指定元素是否可拖动。默认情况下，链接和图像是可拖动的。可拖动属性通常用于拖放操作。

**支持的标签:**支持所有 HTML 元素。

**语法:**

```html
<element draggable = "true|false|auto">
```

**属性值:**该属性包含以下三个值:

*   **true:** 该值表示元素是可拖动的。
*   **false:** 该值表示元素不可拖动。
*   **自动:**该值代表默认浏览器的使用。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>
    <head>
        <title>draggable attribute</title>
        <style>
        .dropbox {
            width: 350px;
            height: 70px;
            padding: 10px;
            border: 1px solid #aaaaaa;
        }
        h1 {
            color:green;
        }
        </style>
        <script>
            function droppoint(event) {
                var data = event.dataTransfer.getData("Text");
                event.target.appendChild(document.getElementById(data));
                event.preventDefault();
            }
            function allowDropOption(event) {
                event.preventDefault();
            }
            function dragpoint(event) {
                event.dataTransfer.setData("Text", event.target.id);
            }
        </script>
    </head>
    <body>
        <center>
        <h1>GeeksforGeeks</h1>
        <h2>draggable attribute</h2>
        <div class = "dropbox" ondrop="droppoint(event)"
        ondragover="allowDropOption(event)"></div>
        <p id="drag1" draggable="true" ondragstart="dragpoint(event)">
        GeeksforGeeks: A computer science portal for geeks</p>

        </center>
    </body>
</html>
```

**输出:**
拖动前:

![](img/b88d7f13cd94330aa5ae8f57cc93fdcd.png)

拖拽
后

![](img/7e6d51e3663aa63a382a3d814a759843.png)

**支持的浏览器:**可拖动属性支持的浏览器如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 9.0
*   Firefox 3.5
*   Opera 12.0
*   Safari 6.0