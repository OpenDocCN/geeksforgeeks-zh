# 使用 CSS 和 JS 设计跟随鼠标光标的笑脸眼

> 原文:[https://www . geesforgeks . org/design-笑脸-眼睛-跟随-鼠标-光标-使用-css-and-js/](https://www.geeksforgeeks.org/design-smiley-face-eyes-that-follow-mouse-cursor-using-css-and-js/)

一张使用了超文本标记语言、CSS 和 JavaScript 的动画脸。脸部将跟随光标。它是简单的 CSS 和 JavaScript 效果之一。对于初学者来说，学习伪元素的概念是最好的例子之一。

**手法:**一张脸的基本思路就是来源于 CSS。在这里，整个动画将由 CSS 和一点点 Javascript 制作。主要是用 CSS 制作卡通脸，用 Javascript 帮助流动脸的眼球。主要思想是面部的眼球会向鼠标指针移动，当鼠标来到面部时，它会闭上嘴，而不是张开嘴微笑。

**HTML 代码:**使用 HTML 我们将制作人脸的基本结构。我们将采取一些草皮，并给他们一些类名，因为我们可以在未来装饰它。

## html

```html
<div class="face">
    <div class="eyes">
        <div class="eye"></div>
        <div class="eye"></div>
    </div>
</div>
<div class="face">
    <div class="eyes">
        <div class="eye"></div>
        <div class="eye"></div>
    </div>
</div>
```