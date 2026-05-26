# PHP Imagick setImageInterlaceScheme() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setimageinterlacescheme-function/](https://www.geeksforgeeks.org/php-imagick-setimageinterlacescheme-function/)

`Imagick::setImageInterlaceScheme()` 函数是 PHP 中的一个内置函数，用于设置图像的隔行扫描方案。

## 语法

```php
bool Imagick::setImageInterlaceScheme( int $interlace_scheme )
```

## 参数

此函数接受与[隔行扫描常数](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.interlace-undefined)之一相对应的单个参数 `$interlace_scheme`。您也可以直接传递常量，如 `$imagick->setImageInterlaceScheme(imagick::INTERLACE_LINE);`。

隔行扫描常量列表如下：

*   `Imagick::INTERLACE_UNDEFINED(0)`
*   `Imagick::INTERLACE_LINE(1)`
*   `Imagick::INTERLACE_PLANE(3)`
*   `Imagick::INTERLACE_PARTITION(4)`
*   `Imagick::INTERLACE_GIF(5)`
*   `Imagick::INTERLACE_JPEG(6)`
*   `Imagick::INTERLACE_PNG(7)`

## 返回值

如果成功，此函数返回 `TRUE`。

## 异常

此函数在出错时引发 `ImagickException`。

下面的程序说明 PHP 中的 `Imagick::setImageInterlaceScheme()` 函数：

## 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Interlace Scheme
$imagick->setImageInterlaceScheme(imagick::INTERLACE_JPEG);

// Display the image
echo $imagick->getImageInterlaceScheme();
?>
```

## 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Interlace Scheme
$imagick->setImageInterlaceScheme(imagick::INTERLACE_PARTITION);

// Display the image
echo $imagick->getImageInterlaceScheme();
?>
```

**引用：**[https://www.php.net/manual/en/imagick.setimageinterlacescheme.php](https://www.php.net/manual/en/imagick.setimageinterlacescheme.php)