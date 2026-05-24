# 如何用 HTML 和 CSS 制作照片滑动效果？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 制作照片滑动效果/](https://www.geeksforgeeks.org/how-to-make-photo-sliding-effect-using-html-and-css/)

这是一个用 HTML 和 CSS 创建的简单而惊人的动画效果，照片像滚轮一样一张张水平移动。当鼠标指针碰到照片时，特定照片停止移动。

**进场:**这些动画的基本思路来自于 CSS 动画的*悬停*效果。让我们看看代码是如何工作的。

**HTML 代码:**使用 HTML，照片将呈圆环移动。为了创建动画，我们取了一个“div”和一个部分来适当地维护照片的区域，并且在 CSS 代码中使用了类名。我们使用 HTML i 图和 *img* 标签来标记将在页面中显示的照片。

## HTML

```html
<!DOCTYPE html>
<html>

<body>
    <div class="addition">
        <section class="slideshow">
            <div class="content">
                <div class="content-carrousel">
                    <figure class="shadow">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201105170558/geeks112.png">
                    </figure>
                    <figure class="shadow">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201105170611/geeks28.png">
                    </figure>
                    <figure class="shadow">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201105170619/geeks33.png">
                    </figure>
                    <figure class="shadow">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201105170627/geeks41.jpg">
                    </figure>
                    <figure class="shadow">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201105170635/geeks51.jpg">
                    </figure>
                    <figure class="shadow">
                        <img src=
"https://media.geeksforgeeks.org/wp-contentuploads/20201105170644/geeks61.jpg">
                    </figure>
                </div>
            </div>
        </section>
    </div>
</body>

</html>
```