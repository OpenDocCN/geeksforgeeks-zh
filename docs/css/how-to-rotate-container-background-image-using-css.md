# 如何使用 CSS 旋转容器背景图像？

> 原文:[https://www . geesforgeks . org/如何旋转-容器-背景-图像-使用-css/](https://www.geeksforgeeks.org/how-to-rotate-container-background-image-using-css/)

CSS **[背景图像属性](https://www.geeksforgeeks.org/css-background-image-property/)** 用于将图像添加到元素的背景中。在本文中，任务是旋转背景中使用的图像。

**方法:****[CSS 变换属性](https://www.geeksforgeeks.org/css-transform-property/)** 用于对元素应用二维或三维变换。此属性可用于旋转、缩放、移动甚至倾斜元素。

**语法:**

```html
.class_name { transform: value } 
```

**示例:**我们可以使用 CSS 变换属性来修复这个问题，并进行如下旋转:

```html
<!DOCTYPE html>
<html>

<head>
    <!-- Bootstrap CDN -->
    <link rel="stylesheet"
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

    <!-- CSS -->
    <style>
        .background-image {
            background-image: url('Geeksforgeeks_image.jpg');
            background-repeat: no-repeat;
            height: 300px;
        }

        .rotated-background-image {
            background-image: url('Geeksforgeeks_image.jpg');
            background-repeat: no-repeat;
            height: 100%;
            margin-top: 250px;
            transform: rotate(90deg);
            /* All browsers support */
            -moz-transform: rotate(90deg);
            -webkit-transform: rotate(90deg);
            -o-transform: rotate(90deg);
            -ms-transform: rotate(90deg);
        }

        .custom {
            height: 100px;
            padding-top: 10px;
        }
    </style>
</head>

<body>
    <!-- Normal image which is not rotated -->
    <div class="container custom">
        <div class="background-image">
        </div>
    </div>
    <!-- Rotated image -->
    <div class="container">
        <div class="rotated-background-image">
        </div>
    </div>
  </body>

</html>
```

**输出:**
![](img/db545dcf3f7145dfe462044c04da6099.png)