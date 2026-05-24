# HTML | 方案属性

> 原文:[https://www.geeksforgeeks.org/html-meta-scheme-attribute/](https://www.geeksforgeeks.org/html-meta-scheme-attribute/)

**HTML <元>方案属性**用于指定一个方案来解释属性的值。
**语法:**

```html
<meta scheme="format | URI">
```

**属性值:**

*   **格式/URI:** 用于定义内容属性内部值的格式(或指向包含信息的 URI)。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="keywords" 
          content="Meta Tags, Metadata" 
          scheme="ISBN" />
</head>

<body>
    <center>
        <h1>GeeksForGeeks</h1>
        <h2> Meta scheme attribute</h2>
        <p>Hello GeeksforGeeks!</p>
    </center>
</body>

</html>            
```

**输出:**
![](img/6cc62f7c2784bc059fea822688f7fdae.png)

**支持的浏览器:**以下是 **HTML < meta >方案属性**支持的浏览器:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队