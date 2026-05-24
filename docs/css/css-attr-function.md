# CSS | attr()函数

> 原文:[https://www.geeksforgeeks.org/css-attr-function/](https://www.geeksforgeeks.org/css-attr-function/)

attr()函数是 CSS 中的一个内置函数，它返回所选元素的属性值。
**语法:**

```html
attr( attr_name )
```

**参数:**该函数接受单个参数 *attr_name* ，用于保存 HTML 元素中属性的名称。它是强制参数。
**返回值:**该函数返回所选元素的属性值。
下面的例子说明了 CSS 中的 attr()函数:
**程序:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
    <head>
        <title>attr function</title>
        <style>
            a:before {
                content: attr(href) " =>";
            }
            a {
                text-decoration:none;
            }
            .gfg {
                font-size:40px;
                color:green;
                font-weight:bold;
            }
            body {
                text-align:center;
            }
        </style>
    </head>
    <body>
        <div class = "gfg">GeeksforGeeks</div>
        <h1>The attr() Function</h1>
        <a href="https://www.geeksforgeeks.org">GeeksforGeeks</a>
    </body>
</html>
```

**输出:**

![](img/be6c52bca0491b397c58b7a827838d42.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   狩猎