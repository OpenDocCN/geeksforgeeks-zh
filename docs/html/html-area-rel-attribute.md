# HTML | rel 属性

> 原文:[https://www.geeksforgeeks.org/html-area-rel-attribute/](https://www.geeksforgeeks.org/html-area-rel-attribute/)

rel 属性用于指定当前文档和链接文档之间的关系。它仅在 href 属性存在时使用。

**语法:**

```html
<area rel="value">
```

**属性值:**

*   **替代版本:**它定义了文档的替代版本，即打印页面、翻译版本或镜像版本。
*   **作者:**定义文档的作者。
*   **书签:**指定相关文档。
*   **帮助:**指定帮助文档。
*   **许可:**定义文档的版权信息。
*   **下一步:**定义选择中的下一个文档。
*   **nofollow:** 它被谷歌使用，用来指定谷歌搜索蜘蛛不应该跟随那个链接，并且主要用于付费链接。
*   **noreferrer:** 用于指定如果用户跟随超链接，浏览器不应发送 HTTP referrer 头。
*   **预取:**指定缓存目标文档。
*   **prev:** 指定选择中的上一个文档。
*   **搜索:**指定文档的搜索工具。
*   **标签:**指定当前文档的标签关键字。

**注意:**<区域> rel 属性在 HTML 5 中是新的。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML area rel Attribute
    </title>
</head>

<body style="text-align:center;">
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190227165729/area11.png"
        alt="" width="300" height="119" class="aligncenter"
        usemap="#shapemap" />

    <map name="shapemap">

        <!-- area tag contained image. -->
        <area shape="poly" coords="59, 31, 28, 83, 91, 83"
href="https://media.geeksforgeeks.org/wp-content/uploads/20190227165802/area2.png"
            alt="Triangle" rel="alternate">

        <area shape="circle" coords="155, 56, 26"
href="https://media.geeksforgeeks.org/wp-content/uploads/20190227165934/area3.png"
            alt="Circle" rel="alternate">

        <area shape="rect" coords="224, 30, 276, 82"
href="https://media.geeksforgeeks.org/wp-content/uploads/20190227170021/area4.png"
            alt="Square" rel="alternate">
    </map>
</body>

</html>                   
```

**输出:**

*   **点击具体可点击区域前:**

![alt_attribute](img/a3b203165e8b29b598811a0482f8953d.png)

*   **点击具体可点击区域后:**

![alt_attribute](img/4b7c1e6272be5affb61b29773d446e39.png)

**支持的浏览器:**HTML<区域> rel 属性支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧