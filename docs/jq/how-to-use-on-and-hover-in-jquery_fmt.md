# 如何在 jQuery 中使用 on() 和 hover()

> 原文: [https://www.geeksforgeeks.org/how-to-use-on-and-hover-in-jquery/](https://www.geeksforgeeks.org/how-to-use-on-and-hover-in-jquery/)

## jQuery.on() 方法

[`on()`](https://www.geeksforgeeks.org/jquery-on-with-examples/) 方法用于将事件监听器附加到元素。这个方法相当于普通 JavaScript 中的 `addEventListener`。

**语法:**

```html
$(element).on(event, childSelector, data, function)
```

**参数**

*   `event`: 指定要附加的事件（点击、提交等）。
*   `childSelector`: 是可选参数，它指定给定事件处理程序可以使用的特定子元素。
*   `data`: 指定随函数传递的可选数据。
*   `function`: 指定触发附加事件时要运行的函数。

**示例:**

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Adding jQuery Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.0/jquery.min.js"></script>
    <style>
        /* Adding basic styling */
        div {
            background-color: green;
            width: 100px;
            height: 100px;
            color: #fff;
            text-align: center;
        }
    </style>
</head>
<body>
    <div>Normal</div>
    <script>
        $('div').on('click', function () {
            // Changing the content
            $(this).html('Clicked!');
        });
    </script>
</body>
</html>
```

**输出:**

*   **点击 div 元素前:**
    ![](img/f79123127d85c04185c4259257fb2758.png)
*   **点击 div 元素后:**
    ![](img/2cee073abeb5bb6721009139154ed430.png)

## jQuery.hover() 方法

[`hover()`](https://www.geeksforgeeks.org/jquery-on-with-examples/) 方法用于在鼠标悬停在和鼠标退出条件下指定元素的样式。它以两个函数作为参数:

*   **鼠标移入函数:** 鼠标进入元素时触发。
*   **鼠标移出函数:** 鼠标离开元素时触发。

您可以在这些函数中指定多种样式。

**语法:**

```html
$(element).hover(mouseoverFunction, mouseoutFunction)
```

**示例:**

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Adding jQuery Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.0/jquery.min.js"></script>
    <style>
        /* Adding basic styling */
        div {
            background-color: green;
            width: 100px;
            height: 100px;
            color: #fff;
            text-align: center;
        }
    </style>
</head>
<body>
    <div>Normal</div>
    <script>
        $('div').hover(function () { // mouse-in
            $(this).css("background-color", "blue");
            $(this).html('Hovered!');
        },
            function () { // mouse-out
                $(this).css("background-color", "green");
                $(this).html('Normal');
            }
        )
    </script>
</body>
</html>
```

**输出:**

*   **鼠标移过前:**
    ![](img/f79123127d85c04185c4259257fb2758.png)
*   **鼠标移过后:**
    ![](img/233dfca2f3ad5fee6caf5c6a120e94b6.png)