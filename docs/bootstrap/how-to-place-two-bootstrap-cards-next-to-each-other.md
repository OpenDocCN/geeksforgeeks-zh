# 如何将两张自举卡并排放置？

> 原文:[https://www . geeksforgeeks . org/how-to-place-two-bootstrap-cards-挨着彼此/](https://www.geeksforgeeks.org/how-to-place-two-bootstrap-cards-next-to-each-other/)

Bootstrap 是最流行的、免费的、开源的 HTML、CSS 框架，用来制作一个有响应的网站，让它们变得漂亮。它提供了各种各样的类，可以用来使网站变得漂亮。它还提供了创建卡片的类。

**卡片:**卡片是一种灵活且可扩展的内容容器。它包括页眉和页脚选项、各种各样的内容、上下文背景颜色和强大的显示选项。

**语法:**

```html
<div class="card" style="width: 20rem">
    <img class="card-img-top" src="..." 
            alt="Card image cap">
    <div class="card-block">
        <h4 class="card-title">Card title</h4>
        <p class="card-text">
            Some quick example text to build
            on the card title and make up the
            bulk of the card's content.
        </p>
        <a href="#" class="btn btn-primary">
            Go somewhere
        </a>
    </div>
</div>
```

**示例 1:** 本示例使用 bootstrap 的网格制作一行并将其划分。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, 
        initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
        integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
        crossorigin="anonymous">

    <link rel="stylesheet" href=
"https://use.fontawesome.com/releases/v5.4.1/css/all.css"
        integrity=
"sha384-5sAR7xN1Nv6T6+dT2mhtzEpVJvfS3NScPQTrOxhwjIuvcA67KV2R5Jz6kr4abQsz"
         crossorigin="anonymous">

    <title>
        Place two bootstrap cards next to each other
    </title>
</head>

<body>
    <div class="container">
        <div class="row">
            <div class="col-lg-6 mb-4">
                <div class="card">
                    <img class="card-img-top" src="" alt="">

                    <div class="card-body">
                        <h5 class="card-title">Card title</h5>
                        <p class="card-text">
                            Some quick example text to build on 
                            the card title and make up the bulk 
                            of the card's content.
                        </p>

                        <a href="#" class="btn btn-outline-primary btn-sm">
                            Card link
                        </a>
                        <a href="#" class="btn btn-outline-secondary btn-sm">
                            <i class="far fa-heart"></i></a>
                    </div>
                </div>
            </div>
            <div class="col-lg-6 mb-4">
                <div class="card">
                    <img class="card-img-top" src="" alt="">

                    <div class="card-body">
                        <h5 class="card-title">Card title</h5>
                        <p class="card-text">
                            Some quick example text to build on the 
                            card title and make up the bulk of the 
                            card's content.
                        </p>

                        <a href="#" class="btn btn-outline-primary btn-sm">
                            Card link
                        </a>
                        <a href="#" class="btn btn-outline-secondary btn-sm">
                            <i class="far fa-heart"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
            integrity=
"sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
            crossorigin="anonymous">
    </script>

    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
            integrity=
"sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
            crossorigin="anonymous">
    </script>

    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
            integrity=
"sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
            crossorigin="anonymous">
    </script>
</body>

</html>
```

**输出:**
![](img/ab37e9dce3553f8183acc7b44a439c19.png)

**示例 2:** 要创建宽度和高度相等的牌，还可以使用一类 Bootstrap 牌组。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1,shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
            integrity=
"sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
         crossorigin="anonymous">

    <link rel="stylesheet" href=
"https://use.fontawesome.com/releases/v5.4.1/css/all.css"
            integrity=
"sha384-5sAR7xN1Nv6T6+dT2mhtzEpVJvfS3NScPQTrOxhwjIuvcA67KV2R5Jz6kr4abQsz"
             crossorigin="anonymous">

    <title>
        Place two bootstrap cards 
        next to each other
    </title>
</head>

<body>
    <div class="card-deck">
        <div class="card">
            <img class="card-img-top" src="" alt="Card image cap">
            <div class="card-block">
                <h4 class="card-title">Card title</h4>
                <p class="card-text">
                    This is a longer card with supporting 
                    text below as a natural lead-in to 
                    additional content. This content
                    is a little bit longer.
                </p>

                <p class="card-text">
                    <small class="text-muted">
                        Last updated 3 mins ago
                    </small>
                </p>
            </div>
        </div>

        <div class="card">
            <img class="card-img-top" src="">
            <div class="card-block">
                <h4 class="card-title">Card title</h4>
                <p class="card-text">
                    This card has supporting text below 
                    as a natural lead-in to additional 
                    content.
                </p>

                <p class="card-text">
                    <small class="text-muted">
                        Last updated 3 mins ago
                    </small>
                </p>
            </div>
        </div>

        <div class="card">
            <img class="card-img-top" src="">
            <div class="card-block">
                <h4 class="card-title">Card title</h4>
                <p class="card-text">
                    This is a wider card with supporting 
                    text below as a natural lead-in to 
                    additional content. This card has 
                    even longer content than the first 
                    to show that equal height action.
                </p>

                <p class="card-text">
                    <small class="text-muted">
                        Last updated 3 mins ago
                    </small>
                </p>
            </div>
        </div>
    </div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
        integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
        crossorigin="anonymous">
    </script>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
        integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
        crossorigin="anonymous">
    </script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
        integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
        crossorigin="anonymous">
    </script>
</body>

</html>
```

**输出:**
![](img/1b45de2f4a2b238e79af8e15c1a66590.png)