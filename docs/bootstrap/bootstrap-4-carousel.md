# 引导 4 |转盘

> 原文:[https://www.geeksforgeeks.org/bootstrap-4-carousel/](https://www.geeksforgeeks.org/bootstrap-4-carousel/)

引导转盘用于为网页创建图像幻灯片，使其看起来更有吸引力。可以使用 **bootstrap.js** 或 **bootstrap.min.js** 将其包含在网页中。在 Internet Explorer 中不正确支持旋转木马，这是因为它们使用 CSS3 过渡和动画来实现幻灯片效果。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Carousel</title>

    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">

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
  /* Make the image fully responsive */
  .carousel-inner img {
      width: 100%;
      height: 100%;
  }
  </style>
</head>

<body>
    <div id="GFG" class="carousel slide" data-ride="carousel">

    <!-- Indicators -->
    <ul class="carousel-indicators">
        <li data-target="#GFG" data-slide-to="0" class="active"></li>
        <li data-target="#GFG" data-slide-to="1"></li>
        <li data-target="#GFG" data-slide-to="2"></li>
        <li data-target="#GFG" data-slide-to="3"></li>
    </ul>

    <!-- The slideshow -->
    <div class="carousel-inner">
        <div class="carousel-item active">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190513180539/c113.png"
            alt="GFG" width="600" height="400">
        </div>

        <div class="carousel-item">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190513180541/c26.png"
            alt="GFG" width="600" height="600">
        </div>

        <div class="carousel-item">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190513180542/c32.png"
            alt="GFG" width="600" height="400">
        </div>

        <div class="carousel-item">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190513180543/c41.png"
            alt="GFG" width="600" height="400">
        </div>
    </div>

      <a class="carousel-control-prev" href="#GFG" data-slide="prev">
        <span class="carousel-control-prev-icon"></span>
      </a>
      <a class="carousel-control-next" href="#GFG" data-slide="next">
        <span class="carousel-control-next-icon"></span>
      </a>
    </div>
</body>

</html>                   
```

**输出:**

![](img/f9da48020807a1b517fa134103514775.png)

**给幻灯片添加标题:**使用*。旋转木马-标题*内的*。转盘-项目*类用于向幻灯片添加标题。
**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Carousel</title>

    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">

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
        /* Set the image size */
        .carousel-inner img {
            width: 100%;

        }
    </style>
</head>

<body>
    <div id="GFG" class="carousel slide" data-ride="carousel">

    <!-- Indicators -->
    <ul class="carousel-indicators">
        <li data-target="#GFG" data-slide-to="0" class="active"></li>
        <li data-target="#GFG" data-slide-to="1"></li>
        <li data-target="#GFG" data-slide-to="2"></li>
    </ul>

    <!-- The slideshow -->
    <div class="carousel-inner">
        <div class="carousel-item active">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190513180539/c113.png"
            alt="GFG" width="600" height="400">

            <div class="carousel-caption">
                <h3 class="text-warning">
                    GeeksforGeeks: Interview Preparation Caption
                </h3>
            </div>  
        </div>

        <div class="carousel-item">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190513180542/c32.png"
            alt="GFG" width="600" height="400">

            <div class="carousel-caption">
                <h3 class="text-warning">
                    GeeksforGeeks: Geeks Classes Caption
                </h3>
            </div>
        </div>

        <div class="carousel-item">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190513180543/c41.png"
            alt="GFG" width="600" height="400">

            <div class="carousel-caption">
                <h3 class="text-warning">
                    GeeksforGeeks: Geeks Classes Caption
                </h3>
            </div>
        </div>
    </div>

    <a class="carousel-control-prev" href="#GFG" data-slide="prev">
        <span class="carousel-control-prev-icon"></span>
    </a>
    <a class="carousel-control-next" href="#GFG" data-slide="next">
        <span class="carousel-control-next-icon"></span>
    </a>
    </div>
</body>

</html>                               
```

**输出:**

![](img/d8feccccd40a896c42000e384f045a7b.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队