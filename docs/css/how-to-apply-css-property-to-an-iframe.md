# 如何对 iframe 应用 CSS 属性？

> 原文:[https://www . geeksforgeeks . org/how-apply-CSS-property-to-an-iframe/](https://www.geeksforgeeks.org/how-to-apply-css-property-to-an-iframe/)

一个 **iframe** 是**直列框架**的简称。通过使用 **iframe** 标签，您可以将另一个网页内容以矩形结构显示到 HTML 页面文档中。网页内容可以是任何视频、另一个网站、任何图像等等。这个 **iframe** 也有滚动条和边框，让文档有良好的外观和感觉。

**语法:**

```html
<iframe src="URL"></iframe>
```

**请参考:**为了更好的理解，请参考文章 [HTML | Iframes](https://www.geeksforgeeks.org/html-iframes/)

**方法 1:** 有几种技术可以将 CSS 属性应用于 iframe，如下所示。
我们可以通过在 *iframe* 标签中使用 CSS 来为 *iframe* 使用**内嵌 CSS** 。

> <iframe src="”www.geeksforgeeks.org”" style="”border:" dotted="" width:="" height:=""></iframe>

**示例:**HTML 页面的设计实现如下。

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to apply CSS property
        to an iframe?
    </title>
</head>

<body style="margin:0px;">
    <table style="width:100%; 
        border-collapse:collapse; 
        font:14px Arial, sans-serif;">
        <tr>
            <td colspan="2" style="padding:10px; 
                background-color:#16641a;">
                <h1 style="font-size:24px; 
                    color:#fbfffb;">
                    Welcome to GeeksforGeeks
                </h1>
            </td>
        </tr>

        <tr style="height:300px;">
            <td style="padding:20px; 
                background-color:#5c9b37; 
                vertical-align:top;">
                <h2>Way to gain knowledge</h2>
                <ul style="list-style:none; 
                    padding:0px; line-height:24px;">
                    <li style="color:#ffffff;">
                        Learn</li><br>
                    <li style="color:#ffffff;">
                        Practice
                    </li><br>
                    <li style="color:#ffffff;">
                        Apply to real world
                    </li>
                </ul>
            </td>
        </tr>
        <tr>
            <td colspan="2" style="padding:5px; 
                background-color:#2b2a2a; 
                text-align:center;">
                <p style="color:#ffffff;">
                    copyright © geeksforgeeks,
                    Some rights reserved
                </p>
            </td>
        </tr>
    </table>
</body>

</html>
```

**示例:**在下面的示例中，iframe 的宽度和高度都是“300px”，边框的厚度是“3px”并且*点缀了*样式。

```html
<!DOCTYPE html>
<html>

<head>
    <h4 style="color:#006400; 
        font-size:24px;">
        Apply CSS to iframe
    </h4>
</head>

<body>
    <!--inline CSS in iframe tag-->
    <iframe style="border: 3px dotted; 
        width: 300px; height: 300px;" 
        src="iframe page.html" id="Iframe">
    </iframe>
</body>

</html>                                       
```

**输出:**
![](img/3aac72286f6252aa6f5fe65362ecb39e.png)

**方法 2:** 您可以使用*内部 CSS* 来标记 HTML 文件中的 *iframe* 。

```html
<style>
    #frame {
        border: 3px dotted;
        width: 300px;
        height: 300px;
    }
</style>
<iframe src="www.geeksforgeeks.org" 
    id="frame">
</iframe>
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS iframe
    </title>
</head>

<head>
    <style>
        #Iframe {
            border: 3px dotted;
            width: 300px;
            height: 300px;
        }
    </style>
</head>

<body>
    <h4 style="color:#006400; 
        font-size:24px;">
        Apply CSS to ifram
    </h4>

    <iframe src="iframe page.html" 
        id="Iframe">
    </iframe>
    <!-- iframe tag-->
</body>

</html>
```

**输出:**
![](img/3aac72286f6252aa6f5fe65362ecb39e.png)

**方法三:**可以对 *iframe* 使用*外部 CSS* ，也就是利用外部 CSS 文件。使用 *iframe* 标签前的*链接*和 *href* 标签，为 CSS 代码创建一个不同的文件，并将其包含在 HTML 文件中。

```html
CSS file: (name of the file *iframeCss.css* )
#frame {
  border: 3px dotted;
  width: 300px;
  height: 300px;
}
```

```html
HTML file:
<link rel="stylesheet" type="text/css" href="iframeCss.css">
<iframe src="www.geeksforgeeks.org" id="frame"> </iframe>
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        CSS iframe
    </title>

    <link type="text/css" 
        rel="Stylesheet" 
        href="iframeCss.css" />

    <style>
        #Iframe {
            border: 3px dotted;
            width: 300px;
            height: 300px;
        }
    </style>
</head>

<body>

    <!--external CSS link-->
    <h4 style="color:#006400; 
    font-size:24px;">
        Apply CSS to iframe
    </h4>

    <iframe src="iframe page.html" 
        id="Iframe">
    </iframe>
    <!--iframe tag-->
</body>

</html>
```

**输出:**
![](img/3aac72286f6252aa6f5fe65362ecb39e.png)

**方法 4:** 在这种方法中，使用 JavaScript 代码在 HTML 文档的头部添加 CSS 文件链接。使用的方法有:

*   **document . createelement():**这个方法创建一个 HTML 元素来定义元素的名称。

    ```html
    var g = document.createElement('link');
    ```

*   **document.appendChild():** This method appends any value or any node at the specified tag as child value.

    ```html
    var g = document.createElement('link');
    document.head.appendChild(g)

    ```

    **g** 是一个孩子，即使用 *appendChild()* 方法添加到头部标签。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        #Iframe {
            border: 3px dotted;
            width: 300px;
            height: 300px;
        }
    </style>

    <script>
        window.onload = function () {

            // Create a link Element
            // for the css file
            var link = 
                document.createElement("link");

            // Set the attributes 
            // for link element  
            link.href = "iframeCss.css";
            link.rel = "stylesheet";
            link.type = "text/css";

            // Set the link element at the
            // 'head' of HTML document  
            document.head.appendChild(link);
        }
    </script>
</head>

<body>
    <h4 style="color:#006400; 
        font-size:24px;">
        Apply CSS to iframe
    </h4>

    <iframe src="iframe page.html"
        id="iframe1">
    </iframe>
    <!--iframe tag-->
</body>

</html>
```

**输出:**
![](img/3aac72286f6252aa6f5fe65362ecb39e.png)