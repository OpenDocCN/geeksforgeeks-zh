# PHP Imagick setImageAlphaChannel() 函数

> Original: [`https://www.geeksforgeeks.org/php-imagick-setimagealphachannel-function/`](https://www.geeksforgeeks.org/php-imagick-setimagealphachannel-function/)

`Imagick::setImageAlphaChannel()` 函数是 PHP 中的内置函数，用于设置图像 Alpha 通道。

## 语法

```php
bool Imagick::setImageAlphaChannel( int $mode )
```

## 参数

此函数接受单个参数 `$mode`，该参数保存与 [`ALPHACHANNEL` 常量](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.alphachannel)之一相对应的整数值。

`ALPHACHANNEL` 常量列表如下：

*   `Imagick::ALPHACHANNEL_ACTIVATE` (0)
*   `Imagick::ALPHACHANNEL_DEACTIVE` (1)
*   `Imagick::ALPHACHANNEL_RESET` (2)
*   `Imagick::ALPHACHANNEL_SET` (3)
*   `Imagick::ALPHACHANNEL_UNDEFINED` (4)
*   `Imagick::ALPHACHANNEL_COPY` (5)
*   `Imagick::ALPHACHANNEL_EXTRACT` (6)
*   `Imagick::ALPHACHANNEL_OPAQUE` (7)
*   `Imagick::ALPHACHANNEL_SHAPE` (8)
*   `Imagick::ALPHACHANNEL_TRANSPARENT` (9)

## 返回值

如果成功，此函数返回 `TRUE`。

## 示例程序

下面的程序说明了 PHP 中的 `Imagick::setImageAlphaChannel()` 函数：

### 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png');

// Set background color
$imagick->setImageBackgroundColor('blue');

// Set the ImageAlphaChannel to 9 which corresponds
// to imagick::ALPHACHANNEL_TRANSPARENT
$imagick->setImageAlphaChannel(9);

// Display the image
header("Content-Type: image/png");

echo $imagick->getImageBlob();
?>
```

**输出：**
![](img/bbde89c3129a52f0ff74a06457935c99.png)

### 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png');

// Set the ImageAlphaChannel to 3 which corresponds to
// imagick::ALPHACHANNEL_SET
$imagick->setImageAlphaChannel(3);

// Display the image
header("Content-Type: image/png");

echo $imagick->getImageBlob();
?>
```

**输出：**
![](img/bbf9f6c27c8ff175b56ab46809544751.png)

## 引用

[`https://www.php.net/manual/en/imagick.setimagealphachannel.php`](https://www.php.net/manual/en/imagick.setimagealphachannel.php)