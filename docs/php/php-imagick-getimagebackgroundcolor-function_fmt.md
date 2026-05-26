# PHP Imagick getImageBackgroundColor() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-getimagebackgroundcolor-function/](https://www.geeksforgeeks.org/php-imagick-getimagebackgroundcolor-function/)

`Imagick::getImageBackgroundColor()` 函数是 PHP 中的一个内置函数，用于获取图像背景颜色。

## 语法

```php
*ImagickPixel* Imagick::getImageBackgroundColor( *void* )
```

## 参数

此函数不接受任何参数。

## 异常

此函数在出错时引发 `ImagickException`。

## 返回值

此函数返回设置为图像背景颜色的 `ImagickPixel`。

下面的程序说明了 PHP 中的 `Imagick::getImageBackgroundColor()` 函数：

## 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Get the Background Color
$imagickPixelColor = $imagick->getImageBackgroundColor();

// Get the Color from ImagickPixel
$color = $imagickPixelColor->getColorAsString();

echo $color;
?>
```

## 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Background Color
$imagick->setImageBackgroundColor('orange');

// Get the Background Color
$imagickPixelColor = $imagick->getImageBackgroundColor();

// Get the Color from ImagickPixel
$color = $imagickPixelColor->getColorAsString();

echo $color;
?>
```

**引用：**[https://www.php.net/manual/en/imagick.getimagebackgroundcolor.php](https://www.php.net/manual/en/imagick.getimagebackgroundcolor.php)