# HTML | DOM readyState 属性

> 原文:[https://www.geeksforgeeks.org/html-dom-readystate-property/](https://www.geeksforgeeks.org/html-dom-readystate-property/)

HTML 中的 **readyState 属性**用于返回当前文档的加载状态。此属性用于只读。

**语法:**

```html
document.readyState
```

**返回值:**返回一个字符串值，用于定义当前单据的状态。下面列出了五种状态之一:

*   未初始化:进程未开始加载。
*   加载:进程正在加载。
*   已加载:进程已加载。
*   交互:进程加载足以与用户交互。
*   完成:进程完全加载。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>DOM readyState Property</title>
        <style>
            h1 {
                color:green;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>DOM readyState Property</h2>
        <button onclick="Geeks()">Submit</button>
        <p id="sudo"></p>
        <script>
            function Geeks() {
                var x = document.readyState;
                document.getElementById("sudo").innerHTML = x;
            }
        </script>
    </body>
</html>                    
```

**输出:**
![](img/94dc7f75c7bdac2feb3999e928bd3db9.png)

**支持的浏览器:**T2 DOM readyState 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队