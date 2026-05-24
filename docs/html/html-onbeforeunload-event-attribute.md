# HTML | onbeforeunload 事件属性

> 原文:[https://www . geesforgeks . org/html-onbeforeunload-event-attribute/](https://www.geeksforgeeks.org/html-onbeforeunload-event-attribute/)

onbeforeunload 事件在文档即将卸载时运行。此事件用于允许在对话框中显示一条消息，通知用户他/她想要停留或离开当前页面。
**支持的标签**

*   **<体>**

**语法:**

```html
<element onbeforeunload = "script">
```

**属性值:**该属性包含单值脚本，调用 onbeforeunload 事件时运行。<正文>标签支持该事件属性。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>onbeforeunload attribute</title>
        <style>
            body {
                text-align:center;
            }
            h1 {
                color:green;
            }
            a {
                text-decoration:none;
                font-weight:bold;
            }
        </style>
    </head>
    <body onbeforeunload="return myFunction()">
        <h1>GeeksforGeeks</h1>
        <h2>onbeforeunload attribute</h2>  
        <a href="https://www.geeksforgeeks.org">Go to GeeksforGeeks</a>
        <script>
        function myFunction() {
            return "This document is ready to load";
        }
        </script>
    </body>
</html>
```

**输出:**

![](img/b5780c7f96124a0c347ce5f1447ffe67.png)

**支持的浏览器:**支持*on beforenload*属性的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   Opera 15.0 及以上版本