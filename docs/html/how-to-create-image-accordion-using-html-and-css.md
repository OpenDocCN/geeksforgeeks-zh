# 如何使用 HTML 和 CSS 创建图像手风琴？

> 原文:[https://www . geesforgeks . org/how-create-image-accordion-use-html-and-CSS/](https://www.geeksforgeeks.org/how-to-create-image-accordion-using-html-and-css/)

在本文中，我们将创建一个图像手风琴，它基本上用于使用 HTML 和 CSS 的电子商务网站上的广告目的。

**方法:**

*   Create an HTML file, in which we will add different types of advertising images.
*   Create a CSS style to give some animation effects to webpage elements.

**HTML 代码:**

1.  First, create an HTML file (index.html).
2.  Now, after our HTML file is created, we will use the tag to give a title to our webpage. It should be placed in the label.
3.  Then link the CSS file that provides all animation effects to our HTML. This is also placed on the label.
4.  Come to the main body of our HTML code.
    1.  Then we have to add different advertisements.

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href="style.css">
</head>

<body>
    <div class="main_box">
        <div class="img img1">
            <p>gfg 1</p>
        </div>

        <div class="img img2">
            <p>gfg 2</p>
        </div>

        <div class="img img3">
            <p>gfg 3</p>
        </div>

        <div class="img img4">
            <p>gfg 4</p>
        </div>
    </div>
</body>

</html>
```