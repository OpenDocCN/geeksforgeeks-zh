# HTML | 下载属性

> 原文:[https://www.geeksforgeeks.org/html-area-download-attribute/](https://www.geeksforgeeks.org/html-area-download-attribute/)

下载属性用于用户点击超链接时下载目标内容。它仅在设置了 href 属性时使用。下载文件的名称将是属性值。浏览器会自动检测正确的文件扩展名并将其添加到文件中。如果该值被删除，则使用原始文件名。
**语法:**

```html
<area download="filename">
```

**属性值:**包含单值**文件名**，可选。它为下载的文件指定新的文件名。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML area download Attribute
    </title>
</head>

<body style="text-align:center;">
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165729/area11.png"
        alt="alt_attribute" width="300" height="119"
        class="aligncenter" usemap="#shapemap" />

    <map name="shapemap">

        <!-- area tag contained image. -->
        <area shape="poly" coords="59, 31, 28, 83, 91, 83" href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165802/area2.png"
        alt="Triangle" download>

        <area shape="circle" coords="155, 56, 26" href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165934/area3.png"
        alt="Circle" download>

        <area shape="rect" coords="224, 30, 276, 82" href=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227170021/area4.png"
        alt="Square" download="rect">
    </map>
</body>

</html>                   
```

**输出:**

*   **点击前具体可点击区域:**

![alt_attribute](img/a3b203165e8b29b598811a0482f8953d.png)

*   **点击具体可点击区域后:**该区域的文件将下载。

![alt_attribute](img/4b7c1e6272be5affb61b29773d446e39.png)

**支持的浏览器:**区域>下载属性支持的浏览器如下:

*   谷歌 Chrome 14.0
*   Firefox 20.0
*   Opera 15.0