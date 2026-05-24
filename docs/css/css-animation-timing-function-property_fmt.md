# CSS `animation-timing-function` 属性

> 原文：[`https://www.geeksforgeeks.org/css-animation-timing-function-property/`](https://www.geeksforgeeks.org/css-animation-timing-function-property/)

CSS 中的 `animation-timing-function` 属性用于指定动画如何通过关键帧进行过渡。也就是说，它用于指定过渡期间动画的运动。

## 语法

```html
animation-timing-function: linear | ease | ease-in | ease-out |
ease-in-out | step-start | step-end|steps(int, start | end) |
cubic-bezier(n, n, n, n) | initial | inherit;
```

## 属性值

*   `ease`：使用该属性值，动画开始缓慢，然后快速，最后缓慢结束（这是默认设置）。
*   `linear`：如果为属性指定了该值，则动画从开始到结束以相同的速度播放。
*   `ease-in`：如果指定了该值，则动画从慢速开始。
*   `ease-out`：如果为属性指定了该值，则动画正常播放，但缓慢结束。这类似于 `ease`。
*   `ease-in-out`：有了这个属性值，动画开始和结束都很慢。

## 示例

以下 HTML 程序说明了 `animation-timing-function` 属性的上述属性值。

```html
<!DOCTYPE html>
<html>
    <head>
        <title>
             CSS | animation-timing-function Property
        </title>
        <style>
            .geeks {
                font-size: 40px;
                text-align:center;
                font-weight:bold;
                color:#090;
                padding-bottom: 5px;
                font-family:Times New Roman;
            }

            .geeks1 {
                font-size:17px;
                font-weight:bold;
                text-align:center;
                font-family:Times New Roman;
            }

            h2 {
                width: 350px;
                animation-name: text;
                animation-duration: 4s;
                animation-iteration-count: infinite;
                background-color: rgb(255, 210, 85);
            }

            #one {
                animation-timing-function: ease;
            }

            #two {
                animation-timing-function: linear;
            }

            #three {
                animation-timing-function: ease-in;
            }

            #four {
                animation-timing-function: ease-out;
            }

            #five {
                animation-timing-function: ease-in-out;
            }

            @keyframes text {
                from {
                    margin-left: 60%;
                }
                to {
                    margin-left: 0%;
                }
            }
        </style>
    </head>
    <body>
        <div class = "geeks">
            GeeksforGeeks
        </div>

        <div class = "geeks1">
            A computer science portal for geeks
        </div>

        <!-- For this the animation-timing-function will
             be set to ease -->
        <h2 id="one">
            This text is ease.
        </h2>

        <!-- For this animation-timing-function will
             be set to linear -->
        <h2 id="two">
            This text is linear.
        </h2>

        <!-- For this animation-timing-function will
             be set to ease-in -->
        <h2 id="three">
            This text is ease-in.
        </h2>

        <!-- For this animation-timing-function will
             be set to ease-out -->
        <h2 id="four">
            This text is ease-out.
        </h2>

        <!-- For this animation-timing-function will
             be set to ease-in-out -->
        <h2 id="five">
            This text is ease-in-out.
        </h2>
    </body>
</html>
```

## 支持的浏览器

`animation-timing-function` 属性支持的浏览器如下：

*   谷歌 Chrome 43.0
*   Internet Explorer 10.0
*   Firefox 16.0
*   Opera 30.0
*   Safari 9.0