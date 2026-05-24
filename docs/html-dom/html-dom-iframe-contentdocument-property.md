# HTML | DOM IFrame content document 属性

> 原文:[https://www . geesforgeks . org/html-DOM-iframe-content document-property/](https://www.geeksforgeeks.org/html-dom-iframe-contentdocument-property/)

HTML DOM 中的 **IFrame contentDocument 属性**用于返回框架或 IFrame 元素生成的文档对象。它可以在宿主窗口中用于访问属于框架或 iframe 元素的文档对象。

**语法:**

```html
iframeObject.contentDocument 
```

**返回值:**返回文档对象的引用。如果没有可用的对象，则返回 null。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML DOM iframe contentDocument Property 
    </title> 
</head> 

<body style="text-align:center;"> 

    <h1>GeeksforGeeks</h1> 

    <h2> 
        HTML DOM iframe contentDocument Property 
    </h2> 

    <iframe src="https://ide.geeksforgeeks.org/index.php"
                id="GFG" height="200" width="400"> 
    </iframe> 

    <br><br> 

    <button onclick="Geeks()">
        Submit
    </button> 

    <script> 
        function Geeks() { 
            var iframeID = document.getElementById("GFG"); 

            var iframeCW = (iframeID.contentWindow
                    || iframeID.contentDocument);

            if (iframeCW.document)iframeCW = iframeCW.document;
                iframeCW.body.style.border = "5px solid black";
        } 
    </script> 
</body> 

</html>
```

*   **点击按钮前:**
    ![](img/3c4f0b6528407b01f16bf49116913b69.png)
*   **点击按钮后:**
    ![](img/3b0cfd16c77a8cb742dc3d89b120f941.png)

**支持的浏览器:**HTML DOM IFrame content document 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧