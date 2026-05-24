# 为什么卡映像在 Bootstrap 4 中对映像使用数据-src(而不是 src)？

> 原文:[https://www . geesforgeks . org/why-card-images-use-data-src-not-src-for-image-in-bootstrap-4/](https://www.geeksforgeeks.org/why-card-images-use-data-src-not-src-for-image-in-bootstrap-4/)

Bootstrap 4 card images 使用图像标签中的 src 来提供要加载到给定图像标签中的位置，并使用 data-src 来提供 JavaScript 可以用来改善用户体验的附加信息。对于**数据-src** 和 **src** 标签，我们可以得出如下结论:
**src:**

*   如果要加载和显示特定图像，请使用。加载图像网址。

**数据-src:**

*   如果你想要一个可以包含 URL 的元数据(在任何标签上)，那么使用你想要选择的 data-src 或者任何 data-xxx。
*   data-*属性用于存储页面或应用程序专用的自定义数据。
*   data-*属性使我们能够在所有 HTML 元素中嵌入自定义数据属性。
*   然后，JavaScript 可以使用这些数据来创建更吸引人的用户体验。

**语法:**

*   使用 src 属性:

    ```html
    <img id="img1" src="abc.jpg">

    <script>
        var url = document.getElementById("img1").src;
    </script>
    ```

*   使用数据-src 属性:

    ```html
    <img id="img1" src="xyz.jpg" data-src="abc.jpg
    <script>
        var ele = document.getElementById("img1");

        // Switch the image to the URL specified in data-src
        ele.src = ele.dataset.src;
    </script>

    ```

下面的例子说明了上面的概念:

**示例:**下面的代码可以看到如何使用 **src** 属性提供到图像的链接，以及如何使用**数据-src** 向 JavaScript 提供附加信息，就像这里使用**数据-src** 属性中的一个来更改图像的原始 src 链接一样。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />

    <meta name="viewport"
        content="width=device-width, initial-scale=1.0" />

    <meta http-equiv="X-UA-Compatible"
        content="ie=edge" />

    <title>
        Why card images use data-src (not src)
        for image in Bootstrap 4 ?
    </title>

    <link rel="stylesheet"
        href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
        integrity=
"sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
        crossorigin="anonymous" />

    <script src=
"https://code.jquery.com/jquery-3.3.1.slim.min.js"
            integrity=
"sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"
            crossorigin="anonymous"></script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"
            integrity=
"sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49"
            crossorigin="anonymous"></script>

    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"
            integrity=
"sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy"
            crossorigin="anonymous">
    </script>

    <style>
        h1 {
            color: green;
        }
        .second {
            float: right;
            margin: 20px;
        }
        .first {
            float: left;
            margin: 20px;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <b>A Computer Science Portal for Geeks</b>
    </center>

    <div class="container">
        <div class="card first" style="width: 18rem;">
            <img class="card-img-top" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190506125816/avt.png"
                alt="Card image cap" />
            <div class="card-body">
                <h5 class="card-title">Courses</h5>
                <p class="card-text">
                    Attend the courses Increase
                    the probability
                </p>
                <a href="#" class="btn btn-primary">Attend</a>
            </div>
        </div>

        <!-- It loaded with JavaScript to allow
            lazy loading of images -->
        <div class="card second" style="width: 18rem;">
            <img id="img1" class="card-img-top"
                data-src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200121112744/logo11.png"
                style="height:295px;"
                src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190506125816/avt.png"
                alt="Card image cap" />

            <div class="card-body">
                <h5 class="card-title">Interview</h5>
                <p class="card-text">
                    Prepare your self for the Interview
                </p>
                <a href="#" class="btn btn-primary">Attend</a>
            </div>
        </div>
    </div>

    <script>
        var ele = document.getElementById("img1");

        // Switch the image to the URL
        // specified in data-src
        ele.src = ele.dataset.src;
    </script>
</body>

</html>
```

**输出:**
![](img/27d0b0f3cd6e797d7e06b591e9f0c74f.png)