# PHP Imagick setInterlaceScheme() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setinterlacescheme-function/](https://www.geeksforgeeks.org/php-imagick-setinterlacescheme-function/)

`Imagick::setInterlaceScheme()` 函数是 PHP 中的一个内置函数，用于设置稍后在图像压缩中使用的隔行扫描方案。存在如下所给出的可用于实现压缩的不同隔行扫描方案。

## 语法

```php
bool Imagick::setInterlaceScheme( int $interlace_scheme )
```

## 参数

此函数接受单个参数 `$interlace_scheme`，该参数保存与[隔行扫描常数](https://www.php.net/manual/en/imagick.constants.php/#imagick.constants.interlace-undefined)之一相对应的整数值。

所有隔行扫描常量列表如下：

*   `Imagick::INTERLACE_UNDEFINED` (0)
*   `Imagick::INTERLACE_LINE` (1)
*   `Imagick::INTERLACE_PLANE` (3)
*   `Imagick::INTERLACE_PARTITION` (4)
*   `Imagick::INTERLACE_GIF` (5)
*   `Imagick::INTERLACE_JPEG` (6)
*   `Imagick::INTERLACE_PNG` (7)

## 返回值

如果成功，此函数返回 `TRUE`。

## 异常

此函数在出错时引发 `ImagickException`。

下面的程序演示了 PHP 中的 `Imagick::setInterlaceScheme()` 函数：

### 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the interlace scheme
$imagick->setInterlaceScheme(Imagick::INTERLACE_PLANE);

// Get the interlace scheme
$interlace_scheme = $imagick->getInterlaceScheme();
echo $interlace_scheme;
?>
```

### 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the interlace scheme to be used in
// compression to imagick::INTERLACE_LINE
$imagick->setInterlaceScheme(Imagick::INTERLACE_LINE);

// Set the quality of the compression
$imagick->setImageCompressionQuality(1);

// Show the output
$imagick->setImageFormat('jpg');
header("Content-Type: image/jpg");
echo $imagick->getImageBlob();
?>
```

**输出：**
![](img/8b541c485cb8f4506a33db6f3ec287d1.png)

**引用：**[https://www.php.net/manual/en/imagick.setinterlacescheme.php](https://www.php.net/manual/en/imagick.setinterlacescheme.php)