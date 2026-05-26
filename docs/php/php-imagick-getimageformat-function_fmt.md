# PHP Imagick getImageFormat() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-getimageformat-function/](https://www.geeksforgeeks.org/php-imagick-getimageformat-function/)

`Imagick::getImageFormat()` 函数是 PHP 中的内置函数，用于获取序列中特定图像的格式。

## 语法

```php
string Imagick::getImageFormat( void )
```

## 参数

此函数不接受任何参数。

## 返回值

如果成功，此函数将返回图像格式的字符串。

## 程序 1

下面的程序说明 PHP 中的 `Imagick::getImageFormat()` 函数。

### 原始图像

![](img/efa5ea8e0258291fa60ad9a32c288072.png)

### PHP

```php
<?php
// require_once('path/vendor/autoload.php');

// Create an Imagick Object
$image = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-15.png');

// Use getImageFormat function to find the formats
// of image

$res= $image->getImageFormat();

// Display the format sequence of image
echo $res;
?>
```