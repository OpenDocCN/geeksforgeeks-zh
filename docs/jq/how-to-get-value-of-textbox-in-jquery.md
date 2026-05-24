# 如何在 jQuery 中获取文本框的值？

> 原文:[https://www . geeksforgeeks . org/如何在 jquery 中获取 textbox 的值/](https://www.geeksforgeeks.org/how-to-get-value-of-textbox-in-jquery/)

本文的目的是演示如何使用 [jQuery](https://www.geeksforgeeks.org/jquery-tutorials/) 获取 textbox 的值。需要对 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 、 [CSS](https://www.geeksforgeeks.org/css-tutorials/) 、 [jQuery](https://www.geeksforgeeks.org/jquery-tutorials/) 有基本的了解。这可以通过使用 jQuery [val()](https://www.geeksforgeeks.org/jquery-val-with-examples/) 方法来完成。

**val()方法:**此方法用于设置或返回所选元素的属性值。

**语法:**获取文本框值的方法

```html
$().val()
```

**进场:**

*   在本地系统中创建一个文件*index.html*。
*   在您的 HTML 正文中创建一个输入字段(键入文本)。
*   要获取输入文本的值，您需要将**[**val()**](https://www.geeksforgeeks.org/jquery-val-with-examples/)**方法附加到特定的选定输入元素。****

******示例:**在本例中，我们将看到输入 **val()** 方法的使用。我们获取一个输入字段(键入文本)并为其附加一个输入事件监听器。当用户在文本框中键入任何字母或单词时，它将立即在输入字段的底部显示文本。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
<html>

<head>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js">
    </script>

    <script type="text/javascript">
        $(document).ready(function () {
            $('.textbox').on('input', function () {

                // Set the inner text of the
                // of the span tag
                $('span').text($('.textbox').val());
            });
        });
    </script>

    <style>
        .container {
            display: flex;
            justify-content: center;
        }

        h1 {
            color: green;
        }

        span {
            margin-top: 10px;
        }
    </style>
</head>

<body>
    <h1 class="container">
        GeeksforGeeks
    </h1>

    <div class="container">
        <input class="textbox" 
            type="text" placeholder="Text" />
    </div>

    <span class="container"></span>
</body>

</html>**
```

******输出:******

****![](img/9e20d4b810a8e4fc44ef14f96c46778d.png)****