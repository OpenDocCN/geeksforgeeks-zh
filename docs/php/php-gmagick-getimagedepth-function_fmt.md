# PHP Gmagick getimageDepth() 函数

> Original: [https://www.geeksforgeeks.org/php-gmagick-getimagedepth-function/](https://www.geeksforgeeks.org/php-gmagick-getimagedepth-function/)

## 函数介绍

`gmagick::getimageDepth()` 函数是 PHP 中的一个内置函数，用于获取图像的深度。

## 语法

```php
int Gmagick::getimageDepth( void )
```

## 参数

此函数不接受任何参数。

## 返回值

此函数返回图像的深度。

## 示例程序

下面的程序说明了 PHP 中的 `Gmagick::getimageDepth()` 函数：

### 程序 1

**原始图像 1：**
![](img/efa5ea8e0258291fa60ad9a32c288072.png)

```php
<?php

// require_once('vendor/autoload.php');

// Create an Gmagick Object
$image = new Gmagick('https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-15.png');

// Use getimagedepth function to calculate image depth
$height = $image->getimageDepth();

// Display the depth of image
print_r($height);
?>
```

### 程序 2

**原始图像 2：**
![](img/966bc3ab7c1f4bfcbccb58f1729053cf.png)

```php
<?php
$string = "Computer Science portal for Geeks!";

// Creating new image of above String
// and add color and background
$im = new Gmagick();
$draw = new GmagickDraw();

// Fill the color in image
$draw->setFillColor(new GmagickPixel('green'));

// Set the text font size
$draw->setFontSize(50);

$metrix = $im->queryFontMetrics($draw, $string);
$draw->annotation(0, 40, $string);
$im->newImage($metrix['textWidth'], $metrix['textHeight'],
         new GmagickPixel('white'));

// Draw the image
$im->drawImage($draw);

$im->setImageFormat('jpeg');

$dpth = $im->getimageDepth();

// Display the depth of image
print_r($dpth);
?>
```

## 引用

[http://php.net/manual/en/gmagick.getimagedepth.php](http://php.net/manual/en/gmagick.getimagedepth.php)