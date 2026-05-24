# 如何使用 HTML & CSS 创建滑动文本展示动画？

> 原文:[https://www . geesforgeks . org/how-create-sliding-text-show-animation-use-html-CSS/](https://www.geeksforgeeks.org/how-to-create-sliding-text-reveal-animation-using-html-css/)

在本文中，我们将实现**滑动文本显示动画**，它可以用于个人文件夹、网站，甚至 YouTube 介绍视频中，为我们的视频增加额外的优势，使其在第一次播放时看起来更有趣、更吸引人眼球，最棒的是，我们将仅使用 HTML 和 CSS 来做到这一点。

**进场:**动画会从第一个文字的出现开始，比如我们把这个词当成“GEEKSFORGEEKS”，然后向左滑动，我们的第二个文字也就是:“一个面向 GEEKS 的计算机科学门户”就会向右露出(如果你还搞不清楚，动画到底讲的是什么，可以快速滚动到页面的最后看到输出，以便更好的理解)。

![](img/f5cb8eac18a1c367b295eb03dedeb9f5.png)

我们将使用不同的 [**<u>关键帧</u>**](https://www.geeksforgeeks.org/css-keyframes-rule/) 来将我们的动画分成不同的阶段，以便它顺利工作。
关键帧保存元素在特定时间的样式。使用了以下关键帧:

*   ***@个关键帧出现:*** 在这个关键帧中，我们将处理第一个文本出现的方式。
*   ***@关键帧滑动:*** 在这个关键帧中，我们将尝试以滑动的方式移动文本。
*   ***@关键帧揭示:*** 在这个关键帧中，我们将揭示我们的第二个文本。

下面是上述方法的实现。

**示例:**在本例中，我们将使用上面定义的属性来创建动画。

## index.html

```html
<!DOCTYPE html>
<html>
   <head>
      <title>Text Reveal Animation</title>
   </head>
   <style>
      @import url(
'https://fonts.googleapis.com/css2?family=Montserrat:wght@600&display=swap');
        body{
        font-family: Montserrat;
        text-align: center;
        color: #006600;
        font-size: 34px;
        padding-top: 40vh;
        overflow: hidden;
      }
      div{
        display: inline-block;
        overflow: hidden;
        white-space: nowrap;
      }
      div:first-of-type{
        animation: appear 6s infinite;
      }
      div:last-of-type{
        animation: reveal 6s infinite;
      }
      div:last-of-type span{
        font-size: 33px;
        color: #808000;
        animation: slide 6s infinite;
      }
      @keyframes appear{
        0%{opacity: 0;}
        20%{opacity: 1;}
        80%{opacity: 1;}
        100%{opacity: 0;}
      }
      @keyframes slide{
        0%{margin-left:-800px;}
        20%{margin-left:-800px;}
        35%{margin-left:0px;}
      100%{margin-left:0px;}
      }
      @keyframes reveal{
        0%{opacity: 0; width: 0px;}
        20%{opacity: 1; width: 0px;}
        30%{width: 655px;}
        80%{opacity: 1;}
        100%{opacity: 0; width: 655px;}
      }
   </style>
   <body>
      <div>GEEKSFORGEEKS</div>
      <div>
         <span>A Computer Science Portal For Geeks</span>
      </div>
   </body>
</html>
```

**输出:** ![](img/1b1fb715dfb38722f28f9da5d1129c3c.png)

**注意:**对于其他不同长度的文本，两个文本的**宽度**和**字体大小**应相应更改。