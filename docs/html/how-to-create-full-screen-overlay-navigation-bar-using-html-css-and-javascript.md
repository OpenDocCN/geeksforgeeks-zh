# 如何使用 HTML CSS 和 JavaScript 创建全屏叠加导航栏？

> 原文:[https://www . geesforgeks . org/如何创建-全屏-覆盖-导航栏-使用-html-CSS-和-javascript/](https://www.geeksforgeeks.org/how-to-create-full-screen-overlay-navigation-bar-using-html-css-and-javascript/)

**创建全屏导航栏:**在本文中，您将学习如何为您的网站创建全屏导航栏。有三种方法可以创建全屏覆盖导航栏，如下所示:

*   从左边
*   从顶部
*   没有动画-只是展示

你需要创建两个 div。一个用于覆盖容器，另一个用于覆盖内容容器。

**第一步:**第一步是创建一个 HTML 文件。

```html
<div id="myNav" class="overlay">

    <!-- Button to close the overlay navigation -->
    <a href="javascript:void(0)" class="closebtn"
        onclick="closeNav()">×
    </a>

    <!-- Overlay content -->
    <div class="overlay-content">
        <a href="#">About</a>
        <a href="#">Services</a>
        <a href="#">Clients</a>
        <a href="#">Contact</a>
    </div>
</div>

<!-- Use any element to open/show the
    overlay navigation menu -->
<span onclick="openNav()">open</span></div>
```

**第二步:**给文件添加 CSS。

```html
<style>
    overlay {
        height: 100%;
        width: 0;
        position: fixed;
        ] z-index: 1;
        left: 0;
        top: 0;
        background-color: rgb(0, 0, 0);
        background-color: rgba(0, 0, 0, 0.9);
        overflow-x: hidden;
        transition: 0.5s;
    }

    ].overlay-content {
        position: relative;
        top: 25%;
        width: 100%;
        text-align: center;
        margin-top: 30px;
    }

    .overlay a {
        padding: 8px;
        text-decoration: none;
        font-size: 36px;
        color: #818181;

        /* Display block instead
            of inline */
        display: block;

        /* Transition effects
            on hover (color) */
        transition: 0.3s;
    }

    .overlay a:hover,
    .overlay a:focus {
        color: #f1f1f1;
    }

    .overlay .closebtn {
        position: absolute;
        top: 20px;
        right: 45px;
        font-size: 60px;
    }

    @media screen and (max-height: 450px) {
        .overlay a {
            font-size: 20px
        }

        .overlay .closebtn {
            font-size: 40px;
            top: 15px;
            right: 35px;
        }
    }
</style>
```

**第 3 步:**在最后一步中，将 JavaScript 添加到文件中。

```html
<script>
    function openNav() {
        document.getElementById("myNav").style.width = "100%";
    }

    function closeNav() {
        document.getElementById("myNav").style.width = "0%";
    }

    //or

    function openNav() {
        document.getElementById("myNav").style.display = "block";
    }

    function closeNav() {
        document.getElementById("myNav").style.display = "none";
    }
</script>
```

**示例 1:** 本示例从左侧创建全屏覆盖导航栏。

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content="width=device-width, 
               initial-scale=1">
    <style>
        .overlay {
            height: 100%;
            width: 0;
            position: fixed;
            top: 0;
            left: 0;
            background-color: #1a6e1a;
            overflow-x: hidden;
            transition: 1.0s;
        }

        .overlay-content {
            position: relative;
            top: 25%;
            width: 100%;
            text-align: center;
        }

        .overlay a {
            padding: 10px;
            text-decoration: none;
            font-size: 40px;
            color: white;
            display: block;
            transition: 0.3s;
        }

        .overlay a:hover,
        .overlay a:focus {
            color: black;
        }

        .overlay .closebtn {
            position: absolute;
            top: 10px;
            right: 35px;
            font-size: 70px;
        }
    </style>
</head>

<body>

    <div id="myNav" class="overlay">
        <a href="javascript:void(0)" 
            class="closebtn" onclick="closeNav()">
            ×
        </a>
        <div class="overlay-content">
            <a href="#">About</a>
            <a href="#">Practice</a>
            <a href="#">Courses</a>
            <a href="#">Contact</a>
        </div>
    </div>

    <span style="font-size:35px;cursor:pointer"
        onclick="openNav()">
        ≡
    </span>

    <h2>GeeksForGeeks</h2>

    <p>
        Click on the nav bar icon 
        to see full screen overlay:
    </p>

    <script>
        function openNav() {
            document.getElementById(
                "myNav").style.width = "100%";
        }

        function closeNav() {
            document.getElementById(
                "myNav").style.width = "0%";
        }
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-393871-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407102433/slide-in.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200407102433/slide-in.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407102433/slide-in.mp4)</video>

**示例 2:** 本示例从顶部创建全屏覆盖导航栏。

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content="width=device-width,
               initial-scale=1">
    <style>
        .overlay {
            height: 0%;
            width: 100%;
            position: fixed;
            top: 0;
            left: 0;
            background-color: #1a6e1a;
            overflow-y: hidden;
            transition: 1.0s;
        }

        .overlay-content {
            position: relative;
            top: 25%;
            width: 100%;
            text-align: center;
        }

        .overlay a {
            padding: 10px;
            text-decoration: none;
            font-size: 40px;
            color: white;
            display: block;
            transition: 0.3s;
        }

        .overlay a:hover,
        .overlay a:focus {
            color: black;
        }

        .overlay .closebtn {
            position: absolute;
            top: 10px;
            right: 35px;
            font-size: 70px;
        }
    </style>
</head>

<body>

    <div id="myNav" class="overlay">
        <a href="javascript:void(0)"
            class="closebtn" onclick="closeNav()">
            ×
        </a>
        <div class="overlay-content">
            <a href="#">About</a>
            <a href="#">Practice</a>
            <a href="#">Courses</a>
            <a href="#">Contact</a>
        </div>
    </div>

    <span style="font-size:35px;cursor:pointer" 
            onclick="openNav()">
        ≡
    </span>

    <h2>GeeksForGeeks</h2>

    <p>
        Click on the nav bar icon
        to see full screen overlay:
    </p>

    <script>
        function openNav() {
            document.getElementById(
                "myNav").style.height = "100%";
        }

        function closeNav() {
            document.getElementById(
                "myNav").style.height = "0%";
        }
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-393871-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407102410/slide-down.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200407102410/slide-down.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407102410/slide-down.mp4)</video>

**示例 3:** 本示例创建没有动画的全屏覆盖导航栏。

```html
<!DOCTYPE html>
<html>

<head>
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <style>
        .overlay {
            height: 100%;
            width: 100%;
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            background-color: #1a6e1a;
        }

        .overlay-content {
            position: relative;
            top: 25%;
            width: 100%;
            text-align: center;
        }

        .overlay a {
            padding: 10px;
            text-decoration: none;
            font-size: 40px;
            color: white;
            display: block;
            transition: 0.3s;
        }

        .overlay a:hover,
        .overlay a:focus {
            color: black;
        }

        .overlay .closebtn {
            position: absolute;
            top: 10px;
            right: 35px;
            font-size: 70px;
        }
    </style>
</head>

<body>

    <div id="myNav" class="overlay">
        <a href="javascript:void(0)"
            class="closebtn" onclick="closeNav()">
            ×
        </a>

        <div class="overlay-content">
            <a href="#">About</a>
            <a href="#">Practice</a>
            <a href="#">Courses</a>
            <a href="#">Contact</a>
        </div>
    </div>

    <span style="font-size:35px;cursor:pointer"
            onclick="openNav()">
        ≡
    </span>

    <h2>GeeksForGeeks</h2>

    <p>
        Click on the nav bar icon to
        see full screen overlay:
    </p>

    <script>
        function openNav() {
            document.getElementById(
                "myNav").style.display = "block";
        }

        function closeNav() {
            document.getElementById(
                "myNav").style.display = "none";
        }
    </script>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-393871-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200407102342/show.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20200407102342/show.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200407102342/show.mp4)</video>