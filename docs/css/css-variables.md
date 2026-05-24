# CSS 变量

> 原文:[https://www.geeksforgeeks.org/css-variables/](https://www.geeksforgeeks.org/css-variables/)

CSS 中的**变量**就像任何其他编程语言的简单变量一样。这些变量用于存储值，并且具有可以使用这些变量的范围。变量是通过在开头和后面使用两个区分大小写的破折号(–)来定义的。变量的好处是，它允许相同的值在多个地方重用，并从一个地方更新/修改。此外，与颜色的值相比，变量名更容易理解和使用，因为它避免了一遍又一遍地复制&粘贴颜色的值。

**语法:**

```html
var( --custom-name, value );
```

[var()函数](https://www.geeksforgeeks.org/css-var-function/)可以用来取 CSS 中变量的值。

**参数:**变量 var()接受下面列出的两个参数:

*   **–自定义名称:**是接受以两个破折号开头的自定义属性名称的必需参数。
*   **值:**为可选参数。它接受当自定义属性无效时使用的回退值。

**CSS var()函数的工作:**CSS 中变量的范围可以是局部的，也可以是全局的。我们可以在整个文档中使用全局变量，而局部变量只能在声明变量的选择器内部的范围内使用。为了创建具有全局范围的变量，我们需要在**:根**选择器中声明变量，在这里它与文档的根元素进行比较。为了在局部范围内创建变量，我们可以在选择器中声明变量，在选择器中变量可以在范围内使用。

我们将通过例子理解上述概念。

**示例 1:** 该示例说明了使用 **var()函数**在:根选择器中声明&全局访问变量。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Variables</title>
    <style>
    :root {
        --bg-color: green;
        --txt-color: white;
    }
    /* var() function used here */

    body {
        background-color: var(--bg-color);
    }

    h1 {
        color: var(--txt-color);
    }

    div {
        color: var(--txt-color);
    }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <div> A computer science portal for geeks </div>
</body>
</html>
```

**输出:**

![CSSVariable](img/ec72e0fbf997ad6bfb2414f6ceb33e2c.png)

**示例 2:** 这个示例说明了使用 CSS 变量来声明变量名，而不是多次复制和粘贴相同的颜色。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>CSS Variables</title>
    <style>
    :root {
        --bg-color: green;
    }
    /* var() function used here */

    body {
        background-color: var(--bg-color);
    }

    h1 {
        color: var(--txt-color, white);
    }

    div {
        color: var(--txt-color, white);
    }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <div> A computer science portal for geeks </div>
</body>
</html>
```

**输出:**

![](img/ec72e0fbf997ad6bfb2414f6ceb33e2c.png)

**支持的浏览器:**CSS 变量支持的浏览器如下:

*   谷歌 Chrome 49.0
*   微软边缘 15.0
*   Firefox 31.0
*   Safari 9.1
*   opera 36.0