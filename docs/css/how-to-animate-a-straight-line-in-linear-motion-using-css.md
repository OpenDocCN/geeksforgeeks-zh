# 如何用 CSS 制作直线运动的动画？

> 原文:[https://www . geeksforgeeks . org/如何使用 css 制作直线运动动画/](https://www.geeksforgeeks.org/how-to-animate-a-straight-line-in-linear-motion-using-css/)

直线的直线运动意味着直线将从一点开始，到第二点，然后回到起点。它是一种往返运动。我们将只使用 CSS。

**方法:**方法是首先创建一条直线，然后使用关键帧为其设置动画。它将分两步完成。第一个用于向前运动，第二个用于向后运动。下面的代码将遵循相同的方法。

**HTML:** 在 HTML 中，我们创建了一个用来做直线的 div 元素。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />
    <title>GeeksforGeeks</title>
</head>

<body>
    <div class="geeks"></div>
</body>

</html>
```

CSS:

*   通过提供您喜欢的最小高度和宽度来创建一条直线。
*   使用 before 选择器制作这条直线的动画，并为其提供一个线性动画，其关键帧标识符命名为*动画*。
*   关键帧的动画非常简单。对于前半帧，使宽度为 100%(向前移动)，然后在下半帧将其减小到 0%(向后移动)。

```html
<style>
    body {
        margin: 0;
        padding: 0;
        background: green;
    }

    .geeks {
        width: 400px;
        height: 2px;
        background: #fff;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .geeks::before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: green;
        animation: animate 5s linear infinite;
    }

    @keyframes animate {
        0% {
            left: 0;
        }

        50% {
            left: 100%;
        }

        0% {
            left: 0;
        }
    }
</style>
```

**完整代码:**在本节中，我们将结合 HTML 和 CSS 代码来制作直线动画效果。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0" />

    <title>
        How to animate a straight
        line in linear motion?
    </title>

    <style>
        body {
            margin: 0;
            padding: 0;
            background: green;
        }

        .geeks {
            width: 400px;
            height: 2px;
            background: #fff;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        .geeks::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: green;
            animation: animate 5s linear infinite;
        }

        @keyframes animate {
            0% {
                left: 0;
            }

            50% {
                left: 100%;
            }

            0% {
                left: 0;
            }
        }
    </style>
</head>

<body>
    <div class="geeks"></div>
</body>

</html>
```

**输出:**
![](img/986b65df0ad2abe0674357fa4794a69b.png)