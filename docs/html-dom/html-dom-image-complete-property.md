# HTML | DOM 图像完整属性

> 原文:[https://www . geesforgeks . org/html-DOM-image-complete-property/](https://www.geeksforgeeks.org/html-dom-image-complete-property/)

HTML DOM 中的**图像完成属性**用于返回浏览器是否完成加载图像。它返回一个布尔值。
**语法:**

```html
imageObject.complete
```

**返回值:**当浏览器完成图像加载时，返回布尔假，即**真**，否则返回假。
**示例:**本示例返回图像完整属性。

## 超文本标记语言

```html
<!DOCTYPE HTML>
<html>

<head>
    <title>
        HTML | DOM Image complete Property
    </title>
</head>

<body>
    <center>

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190602171808/629-300x255.png"
             id="image" alt="" width="250" height="205"
             class="alignnone size-medium wp-image-1092360" />
        <br>
        <br>
        <button type="button" onclick="getHeight()">
          Click
        </button>
        <h4 id="text"></h4>
    </center>
    <script>
        function getHeight() {
            var imgObject = document.getElementById("image");
            var output = document.getElementById("text");
            output.innerHTML =
              "The Image is loaded completely: " + imgObject.complete;
        }
    </script>
</body>

</html>
```

**输出:**

*   点击按钮前:

![](img/b992725052f4b73ae00f0d28eede6f54.png)

*   点击按钮后:

![](img/509f92b10fbc9bb0f3631d62f67c3c09.png)

**支持的浏览器:***HTML DOM Image 完整属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队