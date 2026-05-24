# 如何使用 HTML 和 CSS 在鼠标悬停时旋转文字？

> 原文:[https://www . geesforgeks . org/如何使用 html 和 css 旋转鼠标悬停文本/](https://www.geeksforgeeks.org/how-to-spin-text-on-mouse-hover-using-html-and-css/)

![](img/483c172ddde9d03694bd82f29dc1e595.png)

鼠标悬停时文本的旋转称为旋转效果或旋转效果。在这种效果下，单词的每个字母沿着任何一个轴(最好是 Y 轴)旋转。每个单词都被包裹在 [**< li >标签**](https://www.geeksforgeeks.org/html-li-tag/) 中，然后使用 [**CSS:悬停选择器**](https://www.geeksforgeeks.org/css-hover-selector/) 选择器我们将在 Y 轴上旋转每个字母表。我们将把这篇文章分成两个部分，在第一部分我们将创建文本的基本结构。在第二部分中，当用户将鼠标悬停在文本结构上时，我们将使该文本结构可旋转。

**创建结构:**在本节中，我们将使用 HTML 创建结构。

*   **HTML 代码:**在这里，我们创建了一个无序列表，并将每个字母表包装在一个列表项(li)中。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport"
              content="width=device-width, initial-scale=1.0" />
        <title>Spin Text</title>
    </head>
    <body>
        <ul>
            <li>G</li>
            <li>e</li>
            <li>e</li>
            <li>k</li>
            <li>s</li>
            <li>f</li>
            <li>o</li>
            <li>r</li>
            <li>G</li>
            <li>e</li>
            <li>e</li>
            <li>k</li>
            <li>s</li>
        </ul>
    </body>
</html>
```