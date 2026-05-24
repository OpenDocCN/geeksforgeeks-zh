# 如何在每张幻灯片中显示带有三个帖子的引导转盘？

> 原文:[https://www . geesforgeks . org/如何显示-引导-转盘-每张幻灯片有三个帖子/](https://www.geeksforgeeks.org/how-to-display-bootstrap-carousel-with-three-post-in-each-slide/)

一个**引导转盘**是一个幻灯片，用于旋转一系列内容。它是用 CSS 和 Javascript 构建的。它可以处理一系列照片、图像、文本等。它可以用作图像滑块，用于在网页的小空间内展示大量内容，因为它是根据动态演示的原理工作的。

**语法:**

```html
<div class="container"> Bootstrap image contents... <div>
```

**以下是创建引导转盘的步骤:**

1.  在头部包含引导 Javascript、CSS 和 JQuery 库文件，这些文件是预加载和预编译的

    ```html
    <link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css”>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js">
    <script src="https://netdna.bootstrapcdn.com/bootstrap/3.0.3/js/bootstrap.min.js">
    ```

2.  应用 CSS 来调整。使用下面的代码段旋转引导卡主体。

    ```html
    <style>
     .carousel {
     width:200px;
     height:200px;
     }
     <style>
    ```

3.  在主体部分中，使用下面的语法

    ```html
    <div id=”carousel-demo” class=”carousel slide” data-ride=”carousel”>
    ```

    创建一个带有转盘滑块的分部类
4.  在此步骤中，滑动图像在分割标签中定义如下。

    ```html
    <div class=”carousel-inner”>
    <div class=”item”>
    <img src=”..URL of image”>
    ```

5.  最后一步是使用如下的 carousel-control 类向幻灯片图像添加控件。

    ```html
    <a class="left carousel-control" href="#carousel-demo2" data-slide="prev">
        <span class="icon-prev"></span>
    </a>
    <a class="right carousel-control" href="#carousel-demo2" data-slide="next">
        <span class="icon-next"></span>
    </a>
    ```

**注意:**
我们根据转盘滑块内提供的图像数量重复第 4 步的次数，并精确重复第 3 步两次，以使用图像滑块*在引导卡中显示两个部分。旋转木马*

**示例 1:** 让我们实现上述方法，首先使用 HTML、CSS、带有图像滑块的 Js 创建 Bootstrap 卡，然后在下一个示例中进一步移动以添加多行多列。

```html
<!DOCTYPE html>
<html>

<head>
    <!--Add pre compiled library files -->
    <!--Automatics css and js adder-->
    <!--auto compiled css & Js-->
    <script type="text/javascript" 
            src="//code.jquery.com/jquery-1.9.1.js">
  </script>
    <link rel="stylesheet" 
          type="text/css" 
          href="/css/result-light.css">
    <script type="text/javascript" 
            src=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js">
  </script>
    <link rel="stylesheet" 
          type="text/css" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap-theme.min.css">
    <link rel="stylesheet" 
          type="text/css" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">

</head>

<body>
    <!-- create a bootstrap card in a container-->
    <div class="container">
        <!--Bootstrap card with slider class-->
        <div id="carousel-demo" 
             class="carousel slide" 
             data-ride="carousel">
            <div class="carousel-inner">
                <div class="item">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143850/1382.png">
                </div>
                <div class="item">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143855/223-1.png">
                </div>
                <div class="item active">
                    <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143904/391.png">
                </div>
            </div>
            <!--slider control for card-->
            <a class="left carousel-control"
               href="#carousel-demo"
               data-slide="prev">
                <span class="glyphicon glyphicon-chevron-left">
              </span>
            </a>
            <a class="right carousel-control" 
               href="#carousel-demo" 
               data-slide="next">
                <span class="glyphicon glyphicon-chevron-right">
              </span>
            </a>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/aece7abd48e7cd0478f1775993ca6e19.png)

**示例 2:** 现在我们扩展示例 1 的实现，以在引导转盘中同时显示多个图像，滑块位于末端。
下面是一个样式化的 HTML 代码片段的实现。

```html
<!DOCTYPE html>
<html>

<head>
    <!--auto compiled css & Js-->
    <script type="text/javascript"
            src="//code.jquery.com/jquery-1.9.1.js">
  </script>
    <link rel="stylesheet" 
          type="text/css" 
          href="/css/result-light.css">

    <script type="text/javascript" 
            src=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js">
  </script>
    <link rel="stylesheet" 
          type="text/css" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap-theme.min.css">
    <link rel="stylesheet"
          type="text/css" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
    <!-- JavaScript for adding 
     slider for multiple images
     shown at once-->
    <script type="text/javascript">
        $(window).load(function() {
            $(".carousel .item").each(function() {
                var i = $(this).next();
                i.length || (i = $(this).siblings(":first")),
                  i.children(":first-child").clone().appendTo($(this));

                for (var n = 0; n < 4; n++)(i = i.next()).length ||
                  (i = $(this).siblings(":first")),
                  i.children(":first-child").clone().appendTo($(this))
            })
        });
    </script>

</head>

<body>
    <!-- container class for bootstrap card-->
    <div class="container">
        <!-- bootstrap card with row name myCarousel as row 1-->
        <div class="carousel slide" id="myCarousel">
            <div class="carousel-inner">
                <div class="item active">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143904/391.png" 
                               class="img-responsive">
                      </a>
                    </div>
                </div>
                <div class="item">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143850/1382.png" 
                               class="img-responsive">
                      </a>
                    </div>
                </div>
                <div class="item">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143855/223-1.png" 
                               class="img-responsive">
                      </a>
                    </div>
                </div>
            </div> <a class="left carousel-control"
                      href="#myCarousel"
                      data-slide="prev">
          <i class="glyphicon glyphicon-chevron-left">
          </i>
          </a>
            <a class="right carousel-control" 
               href="#myCarousel" 
               data-slide="next">
              <i class="glyphicon glyphicon-chevron-right">
              </i>
          </a>

        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/bc30935438218a44832ea2fc870119e5.png)

**示例 3:** 现在我们创建一个 Bootstrap 卡，使用滑块将多个图像按行&列堆叠。
我们在引导转盘中显示多个帖子，也就是说，我们使用矩阵表显示多个图像。
下面是一个样式化的 HTML 代码片段的实现。

```html
<!DOCTYPE html>
<html>

<head>
    <!-- auto compiled css and js library files-->
    <script type="text/javascript" 
            src="//code.jquery.com/jquery-1.9.1.js">
  </script>
    <link rel="stylesheet" 
          type="text/css" 
          href="/css/result-light.css">
    <script type="text/javascript" 
            src=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js">
  </script>
    <link rel="stylesheet" 
          type="text/css" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap-theme.min.css">

    <link rel="stylesheet" 
          type="text/css" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
    <script type="text/javascript">
        <!-- JavaScript to slide images horizontally-->
        $(window).load(function() {
            $(".carousel .item").each(function() {
                var i = $(this).next();
                i.length || (i = $(this).siblings(":first")),
                  i.children(":first-child").clone().appendTo($(this));

                for (var n = 0; n < 4; n++)(i = i.next()).length || 
                  (i = $(this).siblings(":first")), 
                  i.children(":first-child").clone().appendTo($(this))
            })
        });
    </script>

</head>

<body>
    <!--container class-->
    <div class="container">
        <!-- myCarousel as row 1 in bootstrap card named container-->
        <div class="carousel slide" id="myCarousel">
            <div class="carousel-inner">
                <div class="item active">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143855/223-1.png" 
                               class="img-responsive">
                      </a>
                    </div>
                </div>
                <div class="item">
                    <div class="col-xs-2">
                        <a href="#">
                         <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143904/391.png" 
                              class="img-responsive">
                      </a>
                    </div>
                </div>
                <div class="item">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143910/457.png" 
                               class="img-responsive">
                      </a>
                    </div>
                </div>
            </div>
            <!-- row 1 of bootstrap card control-->
            <a class="left carousel-control" 
               href="#myCarousel" 
               data-slide="prev">

              <i class="glyphicon glyphicon-chevron-left">
              </i>
          </a>
            <a class="right carousel-control" 
               href="#myCarousel" 
               data-slide="next">
              <i class="glyphicon glyphicon-chevron-right">
              </i>
          </a>

        </div>
        <!-- myCarousel as row 2 of 
             bootstrap card named container-->
        <div class="carousel slide" id="myCarousel2">
            <div class="carousel-inner">
                <div class="item active">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143910/457.png" 
                               class="img-responsive">
                      </a>
                    </div>
                </div>
                <div class="item">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143904/391.png" 
                               class="img-responsive"></a>
                    </div>
                </div>
                <div class="item">
                    <div class="col-xs-2">
                        <a href="#">
                          <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20190709143850/1382.png" 
                               class="img-responsive">
                      </a>
                    </div>
                </div>
            </div>
            <!-- myCarousel2, control of row
                 2 of container class bootstrap card-->
            <a class="left carousel-control" 
               href="#myCarousel2" 
               data-slide="prev">
              <i class="glyphicon glyphicon-chevron-left">
              </i>
          </a>
            <a class="right carousel-control"
               href="#myCarousel2"
               data-slide="next">
              <i class="glyphicon glyphicon-chevron-right">
              </i>
          </a>

        </div>

    </div>
</body>

</html>
```

**输出:**
![](img/4a569f231cc2469426d911d89e60418e.png)