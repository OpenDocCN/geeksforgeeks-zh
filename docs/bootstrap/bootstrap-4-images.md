# 引导 4 |图像

> 原文:[https://www.geeksforgeeks.org/bootstrap-4-images/](https://www.geeksforgeeks.org/bootstrap-4-images/)

Bootstrap 为图像提供了不同的类别，以使它们的外观更好，并使它们更具响应性。使图像具有响应性意味着它应该根据其父元素进行缩放。也就是说，图像的大小不应溢出其父元素，并将根据其父元素大小的变化而增长和收缩，而不会失去其纵横比。
Bootstrap 中可用于映像的不同类别如下所述:
**响应映像:**T4。在< img >标签中使用 img-fluid 类来创建响应图像。响应图像用于将图像自动调整到指定的框中。
**语法:**

```html
<img src="image_source" class="img-fluid" ...>
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Bootstrap Images</title>

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
</head>

<body style="text-align:center;">
    <div class="container">

        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <h2>Responsive Image</h2>

        <img class="img-fluid" src=
"https://media.geeksforgeeks.org/wp-content/uploads/GG-2.png"
             alt="Responsive image" width="667" height="440" />
    </div>
</body>

</html>                   
```

**输出:**

![](img/9f16b2f999c3028fd5e161474933ab6a.png)

**圆角图像:***。圆角*类用于创建圆角图像。该类与< img >标签一起使用。
**语法:**

```html
<img src="image_source" class="rounded" ...>
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Bootstrap Images</title>

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
</head>

<body style="text-align:center;">
    <div class="container">

        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <h2>Rounded Corner Image</h2>

        <img class="rounded" src=
"https://media.geeksforgeeks.org/wp-content/uploads/GG-2.png"
             alt="Responsive image" width="367" height="340" />
    </div>
</body>

</html>                   
```

**输出:**

![](img/d6a32d73dbfd276967f1b20bdbe433f3.png)

**圆形图像:***。圆形*类用于创建圆形图像。
**语法:**

```html
<img src="image_source" class="rounded-circle" ...>
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Bootstrap Images</title>

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
</head>

<body style="text-align:center;">
    <div class="container">

        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <h2>Circle Image</h2>

        <img class="rounded-circle" src=
"https://media.geeksforgeeks.org/wp-content/uploads/GG-2.png"
             alt="Responsive image" width="467" height="340" />
    </div>
</body>

</html>                   
```

**输出:**

![](img/61b8769248f4be59dcf03ffd39148380.png)

**缩略图:**T2。img-thumbnail 类用于创建缩略图(带边框)图像。
**语法:**

```html
<img src="image_source" class="img-thumbnail" ...>
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Bootstrap Images</title>

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
</head>

<body style="text-align:center;">
    <div class="container">

        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <h2>Thumbnail Image</h2>

        <img class="img-thumbnail" src=
"https://media.geeksforgeeks.org/wp-content/uploads/GG-2.png"
             alt="Responsive image" width="467" height="340" />
    </div>
</body>

</html>                   
```

**输出:**

![](img/a72c59f0a19733a63128fb0e48649453.png)

**对齐图像:***。向左浮动*和*。浮动-右*类用于设置图像的左右对齐。
**语法:**

```html
<img src="image_source" class="float-left/float-right" ...>
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Bootstrap Images</title>

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
</head>

<body style="text-align:center;">
    <div class="container">

        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <h2>Aligning Image</h2>

        <!-- Bootstrap float-left class -->
        <img class="float-left" src=
"https://media.geeksforgeeks.org/wp-content/uploads/GG-2.png"
             alt="Responsive image" width="250" height="250" />

        <!-- Bootstrap float-right class -->    
        <img class="float-right" src=
"https://media.geeksforgeeks.org/wp-content/uploads/GG-2.png"
             alt="Responsive image" width="250" height="250" />
    </div>
</body>

</html>                   
```

**输出:**

![](img/e3b9d1ca06633ce5a754bf33d4d4edcb.png)

**中心图像:***。mx-auto* (保证金:自动)和*。d-block* (显示:block)类用于将图像设置为居中。
**语法:**

```html
<img src="image_source" class="mx-auto d-block" ...>
```

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Bootstrap Images</title>

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
</head>

<body>
    <div class="container">

        <h1 style="color:green;text-align:center;">
            GeeksforGeeks
        </h1>

        <h2 style="text-align:center;">Centered Image</h2>

        <img class="mx-auto d-block" src=
"https://media.geeksforgeeks.org/wp-content/uploads/GG-2.png"
             alt="Responsive image" width="350" height="250" />
    </div>
</body>

</html>                   
```

**输出:**

![](img/1a6ecb34d39b383c4427b6330a87cf21.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队