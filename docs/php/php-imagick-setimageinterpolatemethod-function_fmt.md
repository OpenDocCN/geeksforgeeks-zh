# PHP Imagick setImageInterpolateMethod() 函数

> Original: [https://www.geeksforgeeks.org/php-imagick-setimageinterpolatemethod-function/](https://www.geeksforgeeks.org/php-imagick-setimageinterpolatemethod-function/)

`Imagick::setImageInterpolateMethod()` 函数是 PHP 中的内置函数，用于设置图像的隔行扫描方案。

## 语法

```php
bool Imagick::setImageInterpolateMethod( int $method )
```

## 参数

此函数接受单个参数 `$method`，该参数对应于[插值常数](https://www.php.net/manual/en/imagick.constants.php#imagick.constants.interpolate-undefined)之一。我们也可以像 `setImageInterpolateMethod(Imagick::INTERPOLATE_BICUBIC);` 那样直接传递常量。

插补常量列表如下：

*   `Imagick::INTERPOLATE_UNDEFINED(0)`
*   `Imagick::INTERPOLATE_AVERAGE(1)`
*   `Imagick::INTERPOLATE_BICUBIC(2)`
*   `Imagick::INTERPOLATE_BILINEAR(3)`
*   `Imagick::INTERPOLATE_FILTER(4)`
*   `Imagick::INTERPOLATE_INTEGER(5)`
*   `Imagick::INTERPOLATE_MESH(6)`
*   `Imagick::INTERPOLATE_NEARESTNEIGHBOR(7)`
*   `Imagick::INTERPOLATE_SPLINE(8)`

## 返回值

如果成功，此函数返回 `TRUE`。

下面的程序演示了 PHP 中的 `Imagick::setImageInterpolateMethod()` 函数：

## 程序 1

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Interpolate Method
$imagick->setImageInterpolateMethod(imagick::INTERPOLATE_BILINEAR);

// Get the Interpolate Method
$interpolateScheme = $imagick->getImageInterpolateMethod();
echo $interpolateScheme;
?>
```

发帖主题：Re：Колибри0.7.0

```
3 // Which corresponds to imagick::INTERPOLATE_BILINEAR.
```

## 程序 2

```php
<?php

// Create a new imagick object
$imagick = new Imagick(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Set the Interpolate Method
$imagick->setImageInterpolateMethod(imagick::INTERPOLATE_NEARESTNEIGHBOR);

// Get the Interpolate Method
$interpolateScheme = $imagick->getImageInterpolateMethod();
echo $interpolateScheme;
?>
```

发帖主题：Re：Колибри0.7.0

```
7 // Which corresponds to imagick::INTERPOLATE_NEARESTNEIGHBOR.
```

**引用：**[https://www.php.net/manual/en/imagick.setimageinterpolatemethod.php](https://www.php.net/manual/en/imagick.setimageinterpolatemethod.php)