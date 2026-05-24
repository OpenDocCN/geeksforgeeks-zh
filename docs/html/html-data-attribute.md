# HTML |数据属性

> 原文:[https://www.geeksforgeeks.org/html-data-attribute/](https://www.geeksforgeeks.org/html-data-attribute/)

**HTML |数据属性**用于指定*对象的嵌入文件*的网址。它可以与 **<对象>** 元素一起使用。
**语法:**

```html
<object data="URL">
```

**属性值:**包含单值 **URL** ，用于指定对象的来源。

网址的可能值有:

*   **绝对 URL** :指向另一个网站。
*   **相对 URL** :指向网站内的一个文件。

**示例:**本示例说明了数据属性的使用。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>HTML | data Attribute</title>
</head>

<body>
    <center>
        <h1>HTML | data Attribute</h1>
        <br>
    </center>

    <object data=
"https://www.geeksforgeeks.org/wp-content/uploads/Geek_logi_-low_res.png"
            width="550px"
            height="150px">
      GeeksforGeeks
  </object>

</body>

</html>
```

**输出:**

![](img/6223cc1c744e797cdc2dcd1d82703d87.png)

**支持的浏览器:***HTML 数据属性*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队