# jQuery slide . js 插件

> 原文:[https://www.geeksforgeeks.org/jquery-slideshow-js-plugin/](https://www.geeksforgeeks.org/jquery-slideshow-js-plugin/)

Slides.js 是 jQuery 的一个响应性幻灯片插件，具有触摸和 CSS3 过渡等功能。它有助于轻松实现幻灯片以及在设备上流畅运行的动画。

其特点如下:

*   **响应**:可以创建响应的幻灯片。
*   **触摸**:可以在幻灯片中添加触摸动作。
*   **CSS3 转场**:可以添加在幻灯片中运行完美的动画。

要使用这个插件，只需在正文标签上方添加 **CDN** 链接:

```html
<script src="//code.jquery.com/jquery-latest.min.js"></script>

<script src="jquery.slides.min.js"></script>
```

**示例:**

## 超文本标记语言

```html
<!Doctype html>
<html>

<head>
    <meta charset="utf-8">
    <title>SlidesJS Example</title>
    <meta name="description"
          content="SlidesJS is a simple slideshow plugin for jQuery. ">
    <!-- SlidesJS Required (if responsive): 
        Sets the page width to the device width. -->
    <meta name="viewport" 
          content="width=device-width">
    <!-- End SlidesJS Required -->

    <!-- CSS for slidesjs.com example -->
    <link rel="stylesheet" 
          href=
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <!-- End CSS for slidesjs.com example -->

<!-- SlidesJS Optional: If you'd like to use this design -->
    <style>
        #slides {
            display: none
        }

        #slides .slidesjs-navigation {
            margin-top: 3px;
        }

        #slides .slidesjs-previous {
            margin-right: 5px;
            float: left;
        }

        #slides .slidesjs-next {
            margin-right: 5px;
            float: left;
        }

        .slidesjs-pagination {
            margin: 6px 0 0;
            float: right;
            list-style: none;
        }

        .slidesjs-pagination li {
            float: left;
            margin: 0 1px;
        }

        .slidesjs-pagination li a {
            display: block;
            width: 13px;
            height: 0;
            padding-top: 13px;
            background-image: url(
https://media.geeksforgeeks.org/wp-content/uploads/20201213110552/logo.png);
            background-position: 0 0;
            float: left;
            overflow: hidden;
        }

        .slidesjs-pagination li a.active,
        .slidesjs-pagination li a:hover.active {
            background-position: 0 -13px
        }

        .slidesjs-pagination li a:hover {
            background-position: 0 -26px
        }

        #slides a:link,
        #slides a:visited {
            color: #333
        }

        #slides a:hover,
        #slides a:active {
            color: #9e2020
        }

        .navbar {
            overflow: hidden
        }
    </style>

    <!-- SlidesJS Required: These styles are required 
        if you'd like a responsive slideshow -->
    <style>
        #slides {
            display: none
        }

        .container {
            margin: 0 auto
        }
        /* For tablets & smart phones */

        @media (max-width: 767px) {
            body {
                padding-left: 20px;
                padding-right: 20px;
            }
            .container {
                width: auto
            }
        }
        /* For smartphones */

        @media (max-width: 480px) {
            .container {
                width: auto
            }
        }
        /* For smaller displays like laptops */

        @media (min-width: 768px) and (max-width: 979px) {
            .container {
                width: 724px
            }
        }
        /* For larger displays */

        @media (min-width: 1200px) {
            .container {
                width: 1170px
            }
        }
    </style>
    <!-- SlidesJS Required: -->
</head>

<body>

    <!-- SlidesJS Required: Start Slides -->
    <!-- The container is used to define the width of the slideshow -->
    <div class="container">
        <div id="slides">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210302151833/GeeksClassesLiveSession.png" 
                 alt="">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20210103105723/geeksforgeeks6.png" 
                 alt="" 
                 style="size:20px">
            <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201027221346/CompleteInterviewPreparationCoursebyGeeksforGeeks.png" 
                 alt="">
            <a href="#" class="slidesjs-next slidesjs-navigation">
                <i class="fa fa-chevron-circle-left"></i></a>
            <a href="#" class="slidesjs-previous slidesjs-navigation">
                <i class="fa fa-chevron-circle-right"></i></a>
        </div>
    </div>
    <!-- End SlidesJS Required: Start Slides -->

    <!-- SlidesJS Required: Link to jQuery -->
    <script src="http://code.jquery.com/jquery-1.9.1.min.js">
      </script>
    <!-- End SlidesJS Required -->

    <!-- SlidesJS Required: Link to jquery.slides.js -->
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/slidesjs/3.0/jquery.slides.js">
    </script>
    <!-- End SlidesJS Required -->

    <!-- SlidesJS Required: Initialize SlidesJS with a jQuery doc ready -->
    <script>
        $(function() {
            $('#slides').slidesjs({
                width: 940,
                height: 528,
                navigation: false
            });
        });
    </script>
    <!-- End SlidesJS Required -->
</body>

</html>
```

**输出:**

![](img/2ce29d96853b69a1d802b0a57c35a517.png)