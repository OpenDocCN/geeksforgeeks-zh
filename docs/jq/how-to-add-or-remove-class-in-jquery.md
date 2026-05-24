# 如何在 jQuery 中添加或删除类？

> 原文:[https://www . geesforgeks . org/如何在 jquery 中添加或删除类/](https://www.geeksforgeeks.org/how-to-add-or-remove-class-in-jquery/)

[**【AddClass()】**](https://www.geeksforgeeks.org/jquery-addclass-with-examples/)**或[**【remove Class()】**](https://www.geeksforgeeks.org/jquery-removeclass-with-examples/)**方法用于在需要添加到我们的网页时添加 CSS 类，当有一些事件监听器或创建某种效果时。****

****在本文中，让我们看看如何在 jQuery 中添加 CSS 类或移除 CSS 类。****

******语法:******

*   ******增加一个类:**

    ```html
    $('selector').addClass(class_name);
    ```**** 
*   ******移除一个类:**

    ```html
    $('selector').removeClass(class_name);
    ```**** 

******示例:**以下示例添加了一个类，当单击“添加类”按钮时，该类使背景颜色变为黑色，当单击“删除类”按钮时，该类也被删除。****

## ****超文本标记语言****

```html
**<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible"
        content="IE=edge">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <!-- Including jQuery  -->
    <script src=
        "https://code.jquery.com/jquery-3.6.0.min.js" 
        integrity=
"sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4="
        crossorigin="anonymous">
    </script>

    <style>
        h1 {
            color: #006600;
        }

        button {
            color: white;
            background-color: #006600;
            width: auto;
            height: 30px;
        }

        body {
            text-align: center;
        }

        div {
            margin: 10px;
            height: 150px;
            width: 150px;
            position: relative;
            text-align: center;
            display: flex;
            left: 215px;
        }

        .bg-black {
            background-color: black;
        }
    </style>
</head>

<body>
    <h1>Geeks For Geeks</h1>

    <button id="btnadd"> ADD CLASS </button>
    <button id="btnremove"> REMOVE CLASS </button>

    <div id="GFG_IMAGE">

        <!-- Image added using img tag 
            with src attribute -->
        <img src=
"https://write.geeksforgeeks.org/static/media/Group%20210.08204759.svg"
            height='150px' width='150px'>
        <img>
    </div>

    <script>
        $(document).ready(function() {
            $('#btnadd').click(function() {
                $('img').addClass('bg-black');
            });
            $('#btnremove').click(function() {
                $('img').removeClass('bg-black');
            });
        });
    </script>
</body>

</html>**
```

******输出:******

****![](img/b589d32a0428f4680e6b78131e817eee.png)

添加类和删除类****