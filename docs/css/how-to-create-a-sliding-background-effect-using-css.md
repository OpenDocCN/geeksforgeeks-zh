# 如何用 CSS 创建滑动背景效果？

> 原文:[https://www . geesforgeks . org/如何使用-css/](https://www.geeksforgeeks.org/how-to-create-a-sliding-background-effect-using-css/) 创建滑动背景效果

滑动背景效果不同于幻灯片或旋转木马。幻灯片或转盘由可根据用户意愿停止的分割幻灯片组成。滑动背景拍摄图像，并在 x 轴上无限循环滑动，以创建永不结束且持续移动的背景效果。

**方法:**在 HTML 布局中，需要两个元素来实现滑动背景。一个完全符合视口，另一个穿过视口并溢出视口。简单地说，一个用于背景，另一个用作背景的包含包装。

```html
<div class="wrapper">
  <div class="sliding-background"></div>
</div>
```

下一步，这两个元素被赋予相关的位置。默认情况下，包装将是浏览器宽度的 100%，并且应用了一个*溢出*属性，该属性将隐藏包装外部可视的任何内容。包装器将允许用户只看到其中包含的部分。它被设置为一定会溢出几乎每个视口的宽度，这意味着它会溢出包装。

```html
.wrapper {
  overflow: hidden;
}
.sliding-background {
  height: 960px;
  width: 6000px;
}
```

下一步，需要创建任意高度和宽度的背景图像。宽度被认为是三倍大，以适应一分钟长的环。画布将在一分钟内无限循环移动三次。最推荐的创建图像的软件是 Adobe Photoshop。创建图像后，将其添加到*滑动背景* CSS，如下所示。

```html
.sliding-background {
  background: url("path to the image") repeat-x;
  height: 500px;
  width: 5076px;
}
```

下一步包括添加滑动效果。背景图像预计会在一个循环中从左向右移动，该循环重复并创建图像无限移动的无缝效果。*变换*用于在动画开始时将左图像定位在包装器的左侧。当动画完成时，它会将位置负变换(从左到右)一个与我们图像的精确宽度相匹配的量。这就是为什么*滑动背景*是实际图像宽度的三倍，图像在 0%到 100%之间重复三次，然后再次循环。

```html
@keyframes .slide {
  0%{
    transform: translate3d(0, 0, 0);
  }
  100%{
    transform: translate3d(-1692px, 0, 0);
  }
}
```

动画属性将指示*滑动-背景*类使用滑动动画以线性无限循环的方式一次运行一分钟。

```html
.sliding-background {
  background: url("..path/to/image") repeat-x;
  height: 560px;
  width: 5076px;
  animation: slide 60s linear infinite;
}
```

**完整代码:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>Sliding Background</title>
    <style>
        .wrapper {
            overflow: hidden;
        }

        .sliding-background {
            background: url(
"https://ik.imagekit.io/slashit/sliding-background_3z5vIlHdF.png") 
            repeat-x;
            height: 961px;
            width: 6000px;
            animation: slide 60s linear infinite;
        }

        @keyframes slide {
            0% {
                transform: translate3d(0, 0, 0);
            }

            100% {
                transform: translate3d(-2000px, 0, 0);
            }
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <div class="sliding-background"></div>
    </div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-428089-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200609000424/My-Video3.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200609000424/My-Video3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200609000424/My-Video3.mp4)</video>