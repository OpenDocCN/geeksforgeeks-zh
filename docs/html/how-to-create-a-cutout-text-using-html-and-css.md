# 如何使用 HTML 和 CSS 创建剪切文本？

> 原文:[https://www . geeksforgeeks . org/如何使用 html 和 css 创建剪切文本/](https://www.geeksforgeeks.org/how-to-create-a-cutout-text-using-html-and-css/)

![](img/5ff0ad02edffb814c544e739066c5462.png)

剪切文本用作网页的背景标题。剪切文本在网页上创造了一个吸引人的外观。为了创建一个剪切文本，我们将只使用 HTML 和 CSS。我们显示剪切文本，然后将元素的背景与元素的父元素进行文本混合。为此需要 [**CSS 混合-混合-模式属性**](https://www.geeksforgeeks.org/css-mix-blend-mode-property/) 。将本文分成两个部分来创建结构，然后我们将在该结构上应用 CSS。

**创建结构:**在本节中，我们将只使用 HTML 制作剪切文本结构。

*   **HTML 代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        Creating Cutout text with HTML and CSS
    </title>

</head>

<body>
    <div class="container">

        <!-- Cotout tex -->
        <h1 class="text">GeeksforGeeks</h1>

<p>
            "A Computer Science Portal<br>   
            for Geeks"
        </p>

    </div>
</body>

</html>
```