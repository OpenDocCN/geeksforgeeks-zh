# CSS | #id 选择器

> 原文:[https://www.geeksforgeeks.org/css-id-selector/](https://www.geeksforgeeks.org/css-id-selector/)

#id 选择器用于设置给定 id 的样式。id 属性是 HTML 文档中的唯一标识符。id 选择器与#字符一起使用。

**语法:**

```html
#id {
    // CSS property
}
```

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>#id selector</title>

        <!-- CSS property using id attribute -->
        <style>
            #gfg1 {
                color:green;
                text-align:center;
            }
            #gfg2 {
                text-align:center;
            }
        </style>
    </head>

    <body>

        <!-- id attribute declare here -->
        <h1 id = "gfg1">GeeksforGeeks</h1>
        <h2 id = "gfg2">#id selector</h2>
    </body>
</html>
```

**输出:**
![](img/0c3058a7d78df26304552f9c48f63ef2.png)

**支持的浏览器:***id 选择器*支持的浏览器如下:

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   旅行队
*   歌剧