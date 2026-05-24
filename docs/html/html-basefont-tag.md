# HTML <basefont>标签

> 哎哎哎:# t0]https://www . geeksforgeeks . org/html-base font 标签/

**示例:**本示例通过使用可用的 CSS 属性说明了< basefont >标签的替代方案。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Alternative of basefont tag</title>
    <style>
    body {
        text-align: center;
    }

    .gfg {
        color: green;
        font-size: 45px;
        font-family: sans-serif;
    }

    .geeks {
        font-family: arial;
    }
    </style>
</head>

<body>
    <div class="gfg">GeeksforGeeks</div>
    <div class="geeks">
      A Computer Science portal for geeks. It contains well written, 
      well thought and well explained computer science and programming articles.
      </div>
</body>
</html>
```

**输出:**

![](img/c058028a8eb2a9107b7dbdc1a195172b.png)

<basefont>标签用于设置浏览器中所有文本的默认文本颜色、字体大小、字体系列。HTML5 不再支持。因此，作为替代，我们在代码示例中使用了 CSS。互联网浏览器 9 和早期版本支持<basefont>标签。

**语法:**

```html
<basefont attributes...>
```

**属性:**该标签包含三个可选属性，如下所示:

*   [**颜色**](https://www.geeksforgeeks.org/html-basefont-color-attribute/) **:** 用于指定文档的默认文本颜色。
*   [**字号**](https://www.geeksforgeeks.org/html-basefont-size-attribute/) **:** 用于指定文档的默认字号。
*   [](https://www.geeksforgeeks.org/html-basefont-face-attribute/)****:**用于指定文档的默认字体样式。**

****示例:**下面的示例说明了 HTML 中的< basefont >标签。**

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<head>
    <title>basefont tag</title>
    <basefont color="red" size="9">
    <style>
    body {
        text-align: center;
    }

    .gfg {
        font-size: 40px;
        font-weight: bold;
        color: green;
    }

    .geeks {
        font-size: 25px;
        font-weight: bold;
    }
    </style>
</head>

<body>
    <div class="gfg">GeeksforGeeks</div>
    <div class="geeks"><basefont> Tag</div>
    <p>A computer science portal for geeks</p>

</body>

</html>
```

****输出:**** 

**![](img/7ce8421ec47552f9b3f66a087f6ad7f8.png)**

****支持的浏览器:**除了 11.0 版或更低版本的 Internet Explorer 之外，任何浏览器都不支持此标签。**