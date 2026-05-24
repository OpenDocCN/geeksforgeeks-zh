# HTML | a 下载属性

> 原文:[https://www.geeksforgeeks.org/html-a-download-attribute/](https://www.geeksforgeeks.org/html-a-download-attribute/)

**下载属性**用于用户点击超链接时*下载元素。它仅在设置了 href 属性时使用。下载的文件名将是属性值。属性值将是下载文件的名称。如果该值被删除，则使用原始文件名。*

**语法:**

```html
<a download="filename">
```

**属性值:**包含单值文件名，可选。它为下载的文件指定新的文件名。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
      HTML a download Attribute
  </title>
</head>

<body>

    <p>Click on image to download
        <p>

            <a href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190221234751/geeksforgeeks-logo1.png" 
               download>
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190221234751/geeksforgeeks-logo1.png" 
                 alt="gfg" 
                 width="500" 
                 height="200">
            </a>

</body>

</html>
```

**输出:**
![](img/df17e594b3178f81da9e2af6799c4a46.png)

**支持的浏览器:**以下是 *HTML < a >下载属性*支持的浏览器:

*   谷歌 Chrome 14.0
*   Internet Explorer 13.0
*   Firefox 20.0
*   Safari 10.1
*   Opera 15.0