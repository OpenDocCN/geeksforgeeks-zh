
# HTML | onreset 事件属性

> 原文: [https://www.geeksforgeeks.org/html-onreset-event-attribute/](https://www.geeksforgeeks.org/html-onreset-event-attribute/)

重置表单时，会触发 HTML 中的 `onreset` 事件属性。该属性适用于表单标签。

**支持的标签:**

*   `<form>`

**语法:**

```html
<form onreset="script">
```

**属性值:** 该属性包含单值 `script`，该脚本在设置事件调用时工作。

**例:**

## 超文本标记语言

```html
<!DOCTYPE html >
<html>
    <head>
        <title>onreset 事件属性</title>
        <style>
            body {
                text-align:center;
            }
            h1 {
                color:green;
            }
        </style>
        <script>
            function Geeks() {
                alert("Form Reset...") ;
            }
        </script >
    </head>
    <body>
        <h1>GeeksforGeeks</h1>
        <h2>onreset 事件属性</h2>
        <form onreset="Geeks()" style="color:blue;">
            First Name: <input type="text"></br>
            Last Name: <input type="text"></br>
            <input type="reset">
        </form>
    </body>
</html>
```

**输出:**

![onreset](img/08b595a5af88b9b332b45dafe383e027.png)

**支持的浏览器:** 设置事件属性时，以下浏览器支持:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   歌剧
*   火狐浏览器
*   旅行队
