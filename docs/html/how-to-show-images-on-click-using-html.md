# 如何使用 HTML 在点击时显示图像？

> 原文:[https://www . geesforgeks . org/how-show-images-on-click-use-html/](https://www.geeksforgeeks.org/how-to-show-images-on-click-using-html/)

有时，网页可能包含与页面内容不相关的图像。这些不常见的图像是在网页加载时加载的，这会增加加载时间。在网页上加载更多的时间可以减少访问者的数量。

在这篇文章中，我们提出了解决这个问题的方法。我们将学习如何仅当用户使用 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 、 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 和 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 点击图像时才显示图像。

**更改** [***显示***](https://www.geeksforgeeks.org/css-display-property/) **属性的**[**<img>**](https://www.geeksforgeeks.org/html-img-tag/)**属性使用 JavaScript:** 在此方法中，我们将设置*显示*属性内部的[<*img>*](https://www.geeksforgeeks.org/html-img-tag/)*标签使用 [*样式*我们要为图像设置](https://www.geeksforgeeks.org/html-style-attribute/)[显示:无](https://www.geeksforgeeks.org/hide-or-show-elements-in-html-using-display-property/)。之后，当用户点击按钮时，我们将调用一个访问图像的 JavaScript 函数，将其*显示*属性更改为*块。**

***步骤:***

*   *在 HTML 代码中创建 [< img >](https://www.geeksforgeeks.org/html-img-tag/) 元素。*
*   *将样式添加到元素并将 [*显示*](https://www.geeksforgeeks.org/css-display-property/) 属性设置为无。*
*   *创建一个 JavaScript“show()”*函数，可以访问图像并将*显示*属性更改为*阻止*。**
*   **在 HTML 代码中添加按钮，当用户点击它时会调用“show()”函数。**

****示例:****

## **超文本标记语言**

```html
**<!DOCTYPE html>
<html>

<head>
    <style>

        /* Set display to none for image*/
        #image {
            display: none;
        }
    </style>
</head>

<body>
    <div>
        <h1>GeeksforGeeks</h1>
        <h3>Click on the button to see image</h3>

        <!-- Add id to image -->
        <img id="image" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210915115837/gfg3.png"
            alt="GFG image" />
    </div>

    <button type="button"
        onclick="show()" id="btnID">
        Show Image
    </button>

    <script>
        function show() {

            /* Access image by id and change
            the display property to block*/
            document.getElementById('image')
                    .style.display = "block";

            document.getElementById('btnID')
                    .style.display = "none";
        }
    </script>
</body>

</html>**
```

****输出:****

**![](img/3a96e387e4e85e8c38d976106e7b881c.png)**

****使用**[**<img>**](https://www.geeksforgeeks.org/html-img-tag/)**标签用空的**[***src***](https://www.geeksforgeeks.org/html-img-src-attribute/)**属性:**显然，用空的 *src* 值，用户将无法在网页上看到图像。我们将使用为用户点击按钮而实现的 JavaScript 函数来设置 *src* 属性的值。但是，某些浏览器(如 Chrome)在使用此方法时不会移除破碎的图像图标。**

****步骤:****

*   **用空 *src* 属性创建 [< img >](https://www.geeksforgeeks.org/html-img-src-attribute/) 元素。**
*   **在 JavaScript 中创建“show()”函数，可以获取图像并将图像源链接添加到 [*src*](https://www.geeksforgeeks.org/html-img-src-attribute/) 属性中。**
*   **当用户点击时，添加调用“显示()”功能的 HTML 按钮。**

****示例:****

## **超文本标记语言**

```html
**<!DOCTYPE html>
<html>

<body>
    <div>
        <h1>GeeksforGeeks</h1>
        <h3>Click on the button to see image</h3>

        <!-- img element without src attribute -->
        <img id="image" src="" />
    </div>

    <button type="button"
        onclick="show()" id="btnID">
        Show Image
    </button>

    <script>
        function show() {

            /* Get image and change value
            of src attribute */
            let image = document.getElementById("image");

            image.src =
"https://media.geeksforgeeks.org/wp-content/uploads/20210915115837/gfg3.png"

            document.getElementById("btnID")
                    .style.display = "none";
        }
    </script>
</body>

</html>**
```