# HTML pre Tag

> 原文:[https://www.geeksforgeeks.org/html-pre-tag/](https://www.geeksforgeeks.org/html-pre-tag/)

HTML 中的

```html
标记用于定义预格式化文本的块，它保留了文本空格、换行符、制表符和其他被网页浏览器忽略的格式化字符。< pre >元素中的文本以固定宽度字体显示，但可以使用 CSS 进行更改。< pre >标签需要一个开始和结束标签。
 语法: 

```

```html
<pre> Contents... </pre>
```

以下示例说明了 HTML 中的

```html
标记:
 示例 1:  

```

## 超文本标记语言

```html
<html>
    <body>
        <!-- html pre tag starts here -->
        <pre>
            GeeksforGeeks
            A Computer   Science Portal   For Geeks
        </pre>
        <!-- html pre tag ends here -->
    </body>
</html>                   
```

**输出:**

![](img/a601540f516f9698acad8460f26932e4.png)

**例 2:**

## 超文本标记语言

```html
<html>
    <head>
        <title>pre tag with CSS</title>
        <style>
            pre {
                font-family: Arial;
                color: #009900;
                margin: 25px;
            }
        </style>
    </head>
    <body>
        <!-- html pre tag starts here -->
        <pre>
            GeeksforGeeks
            A Computer   Science Portal   For Geeks
        </pre>
        <!-- html pre tag ends here -->
    </body>
</html>
```

**输出:**

![](img/803691ff4c2b4fb83e984f9829cc0737.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队