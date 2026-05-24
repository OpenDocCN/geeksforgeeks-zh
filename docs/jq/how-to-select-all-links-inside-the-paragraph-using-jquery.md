# 如何使用 jQuery 选择段落内部的所有链接？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-select-all-links-inside-the-paragraph-using-jquery/) 选择段落内的所有链接

在本文中，我们将看到如何使用 jQuery 编写代码来选择段落中的所有链接。要选择段落元素内的所有链接，我们使用 [**父代后代选择器**](https://www.geeksforgeeks.org/jquery-parent-descendant-selector/) 。该选择器用于选择特定(父)元素的后代元素。

**语法:**

```html
$("parent descendant")
```

**方法:**这里，我们已经在段落元素内部创建了链接和内容。之后，我们使用**$(“p a”)选择器**选择段落元素内的所有链接，并使用 [css()方法](https://www.geeksforgeeks.org/jquery-css-method/)更改其样式。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        jQuery code to select all 
        links inside the paragraph
    </title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
    </script>

    <style>
        body {
            text-align: center;
            font-size: 30px;
        }

        button {
            background-color: green;
            color: white;
            border: none;
            font-size: 24px;
            border-radius: 5px;
            padding: 15px 32px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
        }

        a {
            text-decoration: none;
        }
    </style>

    <script>
        $(document).ready(function() {
            $("button").click(function() {
                $("p a").css({
                    color: "white",
                    background: "green"
                });
            });
        });
    </script>
</head>

<body>
    <h1 style="color:green">
        GeeksforGeeks
    </h1>

    <h3>
        jQuery code to select all 
        links inside the paragraph
    </h3>

    <p>
        <a href="#">GeeksforGeeks</a> is a 
        computer science <br>portal where 
        you can learn <a href="#">HTML</a>,
        <a href="#">CSS</a>, <br><a href="#">
        JavaScript</a>, etc.
    </p>

    <button>
        Click Here
    </button>
</body>

</html>
```

**输出:**

![](img/df3ce7e3673e7c8d38b5f30c41d4bda2.png)