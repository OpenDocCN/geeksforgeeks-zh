# jQuery 中提供效果的方法有哪些？

> 原文:[https://www . geeksforgeeks . org/jquery 中用于提供效果的方法是什么/](https://www.geeksforgeeks.org/what-are-the-methods-used-to-provide-effects-in-jquery/)

jQuery 中的效果通常用于向网页添加动画。jQuery 库有几种方法，我们可以用来为网页制作自定义动画。在本文中，我们将看到 jQuery 中用于制作动画的每一种方法。我们将讨论所有方法以及 jQuery 代码片段和输出。

**1。[动画()方法](https://www.geeksforgeeks.org/jquery-animate-with-examples/) :** 该方法用于制作带有一些选定 CSS 属性的自定义动画。例如，高度、宽度等可以用这种方法制作动画。

**示例:**在本例中，我们正在制作球体大小的动画。

## HTML

```html
<!DOCTYPE html>
<html>

<head>

    <!-- jQuery CDN link -->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js">
    </script>

    <title>Animate Method</title>
    <style>
        body {
            margin: 0px;
            padding: 0px;
            box-sizing: border-box;
        }

        .main {
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: rgb(41, 41, 41);
            flex-direction: column;
            height: 100vh;
        }

        #shape {
            height: 100px;
            width: 100px;
            background-color: yellow;
            border-radius: 100%;
        }
    </style>
</head>

<body>
    <div class="main">
        <div id="shape">
        </div>
    </div>

    <script>
        $(document).ready(function () {

            // On taking the mouse to the shape,
            // will increase the size of shape.
            $("#shape").mouseover(function () {
                $(this).animate({ 
                    height: "200px", 
                    width: "200px" 
                });
            });

            // On taking out the mouse from the shape,
            // will decrease the size of shape.
            $("#shape").mouseout(function () {
                $(this).animate({ 
                    height: "100px", 
                    width: "100px" 
                });
            });
        });
    </script>
</body>

</html>
```