# HTML | DOM 文档类型属性

> 原文:[https://www.geeksforgeeks.org/html-dom-doctype-property/](https://www.geeksforgeeks.org/html-dom-doctype-property/)

**DOM 文档类型属性**用于返回任意 HTML 文档的文档类型。DocumentType 对象是用于返回对象名称的名称属性。如果文档中没有声明文档类型，则返回空值。

**语法:**

```html
 document.doctype
```

**示例:**

```html
<!DOCTYPE html.5>
<html>
    <head>
        <title>DOM doctype Property</title>
        <style>
            h1, h2 {
                color:green;
                font-weight:bold;
                text-align:center;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body style="text-align:center;">
        <h1>GeeksForGeels</h1>
        <h2>DOM doctype Property</h2>
        <button onclick="geeks()">Submit</button>
        <p id="sudo"></p>
        <script>
            function geeks() {
                var gfg = document.doctype.name;
                document.getElementById("sudo").innerHTML = gfg;
            }
        </script>
    </body>
</html>                    
```

**输出:**
![](img/91b3c083ec7dd900daa9ebf769dd832a.png)

**支持的浏览器:***DOM doctype 属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队