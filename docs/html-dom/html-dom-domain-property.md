# HTML | DOM 域属性

> 原文:[https://www.geeksforgeeks.org/html-dom-domain-property/](https://www.geeksforgeeks.org/html-dom-domain-property/)

**域名属性**用于返回当前文档中加载或运行的网站服务器的域名。

**语法:**

```html
document.domain 
```

**返回值:**返回代表当前文档中加载的网站域名的字符串值，如果域名未被识别，则返回 sentinel 或 null 值。

**示例:**

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color:green;">GeeksForGeeks</h1>
        <h2> DOM domain Property</h2>

        <button onclick="geeks()">Try it</button>

        <p id="sudo"></p>

        <script>
            function geeks() {
                var x = document.domain;
                document.getElementById("sudo").innerHTML = x;
            }
        </script>

</body>

</html>
```

**输出:**
![](img/db546eeb5e7e1822df72e9e31389e36c.png)

**支持的浏览器:**T2 DOM 域属性支持的浏览器如下:

*   谷歌 Chrome
*   火狐浏览器
*   歌剧
*   微软公司出品的 web 浏览器
*   旅行队