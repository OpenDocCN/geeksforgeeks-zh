# 如何在 HTML 中标记缩写并使其易于理解？

> 原文:[https://www . geesforgeks . org/如何在 html 中标记缩写并使其易于理解/](https://www.geeksforgeeks.org/how-to-mark-abbreviations-and-make-them-understandable-in-html/)

在本文中，我们将学习如何在 HTML 中指定内容的较短版本。 [<缩写>标记](https://www.geeksforgeeks.org/html-abbr-tag/)(缩写)用于定义元素的缩写或简称。<缩写>和[缩写<缩写>](https://www.geeksforgeeks.org/html-acronym-tag/) 标记用作缩写版本，用于表示一系列字母。例如，“超文本标记语言”是“超文本标记语言”的缩写。

**语法:**

```html
<abbr title ="text">Abbreviated form</abbr>
```

**属性:**该标签接受如下描述的可选属性:

*   [**标题**](https://www.geeksforgeeks.org/html-title-attribute/) : 它用于指定元素的额外信息。当鼠标在元素上移动时，它显示信息。

**示例:**这个示例说明了在 HTML 中使用<缩写>标签。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>abbr tag</title>
</head>

<body>
    <h2>Welcome to <abbr 
        title="GeekforGeeks">GFG</abbr>
    </h2>
</body>

</html>
```

**输出:**

![](img/60a02d86e603729b30ef529d2904cb6a.png)

使用 [<缩写>标签](https://www.geeksforgeeks.org/html-abbr-tag/)根本不会显示缩写的扩展，即使鼠标悬停在上面。这使得用户很难理解缩写形式。

有两种方法可以让缩写变得容易理解:

*   使用带有标题属性的
*   使用<abbr>和</abbr>

我们将通过例子来理解这两种方式。

*   **<缩写>带标题属性:**

为了消除这个问题，<abbr>标记与标题属性结合使用，为缩写提供了扩展。当鼠标指针悬停在元素上时，浏览器会将此文本作为工具提示提供。</abbr>

**语法:**

```html
<abbr title="expanded form"> abbreviated form </abbr>
```

**示例:**在本例中，我们在<缩写>标签中使用了*标题*属性，该属性指定了关于元素的额外信息。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>abbr tag</title>
</head>

<body>
    <h2>GeeksforGeeks</h2>

    <p>
        <abbr title="GeekforGeeks">GFG</abbr>:
        A Computer Science portal for geeks.
    </p>
</body>

</html>
```

**输出:**

![](img/02129d0150fcbfc69fb47f893b8e9057.png)

*   **<缩写>与< dfn > :** <缩写>可以与< dfn >一起使用，为缩写添加定义。

**语法:**

```html
<dfn> <abbr title="Expanded form"> Abbreviated form </abbr> </dfn>
```

**示例:**此示例说明了在 HTML 中使用带有< dfn >标记的<缩写>标记。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>abbr with dfn</title>
</head>

<body>
    <h2>
        <dfn> <abbr title="Geeks For Geeks">
            GFG</abbr>
        </dfn>
        : Learn Data Structures Online At 
        Your Own Pace With The Best Of Faculty
        In The Industry.
    </h2>
</body>

</html>
```

**输出:**

![](img/ab7acf216941adf572875e23ed0ee071.png)

这些是我们可以用来标记缩写的方法，让用户可以理解它们。