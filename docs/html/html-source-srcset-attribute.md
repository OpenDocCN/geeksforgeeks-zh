# HTML |源 srcset 属性

> 原文:[https://www.geeksforgeeks.org/html-source-srcset-attribute/](https://www.geeksforgeeks.org/html-source-srcset-attribute/)

**HTML srcset 属性**用于指定在不同情况下要使用的图像的网址。<图片<中使用>源时，需要
**语法:**

```html
<source srcset="URL">
```

**属性值**

*   网址:指定图片的网址

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>

<html>

<head>

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

</head>

<body>

    <picture>

        <source media="(min-width: 600px)"
                srcset=
"https://media.geeksforgeeks.org/wp-content/uploads/20190328185307/gfg28-300x83.png">

        <source media="(min-width: 400px)"
                srcset=
"https://media.geeksforgeeks.org/wp-content/uploads/20190809013546/gfg_350X350-300x300.png">

        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190521140445/gfglogo2.png"
             style="width:auto;">

    </picture>

</body>

</html>
```

**输出:**更改浏览器大小

![](img/11d75a22300d1eaf21322ef1a88a13d0.png)

![](img/f3dcb6a0c75a93f428a2d45b0f512106.png)

![](img/695c31d021318cf52f42e6df7a441c05.png)

**支持的浏览器:****HTML srcset 属性**支持的浏览器如下

*   谷歌 Chrome 4.0
*   Firefox 4.0
*   苹果 Safari 4.0
*   歌剧 10.5
*   边缘