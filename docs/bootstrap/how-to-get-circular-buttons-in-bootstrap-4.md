# 如何在 bootstrap 4 中获取圆形按钮？

> 原文:[https://www . geesforgeks . org/如何获取引导程序中的圆形按钮-4/](https://www.geeksforgeeks.org/how-to-get-circular-buttons-in-bootstrap-4/)

这是一个开源工具包，用于开发 HTML、CSS 和 JS。它包括几种类型的按钮、样式、字体，每一种都服务于它自己的语义目的，这是预先定义好的，为了更好的控制，还会增加一些额外的东西。您可以使用 Bootstrap 自定义按钮样式来创建您的按钮以及更多支持多种大小、状态等的按钮。
Bootstrap 默认不提供任何圆形按钮。如果我们想在网页中包含圆形按钮，那么在 Bootstrap 4 和一点 CSS 的帮助下，您可以为您的网页或应用程序创建自己的圆形按钮。

**示例:**

```html
<!DOCTYPE html>
<html>

<head>
    <title>
        How to get circular buttons
        in bootstrap 4 ?
    </title>

    <meta charset="utf-8"> 

    <meta name="viewport" content="width=device-width, initial-scale=1"> 

    <link rel="stylesheet" href= 
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"> 

    <script src= 
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"> 
    </script> 

    <script src= 
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"> 
    </script> 

    <script src= 
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"> 
    </script> 

    <style type="text/css">
        h1 {
            color:green;
        }
        .xyz {
            background-size: auto;
            text-align: center;
            padding-top: 100px;
        }
        .btn-circle.btn-sm {
            width: 30px;
            height: 30px;
            padding: 6px 0px;
            border-radius: 15px;
            font-size: 8px;
            text-align: center;
        }
        .btn-circle.btn-md {
            width: 50px;
            height: 50px;
            padding: 7px 10px;
            border-radius: 25px;
            font-size: 10px;
            text-align: center;
        }
        .btn-circle.btn-xl {
            width: 70px;
            height: 70px;
            padding: 10px 16px;
            border-radius: 35px;
            font-size: 12px;
            text-align: center;
        }
    </style>
</head>

<body class="xyz">
    <h1>GeeksforGeeks</h1>

    <h4>Normal Circle Buttons</h4>
    <button type="button" class="btn btn-primary btn-circle btn-sm">Blue</button>
    <button type="button" class="btn btn-secondary btn-circle btn-sm">Gray</button>
    <button type="button" class="btn btn-success btn-circle btn-sm">Green</button>
    <button type="button" class="btn btn-danger btn-circle btn-sm">Red</button>
    <button type="button" class="btn btn-warning btn-circle btn-sm">Yellow</button>
    <button type="button" class="btn btn-light btn-circle btn-sm">White</button>
    <button type="button" class="btn btn-dark btn-circle btn-sm">Black</button>

    <h4>Large Circle Buttons</h4>
    <button type="button" class="btn btn-primary btn-circle btn-xl">Blue</button>
    <button type="button" class="btn btn-secondary btn-circle btn-xl">Gray</button>
    <button type="button" class="btn btn-success btn-circle btn-xl">Green</button>
    <button type="button" class="btn btn-danger btn-circle btn-xl">Red</button>
    <button type="button" class="btn btn-warning btn-circle btn-xl">Yellow</button>
    <button type="button" class="btn btn-light btn-circle btn-xl">White</button>
    <button type="button" class="btn btn-dark btn-circle btn-xl">Black</button>
</body>

</html>                    
```

**输出:**借助以下代码，我们可以使用 Bootstrap 4 轻松添加圆形按钮。下面是获得的各种圆形按钮的图像。
T3】