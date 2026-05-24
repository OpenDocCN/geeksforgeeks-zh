# JQuery |如何使用 RateYo 实现星级系统

> 原文:[https://www . geeksforgeeks . org/jquery-如何实施-星级-系统-使用-rateyo/](https://www.geeksforgeeks.org/jquery-how-to-implement-star-rating-system-using-rateyo/)

**rateYo** :- rateYo 是一个 jQuery 插件，用于创建一个星级小部件，允许在鼠标悬停时填充基于星级的 SVG(可缩放矢量图形)的未评级部分的背景颜色。它是完全可定制和可扩展的，以满足任何设计需求。

**使用 RateYo 实施星级系统的步骤:**

1.  **Installation:**

    ```html
    1.  # NPM
         $ npm install rateYo
    2. #Bower
         $ bower install rateYo

    ```

    您还可以使用谷歌托管/微软托管的内容交付网络(CDN)来包含 jQuery 的版本。

    ```html
    <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/rateYo/2.3.2/jquery.rateyo.min.css">

    <!-- Latest compiled and minified JavaScript -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/rateYo/2.3.2/jquery.rateyo.min.js"></script>
    ```

2.  在 html 页面的头部添加所需的样式表。

    ```html
    <link rel="stylesheet" type="text/css" href="jquery.rateyo.min.css"> 
    ```

3.  创建一个 div 作为星级容器。

    ```html
    <div id="rateYo"></div>
    ```

4.  在 html 页面的正文部分添加需要的样式表，链接 rateYo 插件的 javaScript 文件，执行各种功能。

    ```html
    <script type="text/javascript" src="jquery.min.js"></script>

    <script type="text/javascript" src="jquery.rateyo.min.js"></script>
    ```

5.  调用一个插件，将一个基本星级渲染到你创建的 rateYo div 中。

    ```html
    $("#rateYo").rateYo();
    ```

**例**

```html
<!DOCTYPE html>
<html>

<head>
    <title>rating</title>
    <link rel="stylesheet" 
          type="text/css" 
          href="jquery.rateyo.min.css">
</head>

<body>
    <div style="width: 600px; margin: 30px auto">
        <div id="rateYo"></div>
    </div>
    <script type="text/javascript" 
            src="jquery.min.js"></script>
    <script type="text/javascript" 
            src="jquery.rateyo.min.js"></script>
    <script>
        $("#rateYo").rateYo({
            rating: 1.5,
            spacing: "10px",
            numStars: 5,
            minValue: 0,
            maxValue: 5,
            normalFill: 'black',
            ratedFill: 'orange',

        })
    </script>

</body>

</html>
```

**输出**
![](img/59f51bb50863d4e0cd17bfb1017770c9.png)