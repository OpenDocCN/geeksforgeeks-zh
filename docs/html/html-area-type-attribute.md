# HTML | 类型属性

> 原文:[https://www.geeksforgeeks.org/html-area-type-attribute/](https://www.geeksforgeeks.org/html-area-type-attribute/)

类型属性用于指定链接文档的互联网媒体类型。它仅在设置了 href 属性时使用。
**语法:**

```html
<area type="media_type">
```

**属性值:**包含单值 **media_type** ，用于指定嵌入文件的互联网媒体类型。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML area type Attribute
    </title>
</head>

<body style="text-align:center;">
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165729/area11.png"
        alt="" width="300" height="119" class="aligncenter"
        usemap="#shapemap" />

    <map name="shapemap">

        <!-- area tag contained image. -->
        <area shape="poly"
            coords="59, 31, 28, 83, 91, 83"
href="https://media.geeksforgeeks.org/wp-content/uploads/20190227165802/area2.png"
            alt="Triangle" type="image/png">

        <area shape="circle"
            coords="155, 56, 26"
href="https://media.geeksforgeeks.org/wp-content/uploads/20190227165934/area3.png"
            alt="Circle" type="image/png">

        <area shape="rect"
            coords="224, 30, 276, 82"
href="https://media.geeksforgeeks.org/wp-content/uploads/20190227170021/area4.png"
            alt="Square" type="image/png">
    </map>
</body>

</html>                   
```

**输出:**

*   **点击前具体可点击区域:**

![alt_attribute](img/a3b203165e8b29b598811a0482f8953d.png)

*   **点击后具体可点击区域:**

![alt_attribute](img/4b7c1e6272be5affb61b29773d446e39.png)

**支持的浏览器:**HTML<区域>类型属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧