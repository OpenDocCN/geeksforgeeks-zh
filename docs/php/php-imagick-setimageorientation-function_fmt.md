# PHP Imagick setImageOrientation() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setimageorientation-function/](https://www.geeksforgeeks.org/php-imagick-setimageorientation-function/)

## 函数介绍

`Imagick::setImageOrientation()` 函数是 PHP 中的内置函数，用于设置图像方向。此函数实际上并不旋转图像，它只是更改 EXIF 旋转信息。

## 语法

```php
bool Imagick::setImageOrientation( int $orientation )
```

## 参数

此函数接受单个参数 `$orientation`，该参数保存一个整数值，其中包含[方向常量](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.orientation-undefined)之一。我们还可以直接传递一个常量，如 `setImageOrientation(imagick::ORIENTATION_BOTTOMRIGHT);`。

方向常数列表如下：

*   `Imagick::ORIENTATION_UNDEFINED(0)`
*   `Imagick::ORIENTATION_TOPLEFT(1)`
*   `Imagick::ORIENTATION_TOPRIGHT(2)`
*   `Imagick::ORIENTATION_BOTTOMRIGHT(3)`
*   `Imagick::ORIENTATION_BOTTOMLEFT(4)`
*   `Imagick::ORIENTATION_LEFTTOP(5)`
*   `Imagick::ORIENTATION_RIGHTTOP(6)`
*   `Imagick::ORIENTATION_RIGHTBOTTOM(7)`
*   `Imagick::ORIENTATION_LEFTBOTTOM(8)`

## 返回值

如果成功，此函数返回 `TRUE`。

## 示例程序

下面的程序演示了 PHP 中的 `Imagick::setImageOrientation()` 函数：

### 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Orientation
$imagick->setImageOrientation(imagick::ORIENTATION_LEFTTOP);

// Get the Orientation
$orientation = $imagick->getImageOrientation();
echo $orientation;
?>
```

发帖主题：Re：Колибри0.7.8.0

### 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Orientation
$imagick->setImageOrientation(imagick::ORIENTATION_RIGHTBOTTOM);

// Get the Orientation
$orientation = $imagick->getImageOrientation();
echo $orientation;
?>
```

发帖主题：Re：Колибри0.7.8.0

## 引用

[https://www.php.net/manual/en/imagick.setimageorientation.php](https://www.php.net/manual/en/imagick.setimageorientation.php)