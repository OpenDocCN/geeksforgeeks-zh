# HTML DOM 加载事件

> 原文:[https://www.geeksforgeeks.org/html-dom-onload-event/](https://www.geeksforgeeks.org/html-dom-onload-event/)

HTML 中的 **DOM onload 事件**发生在对象已经被加载的时候。onload 事件主要用在 **<正文>** 标签内，以便在网页上运行将完全加载所有内容的脚本。onload 事件可用于检查用户的浏览器类型和浏览器版本，并根据信息加载网页的版本。onload 事件也可以用于 cookies。

**支持的标签:**

*   [**<正文>**](https://www.geeksforgeeks.org/html-body-tag/) **:** 用于定义 HTML 页面内部呈现的主要内容。
*   [**<框架>**](https://www.geeksforgeeks.org/html-frame-tag/) **:** 用于将网页浏览器窗口分成多个部分，每个部分可以单独加载。
*   [**<iframe>**](https://www.geeksforgeeks.org/html-iframes/)**:**用于在文档中定义一个矩形区域，浏览器可以在其中显示单独的文档，包括滚动条和边框。
*   [**< img >**](https://www.geeksforgeeks.org/html-img-tag/) **:用于在网页/网站内部添加图片。**
*   [**<输入 type="image" >**](https://www.geeksforgeeks.org/html-input-typeimage/) **:用于指定<输入>元素要显示的类型。**
*   [**<链接>**](https://www.geeksforgeeks.org/html-link-tag/) **:用于定义文档与外部资源之间的链接。**
*   [**<脚本>**](https://www.geeksforgeeks.org/html-script-tag/) **:用于定义客户端脚本。**
*   [**<样式>**](https://www.geeksforgeeks.org/html-style-tag/#:~:text=The%20tag%20in%20HTML,ar%20part%20of%20a%20page.) **:用于修改我们的文字，在页面中查看。**

**语法:**

*   **在 HTML 中:**

    ```html
    <element onload="scriptFile">
    ```

*   **在 JavaScript 中:**

    ```html
    object.onload = function(){scriptFile};
    ```

*   **在 JavaScript 中，使用** [**addEventListener()方法**](https://www.geeksforgeeks.org/javascript-addeventlistener-with-examples/)T6:

    ```html
    object.addEventListener("load", scriptFile);
    ```

**示例:**使用 addEventListener()方法

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML DOM onload Event</title>
</head>

<body>
    <center>
      <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211113003851/geeks-300x83.png" 
           id="imgid" 
           alt="GFG_logo">
        <p id="pid"></p>

        <script>
        document.getElementById("imgid").addEventListener("load", GFGFun);
        function GFGFun() {
            document.getElementById("pid").innerHTML = "Image loaded";
        }
        </script>
    </center>
</body>

</html>
```

这里， [getElementById()方法](https://www.geeksforgeeks.org/html-dom-getelementbyid-method/)将返回已经给定了一个 Id 的元素，该 ID 被传递给函数。它还可以用于更改任何特定元素的值或获取特定元素。 [DOM innerHTML 属性](https://www.geeksforgeeks.org/html-dom-innerhtml-property/)将用于设置或返回元素的 HTML 内容。

**输出:**

![](img/5c3b18f115e83994b051cbbec748343f.png)

DOM 加载事件

**支持的浏览器:****HTML DOM onload 事件**支持的浏览器如下:

*   谷歌 Chrome 1.0
*   Internet Explorer 9.0
*   微软边缘 12.0
*   Firefox 1.0
*   Safari 3.0
*   Opera 9.0