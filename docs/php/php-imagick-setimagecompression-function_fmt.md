# PHP Imagick setImageCompression() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setimagecompression-function/](https://www.geeksforgeeks.org/php-imagick-setimagecompression-function/)

`Imagick::setImageCompression()` 函数是 PHP 中的内置函数，用于设置图像压缩类型。

## 语法

```php
bool Imagick::setImageCompression( int $compression )
```

## 参数

此函数接受单个参数 `$compression`，该参数保存与 `Imagick::COMPRESSION_*` 常量之一匹配的整数。此外，您可以像 `$imagick->setImageCompression(imagick::COMPRESSION_DXT1);` 那样直接传递常量。

压缩常量列表如下：

*   `Imagick::COMPRESSION_UNDEFINED` (0)
*   `Imagick::COMPRESSION_DXT1` (3)
*   `Imagick::COMPRESSION_DXT3` (4)
*   `Imagick::COMPRESSION_GROUP4` (7)
*   `Imagick::COMPRESSION_JPEG` (8)
*   `Imagick::COMPRESSION_LOSSLESSJPEG` (10)
*   `Imagick::COMPRESSION_LZW` (11)
*   `Imagick::COMPRESSION_RLE` (12)
*   `Imagick::COMPRESSION_ZIP` (13)

## 返回值

如果成功，此函数返回 `TRUE`。

## 异常

此函数在出错时引发 `ImagickException`。

## 程序 1

```php
<?php

// Create new Imagick Object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Compression to COMPRESSION_RLE
$imagick->setImageCompression(imagick::COMPRESSION_RLE);

// Get the Compression
$compression = $imagick->getImageCompression();
echo $compression;
?>
```

## 程序 2

```php
<?php

// Create new Imagick Object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Compression to COMPRESSION_JPEG
$imagick->setImageCompression(imagick::COMPRESSION_JPEG);

// Set the Compression quality
// This is where that compression method imagick::COMPRESSION_JPEG is
// used in the program.
$imagick->setImageCompressionQuality(5);

// Show the output
$imagick->setformat('jpg');
header("Content-Type: image/jpg");
echo $imagick->getImageBlob();
?>
```

## 输出

![](img/fa972a44b308d03f317837ed9726e945.png)

## 引用

[https://www.php.net/manual/en/imagick.setimagecompression.php](https://www.php.net/manual/en/imagick.setimagecompression.php)