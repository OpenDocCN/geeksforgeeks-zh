# 如何在引导卡中对图像使用网格？

> 原文:[https://www . geeksforgeeks . org/引导卡映像网格使用方法/](https://www.geeksforgeeks.org/how-to-use-grid-for-images-in-bootstrap-card/)

只需使用 [img](https://www.geeksforgeeks.org/html-images/) 标签，即可将图像添加到[引导卡](https://www.geeksforgeeks.org/bootstrap-cards/)中。但是，我们不能使用相同的方法直接将图像网格放入引导卡，因为这将导致设计错位。因此，要获得每个流将图像网格放入引导卡。完美对齐的网格我们需要在 HTML 代码中添加一些 CSS。

**进场:**先设置数值 **[显示:网格；](https://www.geeksforgeeks.org/css-grid-property/)** 的 div 包装所有的图像，将其转换成网格布局。然后设置 **[网格-模板-列的值:自动；](https://www.geeksforgeeks.org/css-grid-template-columns-property/)** 的网格容器来指定网格布局中的列数。现在设置*宽度值:100%；*的图像得到一个完美的网格。

以下示例说明了上述方法:

**例 1:**2 列图像网格，即 2×2 图像网格。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Bootstrap Card</title>
    <meta charset="utf-8">
    <meta name="viewport"
        content="width=device-width, initial-scale=1">
    <link rel="stylesheet"
        href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
    </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js">
    </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js">
    </script>

    <style>
        .card {
            width: 20rem;
            margin: 2rem;
        }

        .image-grid-container {
            display: grid;

            /* For 2 columns */
            grid-template-columns: auto auto;
        }
        img {
            width: 100%;
        }
    </style>
</body>

<body>
    <div class="container">
        <div class="card">
            <div class="image-grid-container">
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200120152724/gfg_icon.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200120152724/gfg_icon.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
            </div>

            <div class="card-body">
                <h4 class="card-title">Developer Guy</h4>

                <p class="card-text">
                    Developer Guy love to develop
                    front-end and back-end
                </p>

                <a href="#" class="btn btn-primary">
                    See Profile
                </a>
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/d2e818f48d9dd4c22ed081c2fbbb7c55.png)

**例 2:**3 列图像网格，即 3×3 图像网格。

```html
<!DOCTYPE html> 
<html lang="en"> 

<head> 
    <title>Bootstrap Cards</title> 

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
    <style>
        .card {
            width: 20rem;
            margin: 2rem;
        }
        .image-grid-container {
            display: grid;

            /* For 3 columns */
            grid-template-columns: auto auto auto;
        }
        img {
            width: 100%;
        }
    </style>
</head> 

<body>
    <div class="container"> 
        <div class="card"> 
            <div class="image-grid-container">
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200120152724/gfg_icon.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200120152724/gfg_icon.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200120152724/gfg_icon.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20200120152724/gfg_icon.png">
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png">
            </div> 
            <div class="card-body"> 
                <h4 class="card-title">
                    Developer Guy
                </h4> 

                <p class="card-text">
                    Developer Guy love to develop
                    front-end and back-end 
                </p> 
                <a href="#" class="btn btn-primary">
                    See Profile
                </a> 
            </div>
        </div>
    </div>
</body>

</html>
```

**输出:**
![](img/511c6043d8bdfa516cd5645e2acb8f79.png)