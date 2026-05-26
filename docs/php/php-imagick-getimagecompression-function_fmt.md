# PHP Imagick getImageCompression() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-getimagecompression-function/](https://www.geeksforgeeks.org/php-imagick-getimagecompression-function/)

`Imagick::getImageCompression()` 函数是 PHP 中的一个内置函数，用于获取当前图像的压缩类型。

## 语法

```php
int Imagick::getImageCompression( void )
```

## 参数

此函数不接受任何参数。

## 返回值

此函数返回一个整数值，该整数值对应于一个压缩常数。

### 压缩常量

下面给出了压缩常量的列表：

*   `Imagick::COMPRESSION_UNDEFINED` (0)
*   `Imagick::COMPRESSION_GROUP4` (7)
*   `Imagick::COMPRESSION_JPEG` (8)
*   `Imagick::COMPRESSION_LOSSLESSJPEG` (10)
*   `Imagick::COMPRESSION_LZW` (11)
*   `Imagick::COMPRESSION_RLE` (12)
*   `Imagick::COMPRESSION_ZIP` (13)
*   `Imagick::COMPRESSION_DXT1` (3)
*   `Imagick::COMPRESSION_DXT3` (4)

## 示例

### 程序 1

```php
<?php

// Create new Imagick Object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Get the Compression
$compression = $imagick->getImageCompression();
echo $compression;
?>
```

### 程序 2

```php
<?php

// Create new Imagick Object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Compression to COMPRESSION_DXT1
$imagick->setImageCompression(imagick::COMPRESSION_DXT1);

// Get the Compression
$compression = $imagick->getImageCompression();

echo $compression;
?>
```

## 引用

[https://www.php.net/manual/en/imagick.getimagecompression.php](https://www.php.net/manual/en/imagick.getimagecompression.php)