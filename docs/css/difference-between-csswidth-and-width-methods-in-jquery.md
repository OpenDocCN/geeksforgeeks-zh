# jQuery 中 css('width ')和 width()方法的区别

> 原文:[https://www . geeksforgeeks . org/CSS width 和 width-methods-in-jquery/](https://www.geeksforgeeks.org/difference-between-csswidth-and-width-methods-in-jquery/)

在 jQuery 中，我们有两种方法可以改变任何 HTML 元素的宽度。jQuery css()方法和 width()方法，下面这两种方法都用例子进行了恰当的描述。

[**jQuery CSS('width ')方法**](https://www.geeksforgeeks.org/jquery-css-method/) **:** 它是 jQuery 中存在的一种方法，用于获取或设置匹配元素的属性。它是用于获取或设置任何 HTML 元素宽度的属性。

**语法:**

```html
$('selector').css('width', 'value in px')
```

**参数:**

*   **宽度:**是属性名，所以会是字符串类型。
*   **值:**可以是字符串，也可以是数字。

这种改变宽度的方式，我们总是要在值中追加“**px”**。

**语法:**

要改变宽度，我们必须提供价值

```html
$("#test").css("width", "200px")
```

为了获得宽度，我们不提供任何值参数。它以像素为单位返回选定元素的宽度。

```html
$("#test").css("width")
```

**示例:**在这段代码中，我们将打印“h3”元素的默认宽度值，然后将宽度更改为 200px。这演示了如何使用 **css('width')** 获取或设置元素的宽度

## 超文本标记语言

```html
<!DOCTYPE html>

<head>
    <!-- jQuery library -->
    <script src=
"https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <h3>GeeksforGeeks</h3>
    <script>
        // Getting "h3" element default width
        document.write("Width before change : "
            + $("h3").css("width"));
        document.write("<br>");

        // Changing "h3"element width
        $("h3").css("width", "200px")

        // Now checking again width
        document.write("Width after change : "
            + $("h3").css("width"))
    </script>
</body>

</html>
```

**输出:**

![](img/41fdc2ac3b20cdb10e03415f83e8113f.png)

css(“宽度”)

[**jQuery width()方法:**](https://www.geeksforgeeks.org/jquery-width/) 该方法用于获取当前匹配元素的宽度或设置每个匹配元素的宽度。

**语法:**

```html
*$('selector').width()*
```

*   **参数**:不接受任何论证。
*   **返回值:**返回第一个匹配元素的宽度。

**示例:**

```html
$("#test").width()
```

要更改元素的宽度，请使用以下语法

**语法:**

```html
$('selector').width("value")
```

*   **参数:**它接受一个值作为参数，该参数可以是字符串或数字的类型。

**例:**在 **width()** 方法中，我们不需要在 value 中追加 **px** 这个词。

```html
$("#test").width("200")
```

**示例:**在本例中，我们将做与上面代码相同的事情，但是现在使用 **width()** 方法。

## 超文本标记语言

```html
<!DOCTYPE html>

<head>
    <!-- jQuery library -->
    <script src=
"https://code.jquery.com/jquery-git.js">
    </script>
</head>

<body>
    <h3>GeeksforGeeks</h3>
    <script>
        // Getting "h3" element default width
        document.write("Width before change : "
            + $("h3").width());
        document.write("<br>");

        // Changing "h3"element width
        $("h3").width("200")

        // Now checking again width
        document.write("Width after change : "
            + $("h3").width());
    </script>
</body>

</html>
```

**输出:**

![](img/61e5f1deb60d90f2f25855ddb875a42b.png)

宽度()

在这两种方式中，我们的输出将是相同的，因为两种方法执行相同的操作。

**jQuery 中 css('width ')和 width()方法的区别:**

<figure class="table">

| CSS(【宽度】) | 宽度() |
| --- | --- |
| **CSS()** is the method and width is the attribute name. | Is one of the methods of jQuery dimension. |
| Gets or sets the width of the matching element. | Also used to get or set the width of the matching element. |
| In this case, the return value is the width of an element with the value of "px". | It just provides value. |
| It returns the width of an element plus the value of px. For example–$ ("H3"). Css("width ") will return 200px. | Returns the width value of the element. For example–$ ("H3"). Width () will return 200. |

</figure>