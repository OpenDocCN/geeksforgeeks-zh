# PHP Imagick getImageChannelDistortions() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-getimagechanneldistortions-function/](https://www.geeksforgeeks.org/php-imagick-getimagechanneldistortions-function/)

`Imagick::getImageChannelDistortions()` 函数是 PHP 中的内置函数，用于将图像的一个或多个图像通道与重建图像进行比较，并返回指定的失真度量。`GetImageChannelDistortion()` 和 `getImageChannelDistortions()` 之间的区别在于后者不一定接受通道参数，因此它也只能接受两个参数。

## 语法

```php
float Imagick::getImageChannelDistortions( Imagick $reference, int $metric, int $channel = Imagick::CHANNEL_DEFAULT)
```

## 参数

此函数接受上述三个参数，如下所述：

*   `$reference`：它指定图像的 `Imagick` 对象。
*   `$metric`：它指定[公制类型常量](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.metric)之一。
    度量常量列表如下：
    *   `Imagick::METRIC_UNDEFINED(0)`
    *   `Imagick::METRIC_MEANABSOLUTEERROR(1)`
    *   `Imagick::METRIC_MEANSQUAREERROR(2)`
    *   `Imagick::METRIC_PEAKABSOLUTEERROR(3)`
    *   `Imagick::METRIC_PEAKSIGNALTONOISERATIO(4)`
    *   `Imagick::METRIC_ROOTMEANSQUAREDERROR(5)`
*   `$channel`：它指定对通道模式有效的通道常量。 使用按位运算符组合十个以上的一个通道类型常量。 通道常量的默认值为 `Imagick::CHANNEL_DEFAULT`。

## 异常

此函数在出错时引发 `ImagickException`。

## 返回值

此函数返回双精度描述通道失真。

## 示例

以下程序说明了 PHP 中的 `Imagick::getImageChannelDistortions()` 函数：

### 程序 1

```php
<?php

// Create two new imagick object
$imagick1 = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/20190823154611/geeksforgeeks24.png');

$imagick2 = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/20190916133223/diamond.png');

// Get the distortion with METRIC constant as imagick::METRIC_MEANABSOLUTEERROR
$distortion = $imagick1->getImageChannelDistortions($imagick2, 1);

echo $distortion;
?>
```

### 程序 2

```php
<?php

// Create two new imagick object
$imagick1 = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/20190823154611/geeksforgeeks24.png');

$imagick2 = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/20190823154611/geeksforgeeks24.png');

// Get the distortion with METRIC constant as imagick::METRIC_MEANABSOLUTEERROR
$distortion = $imagick1->getImageChannelDistortions($imagick2, 1);

echo $distortion;
?>
```

输出：

```
0
```

### 程序 3

```php
<?php

// Create two new imagick object
$imagick1 = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/20190823154611/geeksforgeeks24.png');

$imagick2 = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/20190916133633/gausian.png');

// Get the distortion with METRIC constant as imagick::METRIC_MEANSQUAREERROR
$distortion = $imagick1->getImageChannelDistortions($imagick2, 2);

echo $distortion;
?>
```

输出：

```
0.048318723480804
```

## 引用

[https://www.php.net/manual/en/imagick.getimagechanneldistortions.php](https://www.php.net/manual/en/imagick.getimagechanneldistortions.php)