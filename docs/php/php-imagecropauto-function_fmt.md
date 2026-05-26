# PHP `imagecropauto()` 函数

> Original: [https://www.geeksforgeeks.org/php-imagecropauto-function/](https://www.geeksforgeeks.org/php-imagecropauto-function/)

`imagecropauto()` 函数是 PHP 中的一个内置函数，用于使用可用模式之一自动裁剪图像。

## 语法

```php
resource imagecropauto( resource $image, int $mode, float $threshold, int $color )
```

## 参数

此函数接受上述四个参数，如下所述：

*   `$image`：它指定要裁剪的图像资源。
*   `$mode` (可选)：它指定一个对应于裁剪模式的整数。

裁剪模式列表如下：

*   `IMG_CROP_DEFAULT` (0)
*   `IMG_CROP_TRANSPARENT` (1)
*   `IMG_CROP_BLACK` (2)
*   `IMG_CROP_WHITE` (3)
*   `IMG_CROP_SIDES` (4)
*   `IMG_CROP_THRESHOLD` (5)
*   `$threshold` (可选)：它指定在比较图像颜色和要裁剪的颜色时要使用的公差百分比。
*   `$color` (可选)：它指定 RGB 颜色值或调色板索引。

## 返回值

如果成功，此函数返回 `TRUE`。

## 异常

此函数在出错时抛出异常。

下面给出的程序演示了 PHP 中的 `imagecropauto()` 函数：

## 程序 1

```php
<?php

// Load the png image
$im = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-13.png');

// Crop the extra white area
$cropped = imagecropauto($im, IMG_CROP_WHITE);

// Convert it to a png file
header('Content-type: image/png');
imagepng($cropped);
?>
```

输出：
![](img/65d5d05c80ff77343382f41b68ee4fa8.png)

## 程序 2

```php
<?php

// Load the png image
$im = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/20200123135210/geeksforgeeksinverted.png');

// Crop the image
$cropped = imagecropauto($im, IMG_CROP_BLACK);

// Convert it to a png file
header('Content-type: image/png');
imagepng($cropped);
?>
```

输出：
![](img/869d86cbd24bae5dc6ea40f717fa6f7a.png)

## 引用

[https://www.php.net/manual/en/function.imagecropauto.php](https://www.php.net/manual/en/function.imagecropauto.php)