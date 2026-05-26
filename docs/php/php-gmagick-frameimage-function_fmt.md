# `Gmagick::frameImage()`函数

> Original: [https://www.geeksforgeeks.org/php-gmagick-frameimage-function/](https://www.geeksforgeeks.org/php-gmagick-frameimage-function/)

`Gmagick::frameImage()`函数是PHP中的一个内置函数，用于在图像周围添加模拟的三维边框。宽度和高度指定框架垂直和水平边的边框宽度。内倒角和外倒角指示框架的内阴影和外阴影的宽度。

**语法：**

`gmagick Gmagick::frameImage(Gmagick $color, int $width, int $height, int $innerBevel, int $outerBevel)`

**参数：** 此函数接受上述五个参数，如下所述：

*   `$color`：它指定框架的颜色。
*   `$width`：它指定框架的宽度。
*   `$height`：它指定框架的高度。
*   `$innerBevel`：它指定内倒角的宽度。
*   `$outerBevel`：它指定外部倒角的宽度。

**返回值：** 此函数返回包含边框图像的`Gmagick`对象。

**异常：** 此函数在出错时引发`GmagickException`。

**使用Image：** 捕获画布区域。
![](img/07c99ec29e7a50fc3ea91a9d4a8d2f31.png)

下面给出的程序演示了PHP中的`Gmagick::frameImage()`函数：

**程序1：**

```php
<?php

// Create a new Gmagick object
$gmagick = new Gmagick('geeksforgeeks.png');

// Add the frame
$gmagick->frameimage('green', 50, 50, 15, 15);

// Output the image
header('Content-type: image/png');
echo $gmagick;
?>
```

**输出：**
![](img/55a9c804a7e359ca800d6490f5b13799.png)

**程序2：**

```php
<?php

// Create a new Gmagick object
$gmagick = new Gmagick('geeksforgeeks.png');

// Create a GmagickDraw object
$draw = new GmagickDraw();

// Set the color
$draw->setFillColor('white');

// Function to draw rectangle
$draw->rectangle(0, 0, 800, 400);

// Set the fill color
$draw->setFillColor('red');

// Set the font size
$draw->setfontsize(50);

// Annotate a text
$draw->annotate(30, 100, 'GeeksforGeeks');

// Use of drawimage function
$gmagick->drawImage($draw);

// Add the frame
$gmagick->frameimage('red', 30, 30, 5, 5);

// Display the output image
header("Content-Type: image/png");
echo $gmagick->getImageBlob();
?>
```

**输出：**
![](img/c7e804870d8d33d38924889bab12c099.png)

**参考：** [https://www.php.net/manual/en/gmagick.frameimage.php](https://www.php.net/manual/en/gmagick.frameimage.php)