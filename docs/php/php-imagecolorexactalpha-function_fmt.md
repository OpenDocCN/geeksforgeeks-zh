# PHP `imagecolorexactalpha()` 函数

> Original: [https://www.geeksforgeeks.org/php-imagecolorexactalpha-function/](https://www.geeksforgeeks.org/php-imagecolorexactalpha-function/)

`imagecolorexactalpha()` 函数是 PHP 中的一个内置函数，用于获取具有 Alpha 值的指定颜色的索引。此函数用于返回图像调色板中指定颜色和 Alpha 值（RGBA 值）的索引。

## 语法

```php
int imagecolorexactalpha ( $image, $red, $green, $blue, $alpha )
```

## 参数

此函数接受上述五个参数，如下所述：

*   `$image`：由图像创建函数（如 `imagecreatetruecolor()`）返回，用于指定图像资源。
*   `$red`：用于设置红色分量的值。
*   `$green`：用于设置绿色分量的值。
*   `$blue`：用于设置蓝色分量的值。
*   `$alpha`：用于设置图像的透明度。`$alpha` 的值在 0 到 127 之间，其中 0 表示完全不透明，127 表示完全透明。

## 返回值

如果成功，此函数将返回图像调色板中指定颜色和 Alpha 的索引，如果图像调色板中不存在该颜色，则返回 -1。

## 示例程序

下面的程序演示了 PHP 中的 `imagecolorexactalpha()` 函数：

### 程序 1

```php
<?php

// Setup an image
$image = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/col1.png');

$colors   = Array();
$colors[] = imagecolorexactalpha($image, 255, 0, 255, 0);
$colors[] = imagecolorexactalpha($image, 0, 225, 146, 127);
$colors[] = imagecolorexactalpha($image, 255, 56, 255, 55);
$colors[] = imagecolorexactalpha($image, 100, 55, 252, 20);

print_r($colors);

// Free from memory
imagedestroy($image);
?>
```

### 程序 2

```php
<?php

// Setup an image
$image = imagecreatefrompng(
'https://media.geeksforgeeks.org/wp-content/uploads/geeksforgeeks-9.png');

$colors   = Array(
    imagecolorexactalpha($image, 255, 120, 255, 45),
    imagecolorexactalpha($image, 160, 25, 146, 127),
    imagecolorexactalpha($image, 255, 56, 55, 155),
    imagecolorexactalpha($image, 190, 155, 252, 200)
);
print_r($colors);

// Free from memory
imagedestroy($image);
?>
```

## 相关文章

*   [php|imagecolorstotal()函数](https://www.geeksforgeeks.org/php-imagecolorstotal-function/)
*   [php|ImageColorSet()函数](https://www.geeksforgeeks.org/php-imagecolorset-function/)
*   [php|图像颜色分辨率 vealpha()函数](https://www.geeksforgeeks.org/php-imagecolorresolvealpha-function/)

## 引用

[http://php.net/manual/en/function.imagecolorexactalpha.php](http://php.net/manual/en/function.imagecolorexactalpha.php)