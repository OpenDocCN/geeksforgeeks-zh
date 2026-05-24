# 如何使用 HTML 和 CSS 在按钮上应用惊人的悬停效果？

> 原文:[https://www . geeksforgeeks . org/如何使用 html 和 css 应用惊人的悬停效果按钮/](https://www.geeksforgeeks.org/how-to-apply-amazing-hover-effect-over-button-using-html-and-css/)

您已经访问了许多网站，并且在这些网站中看到了许多悬停按钮。所以，使用[**HTML**](https://www.geeksforgeeks.org/html-tutorials/)[**CSS**](https://www.geeksforgeeks.org/css-tutorials/)可以轻松生成这样的**悬停按钮**动画效果。通过使用 HTML 我们将设计按钮的基本结构，然后通过使用 CSS 的属性，我们可以创建悬停动画效果。

提供了一个示例视频，以便更清楚地理解今天的任务。

<video class="wp-video-shortcode" id="video-555495-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210208231232/gfgout3-2021-02-08_23.10.32.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210208231232/gfgout3-2021-02-08_23.10.32.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210208231232/gfgout3-2021-02-08_23.10.32.mp4)</video>

#### 逐步实施

**第一步:**首先，我们将使用 HTML 的按钮标签设计一个简单的按钮结构。注释已经在代码中，以供您参考。

## 超文本标记语言

```html
<!DOCTYPE HTML>

<html>

<head>
    <meta http-equiv="Content-Type" 
        content="text/html; charset=UTF-8" />

    <!-- Give a suitable title -->
    <title>GFG| Button Styling</title>
</head>

<body>

    <!-- Create heading using h1 tag -->
    <h1> GeeksForGeeks Button Styling</h1>

    <div class = "container">

        <!--creation of button-->
        <button class="btn btn1">Click Me</button>
        <button class="btn btn2">Click Me</button>
    </div>
</body>

</html>
```