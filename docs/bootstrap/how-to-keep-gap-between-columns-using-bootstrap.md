# 如何使用 Bootstrap 保持列间间隙？

> 原文:[https://www . geeksforgeeks . org/如何使用自举保持列间距/](https://www.geeksforgeeks.org/how-to-keep-gap-between-columns-using-bootstrap/)

我们可以通过使用普通的 CSS 来保持列之间的间隙，但是这里我们将使用 Bootstrap 框架。在本文中，我们将通过以下方法来测量柱之间的间隙。

**使用“div”标签:**只需在两个“div”标签之间添加一个带有**填充**的“div”，即可给出“div”之间的间距。

**示例:**

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8" />
        <meta
            name="viewport"
            content="width=device-width,
                     initial-scale=1, 
                     shrink-to-fit=no"/>

        <!-- Bootstrap CSS -->
        <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
            integrity=
"sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
            crossorigin="anonymous" />

        <style media="screen">
            .a {
                padding: 50px;
            }
        </style>
    </head>

    <body>
        <div class="row">
            <div class="col-4 bg-success a">
                One of two columns
            </div>
            <div class="col-4"><!--extra div--></div>
            <div class="col-4 bg-danger a">
                One of two columns
            </div>
        </div>
    </body>
</html>
```

**输出:**

*   **没有额外“div”标签的图像:**

    ![](img/3aa801b46d2e38282b828a32ceb9e067.png)

*   **带有额外“div”标签的图像:**

    ![](img/ef788bc3afdefaa0deaccd1884ce101a.png)

**使用列偏移量的方法:**偏移量类用于增加列的左边距。类 **col-md-offset-2** 将 **col-md-3** 移动 3 列。

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8" />
        <meta name="viewport" 
              content="width=device-width, 
                       initial-scale=1,
                       shrink-to-fit=no" />

        <!-- Bootstrap CSS -->
        <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" 
              integrity=
"sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" 
              crossorigin="anonymous" />
        <style media="screen">
            .a {
                padding: 50px;
            }
        </style>
    </head>
    <body>
        <!--using offset-->
        <div class="row">
            <div class="col-md-5 bg-success a">geeksforgeeks</div>
            <div class="col-md-5 bg-danger offset-2 a">
                geeksforgeeks
            </div>
        </div>
    </body>
</html>
```

**输出:**该输出可能与给定的输出图像不匹配，因为输出的屏幕尺寸较小。

1.  **无偏移图像:**

    ![](img/f38fa4d33079cf0878edd5469c33e8fd.png)

2.  **偏移图像:**

    ![](img/19fb0f9eb2c492d835d671e57c3a8538.png)