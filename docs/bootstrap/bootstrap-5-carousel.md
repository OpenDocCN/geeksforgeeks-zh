# 引导 5 |转盘

> 原文:[https://www.geeksforgeeks.org/bootstrap-5-carousel/](https://www.geeksforgeeks.org/bootstrap-5-carousel/)

Bootstrap 5 提供了 Carousel，这是一个循环播放元素的幻灯片组件。可以使用 **bootstrap.js** 或 **bootstrap.min.js** 将其包含在网页中。在 Internet Explorer 中不正确支持旋转木马，这是因为它们使用 CSS3 过渡和动画来实现幻灯片效果。它是用 CSS 3D 转换和一点 JavaScript 构建的。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            Bootstrap 5 | Carousel
        </title>

        <!-- Load Bootstrap -->
        <link rel="stylesheet"
              href=
"https://stackpath.bootstrapcdn.com/bootstrap/5.0.0-alpha1/css/bootstrap.min.css"
              integrity=
"sha384-r4NyP46KrjDleawBgD5tp8Y7UzmLA05oM1iAEQ17CSuDqnUK2+k9luXQOfXJCJ4I" 
              crossorigin="anonymous" />
        <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" 
                integrity=
"sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" 
                crossorigin="anonymous">
      </script>
        <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/5.0.0-alpha1/js/bootstrap.min.js" 
                integrity=
"sha384-oesi62hOLfzrys4LxRF63OJCXdXDipiYWBnvTl9Y9/TRlw5xlKIEHpNyvvDShgf/" 
                crossorigin="anonymous">
      </script>
    </head>

    <style>
        // Customizing the carousel for white background
        .carousel-indicators .active {
            background-color: green;
        }

        .carousel-indicators li {
            background-color: burlywood;
        }
    </style>

    <body style="text-align: center;">
        <div class="container mt-3">
            <h1 style="color: green;">
                GeeksforGeeks
            </h1>

            <div id="GFG"
                 class="carousel slide" 
                 data-ride="carousel">
                <!-- Indicators -->
                <ul class="carousel-indicators">
                    <li data-target="#GFG" 
                        data-slide-to="0"
                        class="active"></li>
                    <li data-target="#GFG" 
                        data-slide-to="1"></li>
                    <li data-target="#GFG" 
                        data-slide-to="2"></li>
                </ul>

                <!-- The slideshow -->
                <div class="carousel-inner">
                    <div class="carousel-item active">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png" 
                             alt="GFG" />
                    </div>

                    <div class="carousel-item">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234528/colorize1.png"
                             alt="GFG" />
                    </div>

                    <div class="carousel-item">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234815/colorize2.png" 
                             alt="GFG" />
                    </div>
                </div>

                <a class="carousel-control-prev" 
                   href="#GFG" 
                   data-slide="prev">
                    <span class="carousel-control-prev-icon">
                  </span>
                </a>
                <a class="carousel-control-next"
                   href="#GFG"
                   data-slide="next">
                    <span class="carousel-control-next-icon">
                  </span>
                </a>
            </div>
        </div>
    </body>
</html>
```

**输出:**

![](img/e7f8172cc460563042e3c8e598247909.png)

**给幻灯片添加标题:**使用*。旋转木马-标题*内的*。转盘-项目*类用于向幻灯片添加标题。
**例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
            Bootstrap 5 | Carousel
        </title>

        <!-- Load Bootstrap -->
        <link rel="stylesheet" 
              href=
"https://stackpath.bootstrapcdn.com/bootstrap/5.0.0-alpha1/css/bootstrap.min.css" 
              integrity=
"sha384-r4NyP46KrjDleawBgD5tp8Y7UzmLA05oM1iAEQ17CSuDqnUK2+k9luXQOfXJCJ4I" 
              crossorigin="anonymous" />
        <script src=
"https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" 
                integrity=
"sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" 
                crossorigin="anonymous">
      </script>
        <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/5.0.0-alpha1/js/bootstrap.min.js" 
                integrity=
"sha384-oesi62hOLfzrys4LxRF63OJCXdXDipiYWBnvTl9Y9/TRlw5xlKIEHpNyvvDShgf/"
                crossorigin="anonymous">
      </script>
    </head>

    <style>
        // Customizing the carousel for white background
        .carousel-indicators .active {
            background-color: green;
        }

        .carousel-indicators li {
            background-color: burlywood;
        }
    </style>

    <body style="text-align: center;">
        <div class="container mt-3">
            <h1 style="color: green;">
                GeeksforGeeks
            </h1>

            <div id="GFG"
                 class="carousel slide" 
                 data-ride="carousel">
                <!-- Indicators -->
                <ul class="carousel-indicators">
                    <li data-target="#GFG" 
                        data-slide-to="0" 
                        class="active"></li>
                    <li data-target="#GFG"
                        data-slide-to="1"></li>
                    <li data-target="#GFG" 
                        data-slide-to="2"></li>
                </ul>

                <!-- The slideshow -->
                <div class="carousel-inner">
                    <div class="carousel-item active">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png"
                             alt="GFG" />
                        <div class="carousel-caption">
                            <h3 class="text-warning">
                                Image 1
                            </h3>
                        </div>
                    </div>

                    <div class="carousel-item">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234528/colorize1.png" 
                             alt="GFG" />
                        <div class="carousel-caption">
                            <h3 class="text-warning">
                                Image 2
                            </h3>
                        </div>
                    </div>

                    <div class="carousel-item">
                        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190918234815/colorize2.png" 
                             alt="GFG" />

                        <div class="carousel-caption">
                            <h3 class="text-warning">
                                Image 3
                            </h3>
                        </div>
                    </div>
                </div>

                <a class="carousel-control-prev"
                   href="#GFG" 
                   data-slide="prev">
                    <span class="carousel-control-prev-icon">
                  </span>
                </a>
                <a class="carousel-control-next" 
                   href="#GFG" 
                   data-slide="next">
                    <span class="carousel-control-next-icon">
                  </span>
                </a>
            </div>
        </div>
    </body>
</html>
```

**输出:**

![](img/1e97417c7dbeffaebf45d8296a04dca4.png)