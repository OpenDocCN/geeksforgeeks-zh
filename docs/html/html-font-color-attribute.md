# HTML | font 颜色属性

> 原文:[https://www.geeksforgeeks.org/html-font-color-attribute/](https://www.geeksforgeeks.org/html-font-color-attribute/)

**HTML <字体>颜色属性**用于*指定<字体>元素*内部的文本颜色。

**语法:**

```html
<font color="color_name|hex_number|rgb_number">
```

**属性值:**

*   **color_name:** 使用颜色名称设置文本颜色。例如:**【红色】**。
*   **十六进制数:**使用颜色十六进制码设置文本颜色。例如:**“# 0000 ff”**。
*   **rgb_number:** 用 rgb 码设置文字颜色。例如:**“RGB(0，153，0)”**。

**注意:**html 5 不支持<字体>颜色属性。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        HTML font face Attribute
    </title>
</head>

<body>
    <font size="6"
          face="verdana"
          color="green">
            GeeksforGeeks!
        </font>
    <br>

    <font size="6"
          face="arial" 
          color="#008000">
            GeeksforGeeks!
        </font>
    <br>

    <font size="6"
          color="rgb(128, 128, 0)">
            GeeksforGeeks!
        </font>
</body>

</html>
```

**输出:**
![](img/d3313b5b9d1f51c7ee7c300099de5eb5.png)

**支持的浏览器:**支持的浏览器 **HTML <字体>颜色属性**如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。