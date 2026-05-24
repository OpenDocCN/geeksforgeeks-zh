# 在 CSS 中使用剪辑路径属性的动画

> 原文:[https://www . geesforgeks . org/animation-use-clip-path-property-in-CSS/](https://www.geeksforgeeks.org/animation-using-clip-path-property-in-css/)

**剪辑路径** CSS 属性用于剪辑区域，以便显示剪辑区域中的元素。

在本文中，我们将看到如何一起使用剪辑路径和@关键帧来创建图像动画。

**步骤 1:** 用类容器创建一个 div，该容器应该包含< img >标签。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Clip-Path Animation</title>
</head>

<body>
    <h2>Welcome to GFG</h2>

    <!--div with class container
        contains img tag -->
    <div class="container">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200717172614/authPreLogo.png"
        alt="logo">
    </div>
</body>

</html>
```

**步骤 2:** 包括 CSS 属性–

1.  我们将首先把图像剪成多边形。
2.  然后，将动画绑定到 img 标签。
3.  动画设置为无限循环三秒。
4.  现在，我们将在@关键帧中指定 CSS 样式，这将把剪辑路径属性从一个值更改为另一个值。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Clip-Path Animation</title>

    <style>
        .container {
            /* Aligning all container elements
            to center using flex */
            display: flex;
            justify-content: center;
            align-items: center;
        }

        img {
            width: 600px;

            /* Cliping img into polygon shape*/
            clip-path: polygon(50% 0%, 100% 38%, 
                    82% 100%, 18% 100%, 0% 38%);

            /* Setting animation for 3s in 
                an infinite loop */
            animation: clipPath 3s infinite;
        }

        /* Creating animation name clipPath */
        @keyframes clipPath {
            0% {
                /* clip-path property initially */
                clip-path: polygon(50% 0%, 100% 38%, 
                        82% 100%, 18% 100%, 0% 38%);
            }

            50% {
                /* clip-path property at 50% */
                clip-path: polygon(50% 50%, 90% 88%, 
                        80% 10%, 20% 10%, 8% 90%);
            }

            100% {
                /* clip-path property finally */
                clip-path: polygon(50% 0%, 100% 38%, 
                        82% 100%, 18% 100%, 0% 38%);
            }
        }
    </style>
</head>

<body>
    <h2>Welcome To GFG</h2>

    <!--div with class container 
        which contain img tag -->
    <div class="container">
        <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200717172614/authPreLogo.png"
        alt="Travel">
    </div>
</body>

</html>
```

**输出:**

![](img/b2f857e00b5559160f3251cf2cc4f989.png)