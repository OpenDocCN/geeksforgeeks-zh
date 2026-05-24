# 如何使用 HTML5 拖拽图片？

> 原文:[https://www . geesforgeks . org/如何使用-html5 拖放图像/](https://www.geeksforgeeks.org/how-to-drag-and-drop-images-using-html5/)

在本文中，我们将看到如何使用 HTML5 创建拖放功能。

**进场:**

*   我们已经给定了一个矩形区域和一个图像，任务是将图像拖放到矩形中。
*   我们必须启用[**ondrop =【drop(事件)】**](https://www.geeksforgeeks.org/html-ondrop-event-attribute/) 和[**ondragover =【allowDrop(事件)】**](https://www.geeksforgeeks.org/html-ondragover-event-attribute/) 来制作用于图像插入的矩形。
*   图像链接使用 [< img > src](https://www.geeksforgeeks.org/html-img-src-attribute/) 属性插入到 HTML 页面中。
*   每当我们要插入图像时，我们必须启用*draggable =“true”。*此外，启用 [**ondragstart=“拖动(事件)”**](https://www.geeksforgeeks.org/html-ondragstart-event-attribute/) ，以便该图像可以随着[设置图像宽度和高度](https://www.geeksforgeeks.org/how-to-set-the-width-and-height-of-an-image-using-html/)一起拖动。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        How to Drag and Drop Images using HTML5 ?
    </title>

    <style>
        #div1 {
            width: 350px;
            height: 70px;
            padding: 10px;
            border: 1px solid #aaaaaa;
        }
    </style>
</head>

<body>
    <p>
        Drag the GeeksforGeeks image 
        into the rectangle:
    </p>

    <div id="div1" ondrop="drop(event)" 
        ondragover="allowDrop(event)">
    </div>
    <br>

    <img id="drag1" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211014104411/gfg2.png"
        draggable="true" ondragstart="drag(event)" 
        width="336" height="69">

    <script>
        function allowDrop(ev) {
            ev.preventDefault();
        }

        function drag(ev) {
            ev.dataTransfer.setData("text", ev.target.id);
        }

        function drop(ev) {
            ev.preventDefault();
            var data = ev.dataTransfer.getData("text");
            ev.target.appendChild(document.getElementById(data));
        }
    </script>
</body>

</html>
```

**输出:**

![](img/d25aa7e09fb90cdba6014f2f4cd2ad2e.png)