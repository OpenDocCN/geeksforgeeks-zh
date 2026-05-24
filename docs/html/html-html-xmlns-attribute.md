# HTML | xmlns 属性

> 原文:[https://www.geeksforgeeks.org/html-html-xmlns-attribute/](https://www.geeksforgeeks.org/html-html-xmlns-attribute/)

**HTML < html > xmlns 属性**用于指定文档的 xml 命名空间。

**重要提示:**该属性在 XHTML 中主要为必选项，在 HTML 4.01 中无效，在 HTML 5 中可选。

**语法:**

```html
<html xmlns="http://www.w3.org/1999/xhtml"> 
```

**属性值:**

*   **https://www.geeksforgeeks.org/**它定义了要使用的命名空间(对于 XHTML 文档)。

**示例:**

```html
<!DOCTYPE html PUBLIC 
    "-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html xmlns="http://www.geekforgeeks.org//xhtml">
<head>
    <title>Title of the document</title>
</head>

<body style="text-align: center;">
    <h1>GeeksForGeeks</h1>

    <h2>HTML xmlns Attribute</h2>

    The content of the document......
</body>

</html>
```

**输出:**
![](img/6fe088b51c21c5948cc59f2d28984679.png)

**支持的浏览器:**HTML>xmlns 属性支持的浏览器如下:

*   苹果 Safari 1.0
*   谷歌 Chrome 1.0
*   Firefox 1.0
*   Opera 1.0
*   Internet Explorer 6.0