# jQuery | mouseenter()带示例

> 原文:[https://www . geeksforgeeks . org/jquery-mouse enter-with-examples/](https://www.geeksforgeeks.org/jquery-mouseenter-with-examples/)

mouseenter()方法是 jQuery 中的一个内置方法，当鼠标指针移动到所选元素上时，该方法就会工作。

**语法:**

```html
$(selector).mouseenter(function)
```

**参数:**该方法接受单参数*功能*，可选。它用于指定调用 mouseenter 事件时要运行的函数。

**返回值:**该方法使用 mouseenter()方法所做的更改返回选定的元素。

下面的例子说明了 jQuery 中的 mouseenter()方法:

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>The mouseenter Method</title>
        <script src=
        "https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>

        <!-- jQuery code to show the working of this method -->
        <script>
            $(document).ready(function() {
                $("p").mouseenter(function() {
                    $("p").css("background-color", "green");
                });
            });
        </script>
        <style>
            body {
                width: 300px;
                padding: 40px;
                height: 30px;
                border: 2px solid green;
                font-weight: bold;
                font-size: 20px;
            }
        </style>
    </head>
    <body>
        <!-- move over this paragraph and see the change -->
        <p>Welcome to GeeksforGeeks!</p>
    </body>
</html>
```

**输出:**
在进入鼠标悬停段落前:
![](img/1d35bc5f59be1970cb38b7947df456dc.png)在进入鼠标悬停段落后:
![](img/153e9e9cbf39c9762fb7a9a3f9f961eb.png)

**相关文章:**

*   [jQuery | data()带示例](https://www.geeksforgeeks.org/jquery-data-with-examples/)
*   [jQuery | addBack()带示例](https://www.geeksforgeeks.org/jquery-addback-with-examples/)