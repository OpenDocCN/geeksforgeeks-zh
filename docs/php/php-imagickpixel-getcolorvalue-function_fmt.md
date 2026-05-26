# PHP ImagickPixel::getColorValue() 函数

> Original: [https://www.geeksforgeeks.org/php-imagickpixel-getcolorvalue-function/](https://www.geeksforgeeks.org/php-imagickpixel-getcolorvalue-function/)

`ImagickPixel::getColorValue()` 函数是 PHP 中的一个内置函数，用于获取给定 `ImagickPixel` 颜色的所提供颜色通道的归一化值。归一化值是介于 0 和 1 之间的浮点数。

## 语法

```php
float ImagickPixel::getColorValue( int $color )
```

## 参数

此函数接受单个参数 `$color`，该参数保存[颜色常量](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.color-black)之一。

下面给出了所有颜色常量的列表：

*   `Imagick::COLOR_BLUE(12)`
*   `Imagick::COLOR_CYAN(13)`
*   `Imagick::COLOR_GREEN(14)`
*   `Imagick::COLOR_RED(15)`
*   `Imagick::COLOR_YELLOW(16)`
*   `Imagick::COLOR_MAGENTA(17)`
*   `Imagick::COLOR_OPACITY(18)`
*   `Imagick::COLOR_ALPHA(19)`
*   `Imagick::COLOR_FUZZ(20)`

## 返回值

此函数返回一个浮点值，其中包含颜色值的归一化值。

## 异常

此函数在出错时引发 `ImagickException`。

## 示例

下面给出的程序说明了 PHP 中的 `ImagickPixel::getColorValue()` 函数：

### 程序 1

```php
<?php
// Create a new imagickPixel object
$imagickPixel = new ImagickPixel('#ad4c45');

// Get the Color value with imagick::COLOR_RED
$colorValue = $imagickPixel->getColorValue(imagick::COLOR_RED);
echo $colorValue;
?>
```

输出

```text
0.67843137254902
```

### 程序 2

```php
<?php
// Create a new imagick object
$imagick = new Imagick(
    'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Get the image histogram
$histogramElements = $imagick->getImageHistogram();

// Get the 301th pixel
$getPixel = $histogramElements[300];

// Get the Color value with imagick::COLOR_GREEN
$colorValue = $getPixel->getColorValue(imagick::COLOR_GREEN);

echo $colorValue;
?>
```

输出

```text
0.29803921568627
```

## 引用

[https://www.php.net/manual/en/imagickpixel.getcolorvalue.php](https://www.php.net/manual/en/imagickpixel.getcolorvalue.php)