# 如何在 HTML 中将一张图片变成一个链接？

> 原文:[https://www . geeksforgeeks . org/如何将图像转换为 html 中的链接/](https://www.geeksforgeeks.org/how-to-turn-an-image-into-a-link-in-html/)

**问题陈述:**本文的目的是将一张 HTML 图片变成网页链接。

**方法:**[HTML**<a>**类型属性](https://www.geeksforgeeks.org/html-a-type-attribute/)用于创建指向同一页面上的网页、文件、位置的超链接。我们可以通过将像图像这样的元素嵌套在<和>元素中来将它们变成链接。它定义了一个超链接，用于从一个页面链接到另一个页面。如果< a >标签没有 href 属性，那么它只是一个超链接的占位符。

**语法:**

```html
<a href=""></a>
```

**注意:***href*属性用于指定链接的目的地址。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body style="text-align: center;">
    <h3>
        Click on GeeksforGeeks logo to
        Redirect into geeksforgeeks.org
    </h3>

    <a href="https://geeksforgeeks.org">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png"
             alt="Click to visit geeksforgeeks.org">
    </a>
</body>

</html>
```

**输出:**

![](img/fbc645d05a94e60cae3aea7558e9f42d.png)