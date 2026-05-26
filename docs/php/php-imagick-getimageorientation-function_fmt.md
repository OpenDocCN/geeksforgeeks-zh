# PHP Imagick getImageOrientation() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-getimageorientation-function/](https://www.geeksforgeeks.org/php-imagick-getimageorientation-function/)

`Imagick::getImageOrientation()` 函数是 PHP 中的一个内置函数，用于获取图像方向。

## 语法

```php
int Imagick::getImageOrientation( void )
```

## 参数

此函数不接受任何参数。

## 返回值

此函数返回包含[方向常数](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.orientation-undefined)之一的整数值。

取向常量列表如下：

*   `Imagick::ORIENTATION_UNDEFINED(0)`
*   `Imagick::ORIENTATION_TOPLEFT(1)`
*   `Imagick::ORIENTATION_TOPRIGHT(2)`
*   `Imagick::ORIENTATION_BOTTOMRIGHT(3)`
*   `Imagick::ORIENTATION_BOTTOMLEFT(4)`
*   `Imagick::ORIENTATION_LEFTTOP(5)`
*   `Imagick::ORIENTATION_RIGHTTOP(6)`
*   `Imagick::ORIENTATION_RIGHTBOTTOM(7)`
*   `Imagick::ORIENTATION_LEFTBOTTOM(8)`

## 异常

此函数在出错时引发 `ImagickException`。

下面的程序演示了 PHP 中的 `Imagick::getImageOrientation()` 函数：

### 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Get the Orientation
$orientation = $imagick->getImageOrientation();
echo $orientation;
?>
```

### 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Orientation
$imagick->setImageOrientation(imagick::ORIENTATION_TOPRIGHT);

// Get the Orientation
$orientation = $imagick->getImageOrientation();
echo $orientation;
?>
```

## 引用

[https://www.php.net/manual/en/imagick.getimageorientation.php](https://www.php.net/manual/en/imagick.getimageorientation.php)