# PHP Imagick getImageExtrema() 函数

## 函数说明

`Imagick::getImageExtrema()` 函数是 PHP 中的一个内置函数，用于获取图像的极值。极值是观察到函数的最大值或最小值的点。

## 语法

```php
array Imagick::getImageExtrema( void )
```

## 参数

此函数不接受任何参数。

## 异常

此函数在出错时引发 `ImagickException`。

## 返回值

此函数返回包含键 `"min"` 和 `"max"` 的关联数组。

## 示例程序

下面的程序说明了 PHP 中的 `Imagick::getImageExtrema()` 函数：

### 程序 1

```php
<?php

// Create new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Get the extrema
$extrema = $imagick->getImageExtrema();

print_r($extrema);
?>
```

### 程序 2

```php
<?php

// Create new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/20190918234528/colorize1.png');

// Get the extrema
$extrema = $imagick->getImageExtrema();

print_r($extrema);
?>
```

## 引用

[https://www.php.net/manual/en/imagick.getimageextrema.php](https://www.php.net/manual/en/imagick.getimageextrema.php)