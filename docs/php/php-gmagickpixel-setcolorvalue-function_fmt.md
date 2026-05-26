# GmagickPixel::setColorvalue() 函数

> Original: [https://www.geeksforgeeks.org/php-gmagickpixel-setcolorvalue-function/](https://www.geeksforgeeks.org/php-gmagickpixel-setcolorvalue-function/)

`GmagickPixel::setColorvalue()` 函数是 PHP 中的一个内置函数，用于为给定的 `GmagickPixel` 颜色设置提供的颜色通道的规格化值。规格化值是介于 0 和 1 之间的浮点数。

**语法：**

```php
GmagickPixel GmagickPixel::setcolorvalue( int $color, float $value )
```

**参数：** 此函数接受上述两个参数，如下所述：

*   `$color`：它指定与[颜色常量](https://www.php.net/manual/en/gmagick.constants.php#gmagick.constants.color-black)之一相对应的整数。
    所有颜色常量列表如下：
    *   `Imagick::COLOR_BLUE(12)`
    *   `Imagick::COLOR_CYAN(13)`
    *   `Imagick::COLOR_GREEN(14)`
    *   `Imagick::COLOR_RED(15)`
    *   `Imagick::COLOR_YELLOW(16)`
    *   `Imagick::COLOR_MAGENTA(17)`
    *   `Imagick::COLOR_OPACITY(18)`
    *   `Imagick::COLOR_ALPHA(19)`
*   `$value`：它指定值。

**返回值：** 此函数成功时返回 `GmagickPixel` 对象。

**异常：** 此函数在出错时引发 `GmagickPixelException`。

下面给出的程序说明 PHP 中的 `GmagickPixel::setColorvalue()` 函数。

## PHP

**程序 1：**

```php
<?php
// Create a new gmagickPixel object
$imagickPixel = new GmagickPixel();

// Set the color value
$imagickPixel->setColorValue(gmagick::COLOR_RED, 0.8);

// Get the Color value with gmagick::COLOR_RED
$colorValue = $imagickPixel->getcolorvalue(gmagick::COLOR_RED);
echo $colorValue;
?>
```

**输出：**

```
0.8
```

**已用图像：**
![](img/07c99ec29e7a50fc3ea91a9d4a8d2f31.png)

**程序 2：**

```php
<?php

// Create a new gmagickPixel object
$imagickPixel = new GmagickPixel();

// Create a new Gmagick object
$gmagick = new Gmagick('geeksforgeeks.png');

// Create a new GmagickPixel object
$gmagickPixel = new GmagickPixel();

// Set the color to red
$gmagickPixel->setcolor('red');

// Set the color value of red to 0.5 for light red
$gmagickPixel->setcolorvalue(gmagick::COLOR_RED, 0.5);

// Create a GmagickDraw object
$draw = new GmagickDraw();

// Set fill color using gmagickpixel
$draw->setfillcolor($gmagickPixel);

// Set the font size
$draw->setfontsize(40);

// Annotate a text
$draw->annotate(180, 180, 'GeeksforGeeks');

// Use of drawimage function
$gmagick->drawImage($draw);

// Display the output image
header("Content-Type: image/png");
echo $gmagick->getImageBlob();
?>
```

**输出：**
![](img/a8f4f61269b0cd69e3917377d1914cf4.png)

**引用：** [https://www.php.net/manual/en/gmagickpixel.setcolorvalue.php](https://www.php.net/manual/en/gmagickpixel.setcolorvalue.php)