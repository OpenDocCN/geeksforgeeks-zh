# HTML | DOM IFrame contentWindow 属性

> 原文:[https://www . geesforgeks . org/html-DOM-iframe-content window-property/](https://www.geeksforgeeks.org/html-dom-iframe-contentwindow-property/)

HTML DOM 中的 **IFrame contentWindow 属性**用于返回 IFrame 元素生成的 Window 对象。它可以在宿主窗口中用于访问属于框架或 iframe 元素的文档对象。

**语法:**

```html
iframeObject.contentWindow
```

**返回值:**返回 iframe 元素生成的引用 Window 对象。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML DOM iframe contentWindow Property
    </title>
</head>

<body style="text-align:center;">

    <h1>GeeksforGeeks</h1>

    <h2> 
        HTML DOM iframe contentWindow Property 
    </h2>

    <iframe src="https://ide.geeksforgeeks.org/index.php"
            id="GFG"
            height="200" 
            width="400">
    </iframe>

    <br>
    <br>

    <button onclick="Geeks()">
        Submit
    </button>

    <script>
        function Geeks() {
            var iframeID = document.getElementById("GFG");

            var iframeCW = (iframeID.contentWindow || iframeID.contentDocument);

            if (iframeCW.document) iframeCW = iframeCW.document;
            iframeCW.body.style.border = "5px solid red";
        }
    </script>
</body>

</html>
```

**Output:**
*   **Before Clicking On Button:**

    ![](img/53a06fed1453bc351f1282b0c6209153.png)

*   **After Clicking on Button:**

    ![](img/6ea28815e52be2d5ef8ea3ce1e0f2d00.png)

**支持的浏览器:****IFrame content window 属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧