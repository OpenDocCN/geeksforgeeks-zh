# jQuery Jcrop 插件

> 哎哎哎::1230【https://www . geeksforgeeks . org/jquery-jcrop 插件/

在本文中，我们将学习如何使用 PHP 和 jQuery **Jcrop** 插件裁剪图像。

**注意:**请下载 jQuery [**Jcrop**](https://github.com/tapmodo/Jcrop) 插件，并在你的 HTML 代码头部包含所需文件。

> <link href="”jquery.Jcrop.min.css”" rel="”stylesheet”" type="”text/css”/">
> <脚本 src="jquery . min . js "></脚本>
> <脚本 src = " jquery。jcrop . min . js "></脚本>

**示例:**下面的 HTML 代码演示了 **Jcrop** 插件，它获取一个图像文件，并给出一个“裁剪图像”按钮来裁剪图像，并在另一个 HTML“div”中显示输出的裁剪图像。

```html
<!DOCTYPE html>
<html>

<head>

    <!-- All the required libraries to
         crop the image-->
    <link rel="stylesheet" 
        href="jquery.Jcrop.min.css" 
        type="text/css" />
    <script src="jquery.min.js"></script>
    <script src="jquery.Jcrop.min.js"></script>

    <style>
        body {
            width: 500px;
            height: 380px;
            font-family: Arial, Sans-serif;
        }

        .btnSubmitClass {
            background-color: #696969;
            padding: 5px 30px;
            border: #696969 1px solid;
            border-radius: 4px;
            color: #FFFFFF;
            margin-top: 10px;
        }

        input#cropBtnID {
            padding: 5px 25px 5px 25px;
            background: #D3D3D3;
            border: #98b398 1px solid;
            color: #FFF;
            visibility: hidden;
        }

        #outputImage {
            margin-top: 40px;
        }
    </style>
</head>

<body>
    <h2>
        How to crop image using 
        jQuery and PHP
    </h2>

    <div>
        <img src="gfg2.jpg" id="cropImageID" 
                class="img" /><br />
    </div>
    <div id="btn">
        <input type='button' id="cropBtnID" 
                value='Crop Image'>
    </div>
    <div>
        <img src="#" id="outputImage" 
                style="display:none;">
    </div>
    <script type="text/javascript">
        $(document).ready(function () {
            var size;
            $('#cropImageID').Jcrop({

                /* Some settings for 
                basic configuration*/
                allowSelect: true,
                allowMove: true,
                allowResize: true,
                fixedSupport: true,
                aspectRatio: 1,
                onSelect: function (c) {
                    size = { x: c.x, y: c.y, 
                            w: c.w, h: c.h };

                    $("#cropBtnID").css(
                        "visibility", "visible");
                }//end onSelect
            });//end Jcrop method

            $("#cropBtnID").click(function () {
                var img = $("#cropImageID").attr('src');
                $("#outputImage").show();

                $("#outputImage").attr('src', 
                    'image-features.php?x = ' +
                    size.x + ' & y=' + size.y +
                    ' & w=' + size.w + '&h=' + 
                    size.h + '&img=' + img);
            });
        });//end document ready fn
    </script>
</body>

</html>
```

**PHP 代码:**下面的 PHP 代码实现了“image-features.php”文件，该文件在上面的 HTML 代码中用于创建图像和颜色。用于创建新图像的 PHP 函数是[**imagecreatefrom JPEG()**](https://www.geeksforgeeks.org/php-imagecreatefromjpeg-function/)方法。使用 PHP[**imagecreatetrue color()**](https://www.geeksforgeeks.org/php-imagecreatetruecolor-function/)方法创建一个新的真彩色图像。使用的其他 PHP 函数有[**【imagecopy ressampled()】**](https://www.geeksforgeeks.org/php-imagecopyresampled-function/)[**imagejpeg()**](https://www.geeksforgeeks.org/php-imagejpeg-function/)。

```html
<?php

// Create a new image from a file
$newImage = imagecreatefromjpeg($_GET['img']);

// Create a new true color image
$newTruecolorImage = imagecreatetruecolor(
            $_GET['w'], $_GET['h']);

// Copy a portion from one image to another
imagecopyresampled($newTruecolorImage, 
        $newImage, 0, 0, $_GET['x'], $_GET['y'], 
        $_GET['w'], $_GET['h'], $_GET['w'], 
        $_GET['h']);

header('Content-type: image/jpeg');

// Display image to browser as output
imagejpeg($newTruecolorImage);

exit;
?>
```

**输出:**

![](img/5fd60970dc12561c77db1b0f47cc3a69.png)