# 如何在运行时更改引导转盘间隔？

> 原文:[https://www . geesforgeks . org/how-change-bootstrap-carousel-interval-at-runtime/](https://www.geeksforgeeks.org/how-to-change-bootstrap-carousel-interval-at-runtime/)

我们将学习如何使用 bootstrap 在运行时更改转盘间隔。在这个例子中，我们将讨论多种方法。Bootstrap carousel 是一个幻灯片显示，用于在用 JavaScript、CSS 和动画构建的多个内容中滑动。它可以处理文本、图像和自定义标记。它还包括用于控制其运动的前一个和下一个控制和指示器。

**方法 1:** 我们可以通过使用每个轮播项目的数据间隔属性来控制动画。给出的例子是理解这个概念的最好例子。默认情况下，数据间隔属性用于设置两个转盘项目之间的间隔时间，其值为 3000 毫秒。

## 超文本标记语言

```html
<html>

<head>
    <!-- CSS only -->
    <link href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
          rel="stylesheet" />
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>

    <title>geeksforgeeks</title>
</head>

<body style="width:70%;">
    <div id="carouselExampleIndicators"
         class="carousel slide" data-ride="carousel"
         data-interval="100">
        <ol class="carousel-indicators">
            <li data-target="#carouselExampleIndicators"
                data-slide-to="0" class="active"></li>
            <li data-target="#carouselExampleIndicators"
                data-slide-to="1"></li>
            <li data-target="#carouselExampleIndicators"
                data-slide-to="2"></li>
        </ol>
        <div class="carousel-inner">
            <div class="carousel-item active">
                <img class="d-block w-100" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190802021607/geeks14.png"
                     alt="Second slide">
            </div>
            <div class="carousel-item">
                <img class="d-block w-100" src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210223134821/gfg3.jpg"
                     alt="First slide">
            </div>
            <div class="carousel-item" id="image2">
                <img class="d-block w-100" src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200x200-min.png"
                     alt="Third slide">
            </div>
        </div>
        <a class="carousel-control-prev"
           href="#carouselExampleIndicators"
           role="button" data-slide="prev">
            <span class="carousel-control-prev-icon"
                  aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
        </a>
        <a class="carousel-control-next"
           href="#carouselExampleIndicators"
           role="button" data-slide="next">
            <span class="carousel-control-next-icon"
                  aria-hidden="true"></span>
            <span class="sr-only">Next</span>
        </a>
    </div>
</body>

</html>
```

**输出:**

![](img/63a071d0bcabfcb6bac877491ca01011.png)

**方法 2:** 在这种方法中，我们将使用 bootstrap API 方法更改动画间隔。它将一个参数作为单位毫秒的间隔(即 1s =毫秒)。我们分配的时间间隔将在运行时改变所有转盘项目之间的动画时间。转盘功能中的数据间隔用于设置两张图像幻灯片之间的时间。

**语法**

```html
$('.carousel').carousel({
    interval: time in millisecond
});
```

## 超文本标记语言

```html
<html>

<head>
    <!-- CSS only -->
    <link href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
          rel="stylesheet" />
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>

    <title>geeksforgeeks</title>
</head>

<body style="width:70%;">
    <div id="carouselExampleIndicators"
         class="carousel slide" data-ride="carousel">
        <ol class="carousel-indicators">
            <li data-target="#carouselExampleIndicators"
                data-slide-to="0" class="active"></li>
            <li data-target="#carouselExampleIndicators"
                data-slide-to="1"></li>
            <li data-target="#carouselExampleIndicators"
                data-slide-to="2"></li>
        </ol>
        <div class="carousel-inner">
            <div class="carousel-item active">
                <img class="d-block w-100" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190802021607/geeks14.png"
                     alt="Second slide">
            </div>
            <div class="carousel-item">
                <img class="d-block w-100" src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210223134821/gfg3.jpg"
                     alt="First slide">
            </div>
            <div class="carousel-item" id="image2">
                <img class="d-block w-100" src=
   "https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200x200-min.png"
                     alt="Third slide">
            </div>
        </div>
        <a class="carousel-control-prev"
           href="#carouselExampleIndicators"
           role="button" data-slide="prev">
            <span class="carousel-control-prev-icon"
                  aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
        </a>
        <a class="carousel-control-next"
           href="#carouselExampleIndicators"
           role="button" data-slide="next">
            <span class="carousel-control-next-icon"
                  aria-hidden="true"></span>
            <span class="sr-only">Next</span>
        </a>
    </div>

    <script>
        // Handle Bootstrap carousel slide event
        $('.carousel').carousel({
            interval: 100
        });
    </script>
</body>

</html>
```

**输出:**

![](img/63a071d0bcabfcb6bac877491ca01011.png)

**方法 3:** 我们可以使用数据属性和 javascript 设置数据间隔。这种方法和上面两种方法一样简单。在这种方法中，我们将选择 carousel 类 div，并使用 attr()方法更改属性。attr()方法是一个 jquery 方法，它设置或返回所选元素的属性和值。当此方法用于返回值时，它返回第一个匹配元素的值，如果它用于设置属性值，则它设置一个或多个属性的属性。

**语法:**

```html
 $('.carousel').attr(
    "data-interval","interval that you want to set (in milisec)
");
```

## 超文本标记语言

```html
<html>
    <head>
        <!-- CSS only -->
        <link href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
              rel="stylesheet" />
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
        </script>
        <script src=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
        </script>

        <title>geeksforgeeks</title>
    </head>
    <body style="width: 70%;">
        <div id="carouselExampleIndicators"
             class="carousel slide"
             data-ride="carousel">
            <ol class="carousel-indicators">
                <li data-target="#carouselExampleIndicators"
                    data-slide-to="0"
                    class="active">
                </li>
                <li data-target="#carouselExampleIndicators"
                    data-slide-to="1">
                </li>
                <li data-target="#carouselExampleIndicators"
                    data-slide-to="2">
                </li>
            </ol>
            <div class="carousel-inner">
                <div class="carousel-item active">
                    <img class="d-block w-100"
                         src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190802021607/geeks14.png"
                         alt="Second slide" />
                </div>
                <div class="carousel-item">
                    <img class="d-block w-100"
                         src=
"https://yt3.ggpht.com/ytc/AAUvwnjJqZG9PvGfC3GoV27UlohMeBLxyUdhs9hUbc-Agw=s900-c-k-c0x00ffffff-no-rj"
                         alt="First slide" />
                </div>
                <div class="carousel-item" id="image2">
                    <img class="d-block w-100"
                         src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200x200-min.png"
                         alt="Third slide" />
                </div>
            </div>
            <a class="carousel-control-prev"
               href="#carouselExampleIndicators" role="button"
               data-slide="prev">
                <span class="carousel-control-prev-icon"
                      aria-hidden="true">
                </span>
                <span class="sr-only">Previous</span>
            </a>
            <a class="carousel-control-next"
               href="#carouselExampleIndicators"
               role="button" data-slide="next">
                <span class="carousel-control-next-icon"
                      aria-hidden="true"></span>
                <span class="sr-only">Next</span>
            </a>
        </div>
        <script>
            //handle Bootstrap carousel slide event
            $(".carousel").attr("data-interval", "100");
        </script>
    </body>
</html>
```

**输出**

![](img/63a071d0bcabfcb6bac877491ca01011.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队