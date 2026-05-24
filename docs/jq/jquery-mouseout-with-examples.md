# jQuery | mouseout()带示例

> 原文:[https://www . geesforgeks . org/jquery-mouse out-with-examples/](https://www.geeksforgeeks.org/jquery-mouseout-with-examples/)

mouseout()方法是 jQuery 中的一个内置方法，当鼠标指针从所选元素移出时使用。
**语法:**

```html
$(selector).mouseout(function)
```

**参数:**该方法接受单参数*功能*，可选。此参数用于指定调用 mouseout 事件时要运行的函数。

**返回值:**该方法返回有变化的选中元素。

下面的例子说明了 jQuery 中的 mouseout()方法:

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>The mouseover Method</title>
        <script src=
        "https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>

        <!-- jQuery code to show the working of this method -->
        <script>
            $(document).ready(function() {
                $("p").mouseover(function() {
                    $("p").css("background-color", "lightgreen");
                });
                $("p").mouseout(function() {
                    $("p").css("background-color", "lightgray");
                });
            });
        </script>
        <style>
            body {
                width: 420px;
                padding: 40px;
                height: 30px;
                border: 2px solid green;
                font-weight: bold;
                font-size: 20px;
            }
        </style>
    </head>
    <body>
        <!-- move over this text to see the change -->
        <p>Move the mouse pointer over this paragraph.</p>
    </body>
</html>
```

**输出:**
鼠标移至段落:
![](img/d8b5fda767c914553f5e859084503524.png)
鼠标移出段落:
![](img/a77afda0ddab4f0ea9593a314f141655.png)