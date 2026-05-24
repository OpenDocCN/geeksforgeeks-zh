# 如何在 Bootstrap 中指定方格网图片系统的长宽？

> 原文:[https://www . geesforgeks . org/how-specify-length-width-of-square-grid-picture-in-system-bootstrap/](https://www.geeksforgeeks.org/how-specify-length-and-width-of-square-grid-picture-system-in-bootstrap/)

方形网格图片的长度和宽度可以通过传统的 CSS 方法来指定，这种方法可以通过样式标签或使用链接标签轻松地结合到我们的 HTML 代码中。说到 Bootstrap，它提供了一种更简单、更有效的方法来以更少的工作量执行相同的任务。要在 Bootstrap 中指定正方形网格图片的长度和宽度，您需要 [Bootstrap 网格系统](https://www.geeksforgeeks.org/bootstrap-4-grid-system/)的基本概念。

Bootstrap 中有五个类可以改变长度和宽度，使用这个基本概念，您可以轻松地增加或减少网格列中任何图像的长度。

*   。上校
*   。S7-1200 可编程控制器
*   。col-md-
*   。col-lg-
*   。col-xl-

**例 1:** 这里你会看到三个网格宽度相同的图像，但是如果屏幕变小，那么第三个网格会改变行，变得比其他两个更宽。
T3】例:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Bootstrap Grid System</title>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" 
href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>

    <style>
        .col {
            text-align: center;
            border: 1px solid black;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="row">
            <div class="col">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190710120839/download14.png" />
            </div>
            <div class="col">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190710121155/03.png">
            </div>
            <div class="col">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190710121314/images2.png">
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/38cdddfd40f6184f97e1bbde71b33454.png)

**示例 2:** 在这里，您将看到包含图像的网格的三种不同宽度。
T3】例:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Bootstrap Grid System</title>
    <meta charset="utf-8">
    <meta name="viewport" 
          content="width=device-width, initial-scale=1">
    <link rel="stylesheet" 
href="https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <script src=
          "https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script src=
 "https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
       "https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>
    <style>
        .col {
            text-align: center;
            border: 5px solid black;
        }

        div {
            border: 1px solid black;
        }
    </style>
</head>

<body>
    <div class="container">
        <br>
        <center>
            <div class="row">
                <div class="col-sm-3">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190710120839/download14.png" />
                </div>
                <div class="col-sm-6">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190710123529/GeeksforGeeksLogoHeader1.png">
                </div>
                <div class="col-sm-3">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190710121314/images2.png">
                </div>
            </div>
        </center>
    </div>
</body>

</html>
```

**输出:**
![](img/a4e35a7ff8b4d294fd4759ca506760c8.png)