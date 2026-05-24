# 如何制作 CSS Loader？

> 原文:[https://www.geeksforgeeks.org/how-to-make-css-loader/](https://www.geeksforgeeks.org/how-to-make-css-loader/)

当某个页面花费几秒钟加载网页内容时，CSS 加载器非常有用。当用户必须等待内容完全加载到网页上时。如果某个网页没有 CSS 的加载器，那么加载的时候用户会认为网页根本没有响应。所以在网页上放置 CSS 加载器会让用户分心或者等待几秒钟直到页面完全加载。CSS 可用于在网页上设计和添加动画和其他视觉运动图形。下面的代码解释了 CSS 下动画的一个小演示。

**示例 1:** 本示例使用 CSS 创建 CSS 加载器。

```html
<!DOCTYPE html>
<html>

<head>
    <title>css loader</title>
    <style>
        h1{
            color:green;
        }
        .gfg {
            display: block;
            position: absolute;
            width: 10px;
            height: 10px;
            left: calc(50% - 1em);
            border-radius: 1em;
            transform-origin: 1em 2em;
            animation: rotate;
            animation-iteration-count: infinite;
            animation-duration: 1.8s;
        }

        /* Rotation of loader dots */
        @keyframes rotate {
            from {
                transform: rotateZ(0deg);
            }
            to {
                transform: rotateZ(360deg);
            }
        }
        .g1 {
            animation-delay: 0.1s;
            background-color: #1D8348;

        }
        .g2 {
            animation-delay: 0.2s;
            background-color: #239B56;
        }
        .g3 {
            animation-delay: 0.3s;
            background-color: #2ECC71;
        }
        .g4 {
            animation-delay: 0.4s;
            background-color: #82E0AA ;
        }
        .g5 {
            animation-delay: 0.5s;
            background-color: #D5F5E3;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>CSS Loader</h4>
        <div class='loader'>
            <div class='gfg g1'></div>
            <div class='gfg g2'></div>
            <div class='gfg g3'></div>
            <div class='gfg g4'></div>
            <div class='gfg g5'></div>
        </div>
    </center>
</body>

</html>
```

**输出:**
![](img/3eb87f1ec7447110f6a5281b0e80f5c6.png)

**示例 2:** 本示例使用 CSS 创建 CSS 加载器。

```html
<!DOCTYPE html>
<html>

<head>
    <title>css loader</title>
    <style>
        h1{
            color:green;
        }
        .gfg {
            display: block;
            position: absolute;
            width: 100px;
            height: 10px;
            left: calc(58% - 5em);
            transform-origin: 1px 10px;
            animation: rotate;
            animation-iteration-count: infinite;
            animation-duration: 2.8s;
        }

        /* Rotation of loader dots */
        @keyframes rotate {
            from {
                transform: rotateY(50deg);
            }
            to {
                transform: rotateY(360deg);
            }
        }
        .g1 {
            animation-delay: 0.1s;
            background-color: #1D8348;
        }
        .g2 {
            animation-delay: 0.2s;
            background-color: #239B56;
        }
        .g3 {
            animation-delay: 0.3s;
            background-color: #2ECC71;
        }
        .g4 {
            animation-delay: 0.4s;
            background-color: #82E0AA ;
        }
        .g5 {
            animation-delay: 0.5s;
            background-color: #D5F5E3;
        }
    </style>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>
        <h4>CSS Loader</h4>
        <div class='loader'>
            <div class='gfg g1'></div>
            <div class='gfg g2'></div>
            <div class='gfg g3'></div>
            <div class='gfg g4'></div>
            <div class='gfg g5'></div>
        </div>
    </center>
</body>

</html>                    
```

**输出:**
![](img/7045a3fef9469c214c6ea8701f69f219.png)