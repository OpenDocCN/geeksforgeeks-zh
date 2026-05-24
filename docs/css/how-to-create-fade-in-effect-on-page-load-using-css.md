# 如何使用 CSS 在页面加载时创建淡入效果？

> 原文:[https://www . geesforgeks . org/how-create-fade-in-effect-page-load-use-CSS/](https://www.geeksforgeeks.org/how-to-create-fade-in-effect-on-page-load-using-css/)

使用动画和过渡属性在使用 CSS 加载页面时创建淡入效果。

**方法一:使用 CSS 动画属性:**一个 CSS 动画定义有 2 个关键帧。一个不透明度设置为 0，另一个不透明度设置为 1。当动画类型设置为缓和时，动画在页面中平滑淡入。此属性应用于正文标签。每当页面加载时，这个动画就会播放，并且页面看起来会淡入。淡入的时间可以在动画属性中设置。

**语法:**

```html
body {
    animation: fadeInAnimation ease 3s
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

@keyframes fadeInAnimation {
    0% {
        opacity: 0;
    }
    100% {
        opacity: 1;
     }
}
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to create fade-in effect
        on page load using CSS
    </title>

    <style>
        body {
            animation: fadeInAnimation ease 3s;
            animation-iteration-count: 1;
            animation-fill-mode: forwards;
        }
        @keyframes fadeInAnimation {
            0% {
                opacity: 0;
            }
            100% {
                opacity: 1;
            }
        }
    </style>
</head>

<body>
    <h1 style="color: green">
        GeeksForGeeks
    </h1>

    <b>
        How to create fade-in effect
        on page load using CSS
    </b>

    <p>
        This page will fade in
        after loading
    </p>
</body>

</html>
```

**输出:**
![fadein-example](img/e6a6f63549db160960796612aa251b0d.png)

**方法 2:使用 transition 属性并在加载几何体时将不透明度设置为 1:**在该方法中，几何体最初可以设置为不透明度 0，并且每当该属性发生变化时，transition 属性都用于制作该属性的动画。加载页面时，使用 onload 事件将不透明度设置为 1。由于过渡属性，现在更改不透明度将在页面中出现褪色。淡入的时间可以在过渡属性中设置。

**语法:**

```html
body {
    opacity: 0;
    transition: opacity 5s;
}
```

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to create fade-in effect
        on page load using CSS
    </title>

    <style>
        body {
            opacity: 0;
            transition: opacity 3s;
        }
    </style>
</head>

<body onload="document.body.style.opacity='1'">

    <h1 style="color: green">
        GeeksForGeeks
    </h1>

    <b>
        How to create fade-in effect
        on page load using CSS
    </b>

    <p>
        This page will fade in
        after loading
    </p>
</body>

</html>                    
```

**输出:**
![fadein-example2](img/cb09ca6cff72e685ab2b0027c791e629.png)

CSS 是网页的基础，通过设计网站和网络应用程序用于网页开发。你可以通过以下 [CSS 教程](https://www.geeksforgeeks.org/css-tutorials/)和 [CSS 示例](https://www.geeksforgeeks.org/css-examples/)从头开始学习 CSS。