# PHP Gmagick setimagecolorspace() 函数

> Original: [https://www.geeksforgeeks.org/php-gmagick-setimagecolorspace-function/](https://www.geeksforgeeks.org/php-gmagick-setimagecolorspace-function/)

`Gmagick::setimagecolorspace()` 函数是 PHP 中的一个内置函数，用于设置图像色彩空间。

## 语法

```php
Gmagick Gmagick::setimagecolorspace( int $colorspace )
```

## 参数

此函数接受单个参数 `$colorspace`，该参数保存与其中一个颜色空间常量对应的整数。

## 恒定色彩空间

*   `Gmagick::COLORSPACE_UNDEFINED` (0)
*   `Gmagick::COLORSPACE_TRANSPARENT` (3)
*   `Gmagick::COLORSPACE_OHTA` (4)
*   `Gmagick::COLORSPACE_YCBCR` (7)
*   `Gmagick::COLORSPACE_YCC` (8)
*   `Gmagick::COLORSPACE_YPBPR` (10)
*   `Gmagick::COLORSPACE_YUV` (11)
*   `Gmagick::COLORSPACE_SRGB` (13)
*   `Gmagick::COLORSPACE_HSB` (14)
*   `Gmagick::COLORSPACE_HSL` (15)
*   `Gmagick::COLORSPACE_HWB` (16)
*   `Gmagick::COLORSPACE_REC601LUMA` (17)
*   `Gmagick::COLORSPACE_REC709LUMA` (19)
*   `Gmagick::COLORSPACE_LOG` (21)

## 返回值

如果成功，此函数返回 `TRUE`。

## 异常

此函数在出错时引发 `GmagickException`。

## 用于捕获画布区域的图像

![](img/07c99ec29e7a50fc3ea91a9d4a8d2f31.png)

下面给出的程序演示了 PHP 中的 `Gmagick::setimagecolorspace()` 函数：

### 程序 1：使图像灰显

```php
<?php

// Create a new Gmagick object
$gmagick = new Gmagick('geeksforgeeks.png');

// Set the image colorspace to Gmagick::COLORSPACE_GRAY
$gmagick->setimagecolorspace(Gmagick::COLORSPACE_GRAY);

// Display the image
header("Content-Type: image/png");
echo $gmagick;
?>
```

**输出：**
![](img/d01c8da3f0353bf20a27e15466300b29.png)

### 程序 2：SRGB 色彩空间

```php
<?php

// Create a new Gmagick object
$gmagick = new Gmagick('geeksforgeeks.png');

// Set the image colorspace to Gmagick::COLORSPACE_SRGB
$gmagick->setimagecolorspace(Gmagick::COLORSPACE_SRGB);

// Display the image
header("Content-Type: image/png");
echo $gmagick;
?>
```

**输出：**
![](img/eeb3dc515166b51fff073a0900d3b6d7.png)

## 引用

[https://www.php.net/manual/en/gmagick.setimagecolorspace.php](https://www.php.net/manual/en/gmagick.setimagecolorspace.php)