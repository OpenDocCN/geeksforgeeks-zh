# HTML | DOM 最后修改属性

> 原文:[https://www . geesforgeks . org/html-DOM-last modified-property/](https://www.geeksforgeeks.org/html-dom-lastmodified-property/)

HTML 中的 **DOM lastModified 属性**用于返回上次修改的当前文档的日期和时间。此属性是只读的。此属性返回一个字符串，该字符串包含文档上次修改的日期和时间。

**语法:**

```html
document.lastModified
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      DOM lastModified Property
    </title>
</head>

<body style="text-align:center">

    <h1 style="color:green;">
            GeeksForGeeks
        </h1>

    <h2>
            DOM lastModified Property
        </h2>
    <button onclick="geeks()">
        Submit
    </button>

    <p id="sudo"></p>

    <script>
        /* Function to use lastModified property */
        function geeks() {
            var x = document.lastModified;
            document.getElementById("sudo").innerHTML = x;
        }
    </script>
</body>

</html>     
```

**输出:**
![](img/c023642f15413b5902545a1348c9e94a.png)

**支持的浏览器:**DOM last modified Property 支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队