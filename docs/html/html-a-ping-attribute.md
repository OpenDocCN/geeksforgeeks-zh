# HTML a ping 属性

> 原文:[https://www.geeksforgeeks.org/html-a-ping-attribute/](https://www.geeksforgeeks.org/html-a-ping-attribute/)

**HTML < a > ping 属性**通常用于指定特定的网址或网址列表，当用户点击 HTML < a > href 属性中传递的超链接时，将会收到通知。这是通过用户一点击超链接就向指定的网址发送一个简短的 HTTP post 请求来实现的。

**语法:**

```html
<a href="url_hyperlink" ping="specified_url" />
```

**属性值:**

*   **specified_url:** 这是用户一跟随 url_hyperlink 中给出的链接，就会发送短 HTTP post 请求的 url。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head> </head>
  <body>
    <h2>Welcome To GFG</h2>
    <a href=
"https://auth.geeksforgeeks.org/user/codersaty/articles"
       ping=
"https://www.geeksforgeeks.org/">
      Read codersaty articles
    </a>
  </body>
</html>
```

**输出:**

![](img/5bc82e66d67b33a27f2b05b61395316f.png)

**注意:**只要有人点击“阅读代码安全文章”，就会有一个简短的 HTTP post 请求发送到“https://www.geeksforgeeks.org/”

**支持的浏览器:**

*   Edge 17.0
*   苹果 Safari 6.0
*   Opera 15.0
*   谷歌 Chrome 15.0