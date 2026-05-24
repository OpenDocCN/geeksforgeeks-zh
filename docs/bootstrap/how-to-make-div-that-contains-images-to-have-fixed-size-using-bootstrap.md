# 如何使用 Bootstrap 制作包含固定大小图像的 div？

> 原文:[https://www . geesforgeks . org/如何使用引导程序制作包含固定大小图像的 div/](https://www.geeksforgeeks.org/how-to-make-div-that-contains-images-to-have-fixed-size-using-bootstrap/)

在本文中，我们将看到如何制作一个 *div* ，它将包含具有固定大小的图像。当设计一个网页来展示某一类型的产品时，这是非常有用的。我们将使用 bootstrap 来实现上述问题的解决方案。

**引导 CDN 链路：** [https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css](https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css)

**例:**现在我们借助一个例子来看看。

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
    integrity=
"sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
    crossorigin="anonymous">

    <style>
        .album {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .imgContainer {
            max-width: 400px;
            max-height: 700px;
            overflow: hidden;
        }

        .imgContainer img {
            width: 100%;
            min-height: 100%;
        }
    </style>
</head>

<body>
    <div class="album">
        <div class="imgContainer">
            <div class="row mt-3">
                <div class="col px-2">
                    <img src="1.jpeg">
                </div>
                <div class="col px-2">
                    <img src="1.jpeg">
                </div>
            </div>

            <div class="row mt-3">
                <div class="col px-2">
                    <img src="2.jpeg">
                </div>
                <div class="col px-2">
                    <img src="2.jpeg">
                </div>
            </div>

            <div class="row mt-3">
                <div class="col px-2">
                    <img src="3.jpeg">
                </div>
                <div class="col px-2">
                    <img src="3.jpeg">
                </div>
            </div>
        </div>
    </div>
</body>

</html>
```