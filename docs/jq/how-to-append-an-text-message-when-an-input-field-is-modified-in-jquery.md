# jQuery 中修改输入字段时如何追加文本消息？

> 原文:[https://www . geesforgeks . org/如何在 jquery 中修改输入字段时追加文本消息/](https://www.geeksforgeeks.org/how-to-append-an-text-message-when-an-input-field-is-modified-in-jquery/)

在本文中，我们将看到当 jQuery 中的输入字段发生变化时，如何在文本消息中追加一个元素。要在输入字段更改时用文本消息追加元素，可以使用 [change()](https://www.geeksforgeeks.org/jquery-change-with-examples/) 和 appendTo()方法。[变化()方法](https://www.geeksforgeeks.org/jquery-change-with-examples/)用于检测输入字段值的变化。该方法仅适用于“<输入>、<文本区>和<选择>元素。[追加()方法](https://www.geeksforgeeks.org/jquery-appendto-with-examples/)用于追加元素。

**语法:**

```html
$($selector).change(function() { })
```

这里，我们首先使用 change()方法检测输入字段的变化，并使用 appendTo()方法显示消息。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to append an element with a text message
        when an input field is changed in jQuery?
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <script>
        $(document).ready(function () {
            $("#textInput").change(function () {
                $("<p>Input text has changed.</p>")
                .appendTo("body");
            });
        });
    </script>

    <style>
        body {
            text-align: center;
        }

        h1 {
            color: green;
        }

        .clickable_ele {
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h3>
        How to append an element with a text message
        <br>when an input field is changed in jQuery?
    </h3>

    <form action="#">
        <input id="textInput" type="text" 
            value="GeeksforGeeks">
    </form>
</body>

</html>
```

**输出:**

![](img/d86e37b289ba1fdca9839b2554dbe20a.png)