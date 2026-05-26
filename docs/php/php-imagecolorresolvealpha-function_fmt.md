# PHP `imagecolorresolvealpha()` 函数

> Original: [https://www.geeksforgeeks.org/php-imagecolorresolvealpha-function/](https://www.geeksforgeeks.org/php-imagecolorresolvealpha-function/)

## 函数描述
`imagecolorresolvealpha()` 函数是 PHP 中的一个内置函数，用于获取指定颜色和 Alpha 值或其最接近的备用值的索引。此函数返回所请求颜色的索引，可以是确切的颜色，也可以是最接近的替代颜色。

## 语法
```php
int imagecolorresolvealpha ( $image, $red, $green, $blue, $alpha )
```

## 参数
此函数接受上述五个参数，如下所述：

*   `$image`: 由图像创建函数（如 `imagecreatetruecolor()`）返回，用于指定图像资源。
*   `$red`: 用于设置红色分量的值。
*   `$green`: 用于设置绿色分量的值。
*   `$BLUE`: 用于设置蓝色分量的值。
*   `$alpha`: 用于设置图像的透明度。`$alpha` 的值在 0 到 127 之间，其中 0 表示完全不透明，127 表示完全透明。

## 返回值
此函数返回颜色的索引值。

## 示例程序
下面的程序演示了 PHP 中的 `imagecolorresolvealpha()` 函数：

### 程序 1：
```php
<?php

// Load an image
$image = imagecreatefromgif(
'https://media.geeksforgeeks.org/wp-content/uploads/animateImages.gif');

// Get closest colors from the image
$colors = array();
$colors[] = imagecolorresolvealpha($image, 156, 0, 255, 0);
$colors[] = imagecolorresolvealpha($image, 0, 255, 200, 50);
$colors[] = imagecolorresolvealpha($image, 16, 134, 35, 70);
$colors[] = imagecolorresolvealpha($image, 143, 255, 254, 100);

// Output
print_r($colors);

imagedestroy($image);
?>
```

### 程序 2：
```php
<?php

// Load an image
$image = imagecreatefromgif(
'https://media.geeksforgeeks.org/wp-content/uploads/animateImages.gif');

// Get closest colors from the image
$colors = array(
    imagecolorresolvealpha($image, 156, 0, 255, 0),
    imagecolorresolvealpha($image, 0, 255, 200, 50),
    imagecolorresolvealpha($image, 16, 134, 35, 70),
    imagecolorresolvealpha($image, 143, 255, 254, 100)
);

// Output
print_r($colors);

imagedestroy($image);
?>
```

## 相关文章
*   [`php|imagecolorclosestalpha()` 函数](https://www.geeksforgeeks.org/php-imagecolorclosestalpha-function/)
*   [`php|imagecolorclosest()` 函数](https://www.geeksforgeeks.org/php-imagecolorclosest-function/)

## 引用
[http://php.net/manual/en/function.imagecolorresolvealpha.php](http://php.net/manual/en/function.imagecolorresolvealpha.php)