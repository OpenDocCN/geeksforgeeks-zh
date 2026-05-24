# 什么是 HTML 中的 Longdesc？

> 原文:[https://www.geeksforgeeks.org/what-is-longdesc-in-html/](https://www.geeksforgeeks.org/what-is-longdesc-in-html/)

一般我们用 [alt](https://www.geeksforgeeks.org/html-alt-attribute/) 文字来描述图像。有时，我们需要提供更长的图像描述，在这种情况下， *alt* 文本可能无法提供适当的空间。 [longdesc](https://www.geeksforgeeks.org/html-img-longdesc-attribute/) 属性就是这个问题的解决方案。我们必须提供包含图像描述的网页链接或网址作为 longdesc 属性的值。

我们可以在 [IMG](https://www.geeksforgeeks.org/html-img-src-attribute/) 、 [iframe](https://www.geeksforgeeks.org/html-iframes/) 和、[框架](https://www.geeksforgeeks.org/html-frame-longdesc-attribute/)元素中使用 *longdesc* 属性。它可以在 IMG 元素内部使用，而不是 *alt* 文本。我们可以在 HTML [iframe](https://www.geeksforgeeks.org/html-iframes/) 元素中使用它，作为[标题](https://www.geeksforgeeks.org/html-title-attribute/)属性的补充。但是，longdesc 属性不支持大多数浏览器，因为它是从 HTML5 中移除的。

**语法:**

```html
<img src="Image_path_URL" longdesc="URL or data URI">
```

**属性值:**它将一个网址或数据 URI 作为longdesc 属性的值。

*   **完整网址:**是外部资源的网址。
*   **相对 URL:** 是内部资源的链接。
*   **基于 id 的 URL:** 使用 ID 指出同一页面上的任何元素。
*   **数据 URI:** 实际内容的编码版本。

**例 1:**

## 超文本标记语言

```html
<!--HTML code to demonstrate longdesc 
attribute inside the img element-->
<!DOCTYPE html>
<html>

<body>
    <h1 style="color:green">GeeksforGeek</h1>

    <!-- Id-based URL -->
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210101144014/gfglogo.png" 
         width="100"
         height="132" 
         longdesc="#longdescdeno">

    <!-- Internal URL -->
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210101144014/gfglogo.png"
         width="100"
         height="132" 
         longdesc="longdesc.txt">

    <!-- External URL -->
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210101144014/gfglogo.png" 
         width="100" 
         height="132" 
         longdesc=
 "https://www.geeksforgeeks.org/html-iframe-longdesc-attribute/">

    <!--data:URI -->
    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210101144014/gfglogo.png" 
         width="100"
         height="132" 
         longdesc=
"data:text/html;charset=utf-8;,%3C!DOCTYPE%20html%3E%3Chtml%3E%3Chead%3E%3Ctitle%3EDescription%20of%20the%20Logo%3C/title%3E%3C/head%3E%3Cbody%3E%3Cp%3ESome%20description%20goes%20here%3C/body%3E%3C/html%3E">
</body>
</html>
```

**输出:**

![](img/5ee6aeb3436c767c13d926001d742bd4.png)

在 HTML 5 中，我们可以使用 [**< a >**](https://www.geeksforgeeks.org/html-a-tag/) 标签来提供图片的外部或内部资源的链接。它是 *longdesc* 的最佳替代品，所有浏览器都支持。

**语法:**

```html
<a herf="image_description_URL"> <img src="image_path_URL"> </a>
```

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <a href=
"https://www.geeksforgeeks.org/html-iframe-longdesc-attribute/"> 
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210101144014/gfglogo.png">
    </a>
</body>

</html>
```

**输出:**

![](img/be0ccae85f498251032583ff122171cb.png)

**结论:**由于大多数浏览器不支持 *longdesc* 属性，用户应该在 [< a >](https://www.geeksforgeeks.org/html-a-tag/) 标签内使用[T5】img](https://www.geeksforgeeks.org/html-img-tag/)标签为图片提供长描述。