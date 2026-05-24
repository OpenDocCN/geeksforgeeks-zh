# CSS 雨闪电效果

> 原文:[https://www . geesforgeks . org/CSS-雨闪电效应/](https://www.geeksforgeeks.org/css-rain-and-lightning-effect/)

为了生成雨和闪电效果，我们将使用允许动画 HTML 元素的 CSS 动画。

我们将使用**@关键帧**，允许动画在特定时间从当前样式逐渐变为新样式，然后我们将使用滤镜:色相-旋转()来产生闪电效果。

**进场:**

*   在区域中添加背景图像。
*   要生成雨水效果，请使用 CSS 的**部分:在**属性之前，将雨水的背景图像添加到同一部分。
*   我们将创建一个名为 10s 和无限时间变色的闪电效果动画。
*   为了创建颜色变化动画，我们将使用@关键帧，并使用属性**滤镜:色调-旋转(度)**给出效果。
*   为了再次创建一个下雨效果，我们将使用@关键帧属性，并在某个时间间隔内更改背景图像的位置。

**示例:**

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            body {
                margin: 0;
                padding: 0;
            }
            /*adding background to section
          and animation named color-change*/
            section {
                position: relative;
                width: 100%;
                height: 100vh;
                background-image: url(
https://media.geeksforgeeks.org/wp-content/uploads/20200828184536/download-200x200.png);
                background-size: cover;
                background-position: center;
                animation: color-change 10s linear infinite;
                animation-delay: 1s;
            }
            /*adding rain img and making opacity 0*/
            section:before {
                content: "";
                position: absolute;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background-image: url(
https://media.geeksforgeeks.org/wp-content/uploads/20200828184719/rain-300x300.png);
                animation: rain 0.4s linear infinite;
                opacity: 0;
            }
            /* just changing the position of image 
          of rain using keyframes*/
            @keyframes rain {
                0% {
                    background-position: 0 0;
                    opacity: 1;
                }

                100% {
                    background-position: 8% 80%;
                    opacity: 1;
                }
            }
            /* applying filter at different angle
          on diffrent interval using keyframe*/
            @keyframes color-change {
                0% {
                    filter: hue-rotate(0deg);
                }
                50% {
                    filter: hue-rotate(0deg);
                }
                100% {
                    filter: hue-rotate(360deg);
                }
            }
        </style>
    </head>
    <body>
        <section></section>
    </body>
</html>
```

**输出:**

![](img/cc2c6210d61e89d20635a4d187849852.png)