# PHP Gmagick getimagechanneldepth() 函数

> Original: [https://www.geeksforgeeks.org/php-gmagick-getimagechanneldepth-function/](https://www.geeksforgeeks.org/php-gmagick-getimagechanneldepth-function/)

`Gmagick::getimagechanneldepth()` 函数是 PHP 中的一个内置函数，用于返回通道图像的深度。

**语法：**

```php
int Gmagick::getimagechanneldepth( $channel_type )
```

**参数：** 此函数接受单个参数 `$channel_type`，该参数保存对通道模式有效的通道常量。通道的默认值为 `Gmagick::Channel_Default`。

**返回值：** 此函数返回通道深度。

下面的程序说明了 PHP 中的 `Gmagick::getimagechanneldepth()` 函数：

**原始图像 1：**

![原始图像](img/a377156ca25e3fe93469e179d416418f.png)

**程序 1：**

```php
<?php

// Create new Gmagick object
$im = new Gmagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-15.png');

// Using getimagechanneldepth function
// with different channel
echo $im->getimagechanneldepth(Gmagick::CHANNEL_RED) . "</br>";
echo $im->getimagechanneldepth(Gmagick::CHANNEL_GRAY) . "</br>";
echo $im->getimagechanneldepth(Gmagick::CHANNEL_CYAN) . "</br>";
echo $im->getimagechanneldepth(Gmagick::CHANNEL_GREEN) . "</br>";
echo $im->getimagechanneldepth(Gmagick::CHANNEL_BLUE) . "</br>";

?>
```