# HTML | DOM IFrame 对象

> 原文:[https://www.geeksforgeeks.org/html-dom-iframe-object/](https://www.geeksforgeeks.org/html-dom-iframe-object/)

HTML DOM 中的 **IFrame 对象**属性用于创建和访问对象中的< iframe >元素。内嵌框架用于在当前的 HTML 文档中嵌入另一个文档。

**语法:**

*   它用于访问<iframe>元素。<pre>var x = document.getElementById("myframe");</pre></iframe>
*   用于创建<iframe>元素。<pre>var x = document.createElement("IFRAME");</pre></iframe>

**属性值:**

*   **align:** 用于设置或返回 iframe 中 align 属性的值。HTML 5 不支持。
*   **contentDocument:** 用于返回 iframe 生成的文档对象。
*   **contentWindow:** 用于返回 iframe 生成的窗口对象。
*   **frameBorder:** 用于设置或返回 iframe 中的 frameBorder 属性。HTML 5 不支持。
*   **高度:**用于设置或返回 iframe 中的高度属性。
*   **longDesc:** 用于设置或返回 iframe 中 longDesc 属性的值。HTML 5 不支持。
*   **margin heat:**用于设置或返回 iframe 中 margin heat 属性的值。HTML 5 不支持。
*   **marginWidth:** 用于设置或返回 iframe 中 marginWidth 属性的值。HTML 5 不支持。
*   **名称:**用于设置或返回 iframe 中名称属性的值。
*   **沙盒:**用于返回 iframe 中沙盒属性的值。
*   **滚动:**用于设置或返回 iframe 中滚动属性的值。HTML 5 不支持。
*   **无缝:**用于设置或返回 iframe 是否应该看起来像是包含文档的一部分
*   **src:** 用于设置或返回 iframe 中 src 属性的值。
*   **srcdoc:** 用于设置或返回 iframe 中 srcdoc 属性的值。
*   **width:** 用于设置或返回 iframe 中 width 属性的值。

**示例 1:** 本示例描述了访问< ifram >元素的 getElementById()方法。

```html
<!DOCTYPE html>
<html>

<head>
    <title> 
        HTML DOM IFrame Object Property 
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>DOM IFrame Object Property</h2>

    <button onclick = "myGeeks()">
        Click Here!
    </button>

    <br><br>

    <iframe id = "GFGFrame" src =
        "https://ide.geeksforgeeks.org/tryit.php" 
        width = "400" height = "200">
    </iframe>

    <p id = "GFG"></p>

    <!-- script to access iframe element -->
    <script>
        function myGeeks() {
            var x = document.getElementById("GFGFrame").src;
            document.getElementById("GFG").innerHTML = x;
        }
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![iframe](img/f1e90d40f0f06b918355c4a184ba0d79.png)
**点击按钮后:**
![iframe](img/2eaf59948a06dec727b32d831ba9d462.png)

**示例 2:** 本示例描述了 document.createElement()方法来创建< iframe >元素。

```html
<!DOCTYPE html>
<html>

<head>
    <title> 
        HTML DOM IFrame Object Property 
    </title>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h2>DOM IFrame Object Property</h2>

    <button onclick = "myGeeks()">
        Click Here!
    </button>

    <br><br>

    <!-- script to create iframe element -->
    <script>
        function myGeeks() {

            /* Create iframe element */
            var ifram = document.createElement("IFRAME");

            /* Set the source attribute */
            ifram.setAttribute("src", 
                    "https://ide.geeksforgeeks.org/tryit.php");

            /* Set the iframe height */
            ifram.setAttribute("height", "200");

            /* Set the iframe width */
            ifram.setAttribute("width", "400");

            document.body.appendChild(ifram);
        }     
    </script>
</body>

</html>                    
```

**输出:**
**点击按钮前:**
![iframe](img/f22eea81f28b3a7ff7a110f7125f0b70.png)
**点击按钮后:**
![iframe](img/dd2541543d0b1044697cb6f8539178fe.png)

**支持的浏览器:***DOM IFrame Object 属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧