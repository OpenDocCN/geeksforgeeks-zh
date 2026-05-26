# PHP Imagick setImageColorspace() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setimagecolorspace-function/](https://www.geeksforgeeks.org/php-imagick-setimagecolorspace-function/)

`Imagick::setImageColorspace()` 函数是 PHP 中的内置函数，用于设置图像色彩空间。

## 语法

```php
bool Imagick::setImageColorspace( int $colorspace )
```

## 参数

此函数接受单个参数 `$colorspace`，该参数保存与[颜色空间常量](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.colorspace-undefined)之一相对应的整数值。

*   `Imagick::COLORSPACE_UNDEFINED` (0)
*   `Imagick::COLORSPACE_GRAY` (2)
*   `Imagick::COLORSPACE_TRANSPARENT` (3)
*   `Imagick::COLORSPACE_OHTA` (4)
*   `Imagick::COLORSPACE_YCBCR` (7)
*   `Imagick::COLORSPACE_YCC` (8)
*   `Imagick::COLORSPACE_YIQ` (9)
*   `Imagick::COLORSPACE_YPBPR` (10)
*   `Imagick::COLORSPACE_YUV` (11)
*   `Imagick::COLORSPACE_SRGB` (13)
*   `Imagick::COLORSPACE_HSB` (14)
*   `Imagick::COLORSPACE_HSL` (15)
*   `Imagick::COLORSPACE_HWB` (16)
*   `Imagick::COLORSPACE_REC601LUMA` (17)
*   `Imagick::COLORSPACE_REC709LUMA` (19)

## 返回值

如果成功，此函数返回 `TRUE`。

## 异常

此函数在出错时引发 `ImagickException`。

## 示例

下面的程序演示了 PHP 中的 `Imagick::setImageColorspace()` 函数：

### 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the image colorspace
$imagick->setImageColorspace(imagick::COLORSPACE_RGB);

// Display the image
header("Content-Type: image/png");
echo $imagick->getImageBlob();
?>
```

**输出：**
![](img/782c90925bc0aae1dbc9c85c0ab4ecb0.png)

### 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the image colorspace
$imagick->setImageColorspace(imagick::COLORSPACE_OHTA);

// Display the image
header("Content-Type: image/png");
echo $imagick->getImageBlob();
?>
```

**输出：**
![](img/71a17554020af23325ef7c10a892e705.png)

## 引用

[https://www.php.net/manual/en/imagick.setimagecolorspace.php](https://www.php.net/manual/en/imagick.setimagecolorspace.php)