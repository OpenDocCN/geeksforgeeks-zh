# HTML |下载属性

> 原文:[https://www.geeksforgeeks.org/html-download-attribute/](https://www.geeksforgeeks.org/html-download-attribute/)

**HTML 下载属性**用于用户点击超链接时下载元素。它仅在设置了 href 属性时使用。下载的文件名将是属性值。属性值将是下载文件的名称。如果该值被删除，则使用原始文件名。
**用法:**用于 **< a >** **和<区>** 元素。
**语法:**

```html
<Element download="filename">
```

**属性值:**包含单值**文件名**，可选。它为下载的文件指定新的文件名。

下面的例子说明了下载属性在锚元素中的使用。
**例:**

## 超文本标记语言

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

            <a href="
https://media.geeksforgeeks.org/wp-content/uploads/20190221234751/geeksforgeeks-logo1.png"
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

![](img/e0344306395b917aa5c15c8bbaf726e2.png)

**支持的浏览器:****下载属性**支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧