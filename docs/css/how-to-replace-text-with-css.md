# 如何用 CSS 替换文字？

> 原文:[https://www.geeksforgeeks.org/how-to-replace-text-with-css/](https://www.geeksforgeeks.org/how-to-replace-text-with-css/)

替换文本主要是在服务器端完成的。但是在某些情况下，我们无法控制服务器，或者我们在限制下工作，使用 CSS 替换文本可能是一种选择。
**方法 1:** 使用伪元素和具有绝对定位的可见性修改器
首先，我们包装文本并为其分配一个类。这种方法只需要很少的标记。

```html
<p class="toBeReplaced">Old Text</p>
```

文本“旧文本”需要首先隐藏，新文本必须准确定位在旧文本所在的位置。为此，我们首先使用 CSS 将该文本的*可见性*更改为*隐藏*。

```html
.toBeReplaced {
    visibility: hidden;
    position: relative;
}

```

然后，我们在完全相同的位置添加一个新文本，使用伪元素和相应的显式定位。

```html
.toBeReplaced:after {
    visibility: visible;
    position: absolute;
    top: 0;
    left: 0;
    content: "This text replaces the original.";
}

```

注意之后的*是这里使用的伪元素。我们再次使用*可见性*修改器来显示新文本。*内容*属性包含新文本。
**例:***

```html
<html>

<head>
    <style>
        .toBeReplaced {
            visibility: hidden;
            position: relative;
        }
        .toBeReplaced:after {
            visibility: visible;
            position: absolute;
            top: 0;
            left: 0;
            content: "This text replaces the original.";
        }
    </style>
</head>

<body>
    <p class="toBeReplaced">Old Text</p>
</body>

</html>
```

**输出:**

```html
This text replaces the original.
```

**方法 2:** 使用带有< span >标签
的伪元素和可见性修改器在这个方法中，我们需要更多一点的标记，但是我们不再需要为我们的新文本指定任何绝对位置。我们使用< span >标签包装文本。

```html
<p class="toBeReplaced"><span>Old Text</span></p>
```

在这个方法中，我们使用一个子元素来包装文本，也就是说，文本现在在

和标签内。所以我们可以使用*显示:无* CSS 属性来隐藏< span >元素中的文本。然后我们可以简单地替换文本，就像我们在前面的方法中所做的那样，而不需要指定任何定位。

```html
.toBeReplaced span {
    display: none;
}

.toBeReplaced:after {
    content: "This text replaces the original.";
}

```

**示例:**

```html
<html>

<head>
    <style>
        .toBeReplaced span {
            display: none;
        }
        .toBeReplaced:after {
            content: "This text replaces the original.";
        }
    </style>
</head>

<body>
    <p class="toBeReplaced"><span>Old Text</span></p>
</body>

</html>
```

**输出:**

```html
This text replaces the original.
```

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。