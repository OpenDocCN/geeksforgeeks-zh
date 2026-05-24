# 如何使用 jQuery 制作水波纹效果？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-make-water-ripple-effect-using-jquery/) 制造水涟漪效应

在这里，我们将使用 jQuery 在我们的网页上产生水波纹效果。为此，我们将使用 jQuery ripple.js。

**安装:**在进一步移动之前，首先我们要将水波纹 CDN 文件添加到我们的项目文件中:

> https://cdnjs.cloudflare.com/ajax/libs/jquery.ripples/0.5.3/jquery.ripples.min.js

**进场:**

*   首先，将上面的 CDN 添加到您的工作文件中。
*   拖放半径定义通过在画布上单击或移动鼠标而产生的拖放大小(以像素为单位)。
*   Perdurance 是由波纹引起的折射量。0 表示没有折射。
*   要渲染到的 WebGL 纹理的分辨率、宽度和高度。该值越大，渲染越平滑，波纹传播越慢。
*   互动，鼠标点击和鼠标移动这两个事件都可以触发效果。

下面是这个效果的代码。

**HTML 代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="utf-8">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery.ripples/0.5.3/jquery.ripples.min.js">
    </script>
</head>

<body>
    <div class="full-landing-image">
        <h1>GeeksForGeeks</h1>
    </div>
</body>

</html>
```

**CSS 代码:**

```html
body{
    margin: 0;
    padding: 0;
}

h1{
    text-align: center;
    color: blueviolet;
    padding-top: 300px;
}

.full-landing-image{
    width: 100%;
    height: 100vh;
    background-color: black;
    background-size: cover;
}
```

**JavaScript 代码:**

## java 描述语言

```html
<!DOCTYPE html>
<html lang="en" dir="ltr">

<head>
    <meta charset="utf-8">

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js">
        </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery.ripples/0.5.3/jquery.ripples.min.js">
        </script>

    <style type="text/css">
        body {
            margin: 0;
            padding: 0;
        }

        h1 {
            text-align: center;
            color: blueviolet;
            padding-top: 300px;
        }

        .full-landing-image {
            width: 100%;
            height: 100vh;
            background-color: black;
            background-size: cover;
        }
    </style>
</head>

<body>
    <div class="full-landing-image">
        <h1>GeeksForGeeks</h1>
    </div>

    <script type="text/javascript">
        $(".full-landing-image").ripples({
            resolution: 512,
            dropRadius: 20,
            interactive: true,
            perturbance: 0.02,
        });
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-557478-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210213093941/WhatsApp-Video-2021-02-12-at-4.14.28-PM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210213093941/WhatsApp-Video-2021-02-12-at-4.14.28-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210213093941/WhatsApp-Video-2021-02-12-at-4.14.28-PM.mp4)</video>