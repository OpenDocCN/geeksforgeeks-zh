# 使用纯 CSS 在文本内波动

> 原文:[https://www . geesforgeks . org/wave-in-text-using-pure-CSS/](https://www.geeksforgeeks.org/wave-inside-text-using-pure-css/)

文本中的波浪是最酷的文本效果之一，用于网站中的文本装饰。这个动画是一个非凡的例证，说明了文本中的一个波动吸引了你的眼球。这种效果可以用来在文本、用户界面中创建波浪，在文本上创建水波效果。

**方法:**方法是使用@关键帧将动画放在第 2 个子对象上，这里我们通过 **h5:第 n 个子对象(2)** 来定位身体的第 2 个子对象，并将动画放在其中，现在对于波浪状动画，我们需要使用 CSS 的 clip-path 属性，现在通过该属性来为波浪状结构塑造多边形路径。现在让我们理解 CSS 的一些基本概念，如@关键帧、第 n 个子属性和剪辑路径属性:

*   **第 n 个子属性:**CSS 中的:第 n 个子()选择器用于根据元素在一组兄弟中的位置来匹配元素。
*   **@关键帧:**@关键帧属性用于设置使用 CSS 的动画，并提供将动画时间分成部分/速率的选项，以及播放为整个动画期间的该部分确定的动画。
*   **剪切路径属性:**利用 CSS 的剪切路径属性，将图片的特定片段剪切到这样的程度，即显示片段内部的图片，而不显示片段外部的部分图片。

下面是上述方法的实现:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Wave inside Text Animation</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Giving 1st child(first text in body) 
        basic transparent color and border */
        h5:nth-child(1) {
            color: transparent;
            -webkit-text-stroke: 1px green;
        }

        /* Giving 2nd child(second text in body) 
        green colour along with animation property */
        h5:nth-child(2) {
            color: rgb(10, 124, 16);
            animation: animate 7s ease-in-out infinite;
        }

        h5 {
            top: 50%;
            text-transform: uppercase;
            position: absolute;
            font-family: 'Segoe UI', Tahoma, 
                    Geneva, Verdana, sans-serif;
            transform: translate(calc(50vw - 50%), -55%);
            font-size: 2em;
        }

        /* giving animation to 2nd child using @keyframes
        and making wave like path using clip-path property */
        @keyframes animate {

            0%,
            100% {
                clip-path: polygon(0 45%, 6% 38%, 20% 27%, 
                    38% 24%, 40% 47%, 49% 64%, 51% 72%, 
                    74% 78%, 79% 75%, 100% 67%, 100% 100%, 
                    0 100%);
            }

            50% {
                clip-path: polygon(0 59%, 5% 71%, 24% 86%, 
                    34% 71%, 41% 64%, 41% 46%, 51% 35%, 
                    74% 21%, 89% 35%, 100% 42%, 100% 100%, 
                    0 100%);
            }
        }
    </style>
</head>

<body>
    <h5>GeeksForGeeks</h5>
    <h5>GeeksForGeeks</h5>
</body>

</html>
```

**输出:**

![](img/18111c736f25747375f3790dadb2203a.png)